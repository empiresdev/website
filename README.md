# empiresdev.com

Landing page da **EMPIRES Dev**, hospedada no GitHub Pages.

🔗 https://empiresdev.com

## Estrutura

```
index.html          Página única — HTML + CSS inline, sem build e sem dependências
CNAME               Domínio customizado do GitHub Pages (empiresdev.com)
.nojekyll           Desliga o processamento Jekyll do Pages
robots.txt          Diretivas de crawler
sitemap.xml         Sitemap
assets/             Imagens usadas pela página (logo, favicon, og-image)
brand/              Kit de marca — logos em SVG e PNG (fonte da verdade)
design/             Fonte original exportada do Claude Design, para referência
```

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
