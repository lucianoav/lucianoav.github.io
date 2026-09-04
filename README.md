# lucianoav.github.io

Blog e portfólio de Luciano Alves — **While True: coffee++**.
Site estático em [Jekyll](https://jekyllrb.com/) com o tema [Minima](https://github.com/jekyll/minima),
publicado via GitHub Pages em <https://lucianoav.github.io>.

## Rodando localmente

```bash
bundle install
bundle exec jekyll serve
```

O site fica disponível em <http://localhost:4000>.

O Google Analytics só é incluído quando `jekyll.environment == "production"`,
então o desenvolvimento local não gera métricas. Para conferir o build de produção:

```bash
JEKYLL_ENV=production bundle exec jekyll build
```

## Estrutura

| Caminho | Descrição |
|---|---|
| `_posts/` | Posts do blog (`AAAA-MM-DD-slug.markdown`) |
| `_layouts/` | Layouts `default` e `post` que sobrescrevem os do Minima |
| `_includes/` | `analytics.html` (GA) e `mathjax.html` (carregado só com `mathjax: true` no front matter) |
| `assets/main.scss` | Camada de estilo própria sobre o Minima, incluindo modo escuro |
| `about.markdown` | Página `/about/` |

Os posts usam o permalink `/blog/:title/`.
