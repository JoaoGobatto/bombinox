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
