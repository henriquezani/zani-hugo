# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Visão geral

Blog pessoal estático do Henrique Zani (https://henriquezani.com/), feito em **Hugo** com o tema
**[Hextra](https://github.com/imfing/hextra)**. O repositório nasceu do `hextra-starter-template` e
contém quase só conteúdo e configuração — não há código de aplicação, testes nem linters.

O conteúdo é majoritariamente em **pt-BR** (`languageCode: pt-BR` em `hugo.yaml`), mas a interface do
tema e alguns títulos de seção estão em inglês.

## Comandos

```shell
# Baixar/sincronizar o tema (Hugo Module) — necessário após clonar
hugo mod tidy

# Servidor local em http://localhost:1313
hugo server --logLevel debug --disableFastRender -p 1313

# Incluir posts com draft: true ou data futura
hugo server -D -F

# Build de produção (gera ./public)
hugo --gc --minify

# Atualizar o tema Hextra
hugo mod get -u && hugo mod tidy
```

Pré-requisitos: Hugo **extended** (versão fixada em `0.152.2` no `netlify.toml` e no workflow) e Go
(o tema é um Go module).

## Arquitetura

### O tema é um Go module, não um submodule

Não existe diretório `themes/`, `layouts/` nem `assets/` no repositório. O Hextra é importado em
`hugo.yaml` via `module.imports` e resolvido pelo Go (`go.mod`/`go.sum`). Consequências:

- Para customizar um template, **crie** o arquivo em `layouts/` na raiz espelhando o caminho do tema
  — a versão local sobrescreve a do módulo. Nunca edite arquivos dentro do cache de módulos.
- O `module` declarado em `go.mod` ainda é `github.com/imfing/hextra-starter-template` (herdado do
  template). Não é usado para nada além de satisfazer o Go; trocar o nome não é necessário.

### Estrutura de conteúdo

```
content/
  _index.md        # home: bio, experiência e lista manual de posts
  about.md         # usa `type: about` (layout próprio do Hextra)
  posts/
    _index.md      # índice do blog, agrupado por mês — lista manual
    YYYY/MM/DD/<slug>/index.md   # page bundle de cada post
  docs/            # demo remanescente do template, não é conteúdo real
```

Posts são **page bundles** em diretórios com data (`content/posts/2026/04/28/cpp/index.md`), o que faz
a URL final ser `/posts/2026/04/28/cpp/`. O front matter segue este padrão:

```yaml
---
title: C++ Review
date: "2026-04-28T14:00:00-03:00"   # sempre com offset -03:00
slug: cpp                            # igual ao nome do diretório
tags: [...]
draft: false
---
```

**Gotcha importante:** os índices de posts são escritos à mão. Ao adicionar um post novo é preciso
atualizar **dois** arquivos além do post em si:

1. `content/posts/_index.md` — adicionar sob o cabeçalho `## YYYY - Mês` (criando a seção se não existir)
2. `content/_index.md` — adicionar no topo da lista da seção `### blogs`

Ambos usam links absolutos no formato `/posts/YYYY/MM/DD/<slug>`.

### Configuração

Tudo vive em `hugo.yaml`: menu da navbar (incluindo o item de busca e os ícones de GitHub/X),
`params.theme.default: dark`, autor, descrição e `markup.goldmark.renderer.unsafe: true` (HTML cru é
permitido dentro do Markdown — a home usa isso para o botão "View all posts").

`i18n/en.yaml` contém apenas a string de copyright do rodapé.

## Deploy

O site é publicado em **dois** destinos, com `baseURL` diferente em cada um:

- **Netlify** (produção real, `henriquezani.com`) — `netlify.toml`. O build de produção usa o
  `baseURL` do `hugo.yaml` (domínio apex, sem `www`); deploy previews e branch deploys sobrescrevem
  com `-b ${DEPLOY_PRIME_URL}`. Não reintroduza `DEPLOY_PRIME_URL` no contexto de produção: ele
  resolve para o domínio primário da Netlify e contamina sitemap/RSS/links absolutos.
- **GitHub Pages** — `.github/workflows/pages.yaml`, dispara em push para `master` e força
  `--baseURL "https://henriquezani.github.io/"`.

A versão do Hugo está fixada em três lugares (`netlify.toml`, `pages.yaml`, `.devcontainer/devcontainer.json`)
e precisa ser atualizada em conjunto.
