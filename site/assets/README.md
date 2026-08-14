# Assets do site

## Vídeos

Ambos gerados no Google Flow, 1280×720, 24 fps, H.264, sem áudio.

| Arquivo | Onde | Duração | Tamanho |
|---|---|---|---|
| `hero-bomba.mp4` | fundo do hero | 15,91 s | 3,10 MB |
| `sobre-fabrica.mp4` | figura da seção "Sobre nós" | 5,91 s | 1,58 MB |

Pôsteres: `poster-hero.jpg` e `poster-sobre.jpg` — primeiro quadro de cada,
exibidos enquanto o vídeo carrega.

### Os dois têm ida e volta embutidas

O `loop` nativo do navegador fecha sem emenda porque a volta está dentro do
arquivo. Em ambos o movimento é uma **deriva lateral lenta de câmera**, então a
volta lê como oscilação, não como marcha a ré — ninguém percebe que inverteu.

> Isso é diferente do caso do vídeo de desmonte, descartado antes: lá a volta
> remontava a bomba, e o olho pegava na hora. Reverter só é invisível quando o
> que se move é a câmera, não o assunto.

O quadro do ápice e o do reinício são descartados no processamento — sem isso
cada virada teria um quadro repetido, visível como travada.

### Recorte aplicado ao vídeo do "Sobre nós"

O bruto de origem tinha **duas cenas**: fábrica com fileira de bombas, depois um
crossfade entre 3,2 s e 3,8 s para vasos de inox na neve, num campo de petróleo
— fora do segmento e fora de contexto. Só os primeiros 3,0 s foram aproveitados,
antes do início da dissolvência.

### Cor

Nenhuma correção aplicada. Testei rotação de matiz para puxar o azul dos
motores na direção do roxo da marca e **descartei**: a rotação contamina o inox,
que vira roxo-magenta, justamente o oposto da leitura de higiene que o material
precisa ter.

E o azul é autêntico — os motores das fotos reais de produto, nos cards de
"Nossas soluções", são do mesmo azul. Manter cria coerência entre o hero e os
produtos logo abaixo.

### Refazer

```bash
# ida e volta, preservando todos os quadros do original
ffmpeg -i bruto.mp4 -filter_complex \
  "[0:v]split[a][b];[b]reverse,trim=start_frame=1:end_frame=191,\
setpts=PTS-STARTPTS[r];[a][r]concat=n=2:v=1[out]" \
  -map "[out]" -an -r 24 -c:v libx264 -preset slow -crf 21 \
  -pix_fmt yuv420p -movflags +faststart saida.mp4
```

`end_frame` = total de quadros menos 1. Se mudar a velocidade com
`setpts=PTS/N`, passe `-r` explicitamente na saída — `fps=` dentro do
`-filter_complex` não surte efeito e descarta quadros.

### Enquadramento

O hero é mais largo que 16:9: o vídeo é escalado pela largura e o corte acontece
em cima e embaixo. O controle é `object-position` na regra `.hero__video`; a
lavagem clara que segura a legibilidade do texto é a `.hero__wash`, logo abaixo.

### Pendências

- **1080p.** Os dois são 720p e ficam levemente suaves em monitor grande.
- **Filmagem real.** Continua valendo mais que vídeo gerado, em credibilidade.
  Ver `marketing/video-hero-briefing.md`.

---

## Fotos dos produtos — `produtos/`

Ver `produtos/README.md`.

## Logo

Não fica aqui — vai em `identidade/logo.svg` (e `logo-branco.svg` para fundo
escuro). Hoje o header e o rodapé usam um wordmark provisório em texto.
