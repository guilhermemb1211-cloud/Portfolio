# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Visualizar localmente

```bash
python -m http.server 8000
```

Acesse `http://localhost:8000`. Não há build, bundler ou dependências — é HTML/CSS/JS puro.

## Arquitetura

Site estático sem frameworks. Todo o CSS está inline dentro de cada `<style>` no `<head>` de cada página — não há folha de estilos externa compartilhada.

- `index.html` — página principal do portfolio (hero, experiência, projetos, skills, formação, contato)
- `projetos/baja/index.html` — página de detalhes do projeto Baja SAE MackGear
- `projetos/tcc/index.html` — página de detalhes do TCC (impressão 3D)
- `projetos/tech/index.html` — página de detalhes dos projetos Python/Data Science

As páginas de projeto são acessadas via links `<a href="projetos/baja/">` na página principal.

## Design system

Todas as páginas compartilham as mesmas variáveis CSS definidas em `:root`. Ao alterar cores ou estilos, replique a mudança em todos os `index.html`:

```css
--bg: #0d0f14;
--accent: #4f8ef7;
--accent2: #7c3aed;
--accent-grad: linear-gradient(135deg, #4f8ef7, #7c3aed);
--card: #161b27;
--radius: 14px;
```

## Regras do projeto

- Todo texto em **português (pt-BR)**
- Sem frameworks externos (sem Bootstrap, Tailwind, React, etc.)
- CSS sempre inline na própria página (`<style>` no `<head>`)
- Animações de scroll usam `IntersectionObserver` com classe `.fade-in` / `.visible`

## Deploy

GitHub Pages a partir da branch `main`, raiz `/`. O link público é:
`https://guilhermemb1211-cloud.github.io/Portfolio/`
