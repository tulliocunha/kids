# Globoplay Kids — Abordagem 2 (Roleta)

Protótipo de TV (1920×1080, escalado por transform) do Globoplay Kids, versão Roleta.
Navegação por D-pad (setas / OK / Voltar) e por clique.

## Testar localmente

O arquivo carrega assets por caminho relativo, então precisa de um servidor HTTP
(abrir o `index.html` direto do disco bloqueia os fetches).

    cd pacote-roleta
    python3 -m http.server 8000
    # abra http://localhost:8000

## Subir no GitHub Pages

1. Crie um repositório e envie **o conteúdo desta pasta** na raiz do branch.
2. Settings → Pages → Source: `main` / `/ (root)`.
3. O `.nojekyll` já está incluído (o Jekyll ignoraria as pastas com `_`, como `_ds/`).

## Estrutura

    index.html   protótipo (uma única página, cinco telas)
    support.js   runtime
    _ds/         Playkit 3.0 — Globoplay Design System (tokens + bundle)
    icons/       ícones dos universos e do seletor
    uploads/     cartazes dos IPs, stickers, artes do menu, avatares, preview.mp4

## Controles

- ← / → : cartazes do universo (transborda para o universo vizinho)
- ↑ / ↓ : alterna entre leque, roleta de universos e cabeçalho; ↓ na roleta abre o Ver tudo
- OK / Enter : assistir, entrar no universo, abrir o card do menu
- Esc / Backspace / Voltar : volta uma tela

## Telas

perfis → idade → home (roleta de universos + leque de cartazes) → ver tudo → player,
mais o universo **Menu** (Ver tudo, Encontrar algo para assistir, Buscar).

## Notas para navegador de TV

- Teclas aceitas por `e.key` **e** por `keyCode` (37–40, 13, 27, 8, 10009 Tizen, 461 webOS).
- Nenhum elemento entra na ordem de foco nativa (`tabindex` só negativo): o foco é
  todo controlado pelo estado do protótipo, para não competir com o foco do navegador.
- O palco reescala em `resize`/`orientationchange` e em cinco tentativas depois do load
  (TVs relatam o viewport com atraso). Funciona em 1280×720 e 1920×1080.
- O vídeo do quadro 16:9 só é montado se o arquivo decodificar; se a TV não tocar MP4,
  o cartaz continua aparecendo no lugar.
