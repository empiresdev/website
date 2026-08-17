# empiresdev.com

Landing page da **EMPIRES Dev**, hospedada no GitHub Pages.

🔗 https://empiresdev.com

## Estrutura

```
index.html          Versão em inglês, servida na raiz (/)
br/index.html       Versão em português, servida em /br/
assets/styles.css   CSS compartilhado pelas duas versões
CNAME               Domínio customizado do GitHub Pages (empiresdev.com)
.nojekyll           Desliga o processamento Jekyll do Pages
robots.txt          Diretivas de crawler
sitemap.xml         Sitemap com as duas URLs e suas alternâncias de idioma
assets/             Imagens usadas pelas páginas (logo, favicon, og-image, Metria)
brand/              Kit de marca — logos em SVG e PNG (fonte da verdade)
design/             Fonte original exportada do Claude Design, para referência
```

## Bilíngue

O site tem duas versões estáticas, uma por URL — sem JavaScript e sem
redirecionamento automático por idioma do navegador:

| URL | Idioma | `lang` |
| --- | --- | --- |
| `/` | Inglês | `en` |
| `/br/` | Português | `pt-BR` |

O seletor no canto superior direito são links comuns entre as duas. Cada página
declara a outra em `<link rel="alternate" hreflang>`, com `x-default` apontando
para a raiz.

**Ao editar, mude as duas.** Todo texto visível existe em dois arquivos. O CSS
não: ele mora só em `assets/styles.css`.

Os screenshots do Metria continuam em português nas duas versões — a interface
do app é em português, e trocá-los exigiria rodar o app em outra locale. Nas
páginas em inglês o `alt` das imagens diz isso explicitamente.

## Desenvolvimento local

Não há build. Basta abrir o arquivo ou servir a pasta:

```bash
python3 -m http.server 8000
```

Depois acesse http://localhost:8000.

## Deploy

Todo push para `main` publica automaticamente via GitHub Pages.
A configuração fica em **Settings → Pages** (Source: `Deploy from a branch` → `main` / `/ (root)`).

## Marca

| Token | Valor |
| --- | --- |
| Fundo | `#061B40` |
| Texto | `#FCF5ED` |
| Texto suave | `#A8B4C8` |
| Destaque | `#38B6B2` |
| Divisor | `#1E4272` |
| Tipografia | Space Grotesk |

## Regerar a imagem de compartilhamento (og-image)

`assets/og-image.png` (1200×630) é gerada a partir de um SVG com [`librsvg`](https://formulae.brew.sh/formula/librsvg):

```bash
rsvg-convert -w 1200 -h 630 design/og.svg -o assets/og-image.png
```
