# Globoplay Kids — Roleta (TV)

Protótipo navegável da abordagem **Roleta** do Globoplay Kids para TV (1920×1080,
escalado por transform). Português do Brasil, pré-leitores de 3 a 6 anos.

## Rodar

Precisa de um servidor HTTP (o arquivo carrega assets relativos):

```bash
npx serve .          # ou: python3 -m http.server
```

Abra `index.html`.

## Publicar no GitHub Pages

1. Crie o repositório e envie o conteúdo desta pasta na raiz da branch.
2. Settings → Pages → Source: *Deploy from a branch*, branch `main`, pasta `/ (root)`.
3. O `.nojekyll` já está incluído (necessário por causa da pasta `_ds/`).

## Navegação

- **Setas** movem o foco, **OK/Enter** confirma, **Esc** volta.
- Fluxo: perfis → idade → home (leque de posters + roleta de universos) → ver tudo → player.
- Área dos adultos atrás da conta de multiplicação.

## Estrutura

| Caminho | O que é |
| --- | --- |
| `index.html` | O protótipo inteiro (template + lógica) |
| `support.js` | Runtime do componente |
| `_ds/…` | Design system Playkit 3.0 (tokens + bundle) |
| `icons/roleta/` | Ícones dos universos, cronômetro, seta e logo |
| `uploads/IPs Globoplay/` | Cartazes dos títulos |
| `uploads/Arquivo/` | Stickers (4 por universo) |

Fontes (Inter, Slackey) vêm do Google Fonts — precisa de internet na primeira carga.
