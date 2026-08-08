# Assets do site

Arquivos que o site espera e ainda não existem. Enquanto faltarem, as áreas
correspondentes mostram placeholder marcado — foto de banco genérica não entra,
por decisão de marca (`identidade/design-guide.md`).

## Vídeo do hero — `hero-loop.mp4` ✅ em uso

Exploded view de bomba centrífuga, gerado no Google Flow. O arquivo em uso é
uma versão processada do original: **1,25× de velocidade e vai-e-volta
embutido**.

| | |
|---|---|
| Resolução | 1280×720 (16:9) |
| Duração | 15,96 s (7,98 s de ida + 7,98 s de volta) |
| Quadros | 30 fps · 478 quadros |
| Codec | H.264 (`avc1`), sem áudio |
| Tamanho | 2,70 MB |

`hero-poster.jpg` é o primeiro quadro, exibido enquanto o vídeo carrega.

### Por que o vai-e-volta está no arquivo

Navegador não reproduz vídeo de trás para frente: `playbackRate` negativo não
existe, e simular com JavaScript significa reposicionar `currentTime` a cada
quadro — cada salto força o decodificador a voltar até o keyframe anterior, o
que engasga.

Com ida e volta dentro do arquivo, o `loop` nativo resolve: a volta termina no
quadro montado, que é exatamente onde a ida começa. Emenda invisível, custo zero
de JavaScript.

O quadro do ápice e o do reinício foram descartados no processamento — sem eles
haveria um quadro repetido em cada virada, visível como uma travadinha.

### Refazer com outra velocidade

O original (10,01 s, 24 fps, com áudio) não está mais na pasta — seria publicado
sem ser usado. Está no histórico do git:

```bash
git show ce1881d:site/assets/hero.mp4 > hero-original.mp4
```

Comando que gerou o arquivo atual (troque `1.25` pela velocidade desejada):

```bash
ffmpeg -i hero-original.mp4 \
  -filter_complex "[0:v]setpts=PTS/1.25,fps=30,split[a][b];\
[b]reverse,trim=start_frame=1:end_frame=239,setpts=PTS-STARTPTS[r];\
[a][r]concat=n=2:v=1[out]" \
  -map "[out]" -an -c:v libx264 -preset slow -crf 19 \
  -pix_fmt yuv420p -movflags +faststart hero-loop.mp4
```

### Enquadramento

O hero é mais largo que 16:9, então o vídeo é escalado pela largura e o corte
acontece em cima e embaixo. Para ajustar, mexer em `object-position` na regra
`.hero__video` de `site/css/style.css`:

```css
object-position: center 45%;   /* menor = mostra mais do topo */
```

A intensidade da lavagem clara sobre a metade esquerda (que mantém a headline
legível) fica na regra `.hero__wash`, logo abaixo.

### Limitações conhecidas

- **720p** fica levemente suave em monitor grande, já que o hero ocupa a largura
  toda. Se houver versão em 1080p, vale trocar.
- Se o vídeo falhar ou demorar, aparece atrás dele uma textura de inox como
  fallback — nunca uma foto genérica.

## Fotos dos produtos — seção "Nossas soluções"

Já estão cabeadas no HTML. Basta salvar os arquivos com **exatamente** estes
nomes em `site/assets/produtos/` que eles aparecem sozinhos — nenhuma mudança
de código é necessária. Enquanto faltarem, cada card mostra a etiqueta "foto
pendente" com o nome esperado.

| Arquivo | Produto |
|---|---|
| `produtos/bomba-duplo-parafuso.png` | Bomba duplo parafuso |
| `produtos/bomba-lobulos.png` | Bomba de lóbulos |
| `produtos/triblender.png` | Triblender / misturadores |

São as mesmas fotos que já estão no site atual da Bombinox: produto recortado
em fundo branco. A placa do card também é clara, então o recorte encaixa sem
contorno aparente. PNG com fundo transparente funciona ainda melhor.

Proporção da placa: 4:3. Imagens em outra proporção são encaixadas por dentro
(`object-fit: contain`), sem corte nem distorção.

## Foto da seção "Sobre nós"

| Arquivo | Uso |
|---|---|
| `fabrica.jpg` | proporção 4:3, fábrica ou linha de produção |

Trocar o `<div class="sobre__ph">` por um `<img>` em `site/index.html`.

## Logo

Não fica aqui — vai em `identidade/logo.svg` (e `logo-branco.svg` para fundo
escuro). Hoje o header usa um wordmark provisório em texto.
