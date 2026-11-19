# Site Herta Silva | Massoterapeuta

Site estático (HTML, CSS e JS num único `index.html`), sem etapa de build.

No ar: https://site-herta-silva.vercel.app/

## Rodar localmente

Na pasta do projeto:

```bash
npx serve .
```

ou, com Python:

```bash
python -m http.server 8080
```

Depois abra `http://localhost:8080` (ou o endereço que o `serve` mostrar). Abrir o `index.html` direto pelo arquivo não funciona, porque as imagens usam caminhos a partir da raiz (`/img/...`).

## Estrutura

- `index.html`: página com CSS e JS embutidos
- `img/`: fotos em webp (800 e 1600 px; recortes em 700 e 1200 px) e a logo em PNG
- `vendor/`: GSAP 3.12.5 + ScrollTrigger e Lenis 1.1.20, servidos pelo próprio site
- `favicon.svg`, `apple-touch-icon.png`, `og-image.jpg` (preview do link no WhatsApp)
- `vercel.json`: URLs limpas e cache longo para `/img` e `/vendor`

## Publicar

O repositório está ligado à Vercel: cada push na branch `main` publica sozinho.
Na primeira vez: Vercel > Add New > Project > importar o repositório, Framework Preset: Other, Build Command vazio, Output Directory `./`.

Se o domínio mudar, atualize no `index.html` o `<link rel="canonical">`, as tags `og:url`, `og:image`, `twitter:image` e a `url` dos dados estruturados.

## Trocar uma foto

Gere as duas larguras em webp com o mesmo nome (ex.: `img/05-maos-sessao-800.webp` e `img/05-maos-sessao-1600.webp`) e substitua os arquivos.
