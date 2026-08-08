# Assets do site

Arquivos que o site espera e ainda não existem. Enquanto faltarem, as áreas
correspondentes mostram placeholder marcado — foto de banco genérica não entra,
por decisão de marca (`identidade/design-guide.md`).

## Vídeo do hero

| Arquivo | Uso |
|---|---|
| `hero.mp4` | fonte principal (H.264) |
| `hero.webm` | fonte alternativa, opcional |
| `hero-poster.jpg` | primeiro quadro, aparece antes do vídeo carregar |

Depois de colocar os arquivos aqui, descomentar os `<source>` em
`site/index.html` (bloco marcado `► VÍDEO DE FUNDO`).

**O que o vídeo deve mostrar:** equipamento em inox em operação — bomba,
tubulação, linha de processo. Ambiente limpo e organizado, iluminação clara,
reflexo metálico. Sem pessoas de terno, sem estética de banco de imagem.

**Especificação sugerida:** 1920×1080, 8–15s em loop, sem áudio, arquivo abaixo
de ~5 MB. O vídeo roda `muted` e `loop` — o corte precisa fechar sem salto
perceptível.

O texto do hero fica sobre a metade esquerda com uma lavagem clara por cima.
Enquadrar o assunto à direita para não competir com a headline.

## Foto da seção "Sobre nós"

| Arquivo | Uso |
|---|---|
| `fabrica.jpg` | proporção 4:3, fábrica ou linha de produção |

Trocar o `<div class="sobre__ph">` por um `<img>` em `site/index.html`.

## Logo

Não fica aqui — vai em `identidade/logo.svg` (e `logo-branco.svg` para fundo
escuro). Hoje o header usa um wordmark provisório em texto.
