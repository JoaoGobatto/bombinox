# Assets do site

Arquivos que o site espera e ainda não existem. Enquanto faltarem, as áreas
correspondentes mostram placeholder marcado — foto de banco genérica não entra,
por decisão de marca (`identidade/design-guide.md`).

## Vídeo do hero — `hero-once.mp4` ✅ em uso

Exploded view de bomba centrífuga, gerado no Google Flow. O arquivo em uso tem
**1,25× de velocidade embutida** no próprio vídeo.

| | |
|---|---|
| Resolução | 1280×720 (16:9) |
| Duração | 8,00 s |
| Quadros | 30 fps · 240 quadros |
| Codec | H.264 (`avc1`), sem áudio |
| Tamanho | 1,41 MB |

`hero-poster.jpg` é o primeiro quadro, exibido enquanto o vídeo carrega.

### Toca uma vez e congela

O `<video>` **não tem o atributo `loop`**. Isso basta: ao chegar no fim, o
navegador mantém o último quadro na tela e não volta ao início. Não há
JavaScript envolvido — tirar `loop` é a implementação inteira.

O quadro final é o exploded view completo, com as peças separadas. É ele que
fica em tela permanentemente depois dos 8 segundos, então vale tratá-lo como
imagem principal do hero: as peças se espalham para a direita e o motor fica
sob a lavagem clara, atrás do texto.

**Se um dia o loop voltar a ser desejado**, basta acrescentar `loop` no
`<video>` — mas aí o corte do último quadro para o primeiro fica seco, porque o
vídeo começa montado e termina desmontado. Nesse caso o certo é gerar a versão
vai-e-volta (comando no histórico, commit `a00f9db`).

### Refazer com outra velocidade

O original (10,01 s, 24 fps, com áudio) não está mais na pasta — seria publicado
sem ser usado. Está no histórico do git:

```bash
git show ce1881d:site/assets/hero.mp4 > hero-original.mp4
```

Comando que gerou o arquivo atual (troque `1.25` pela velocidade desejada):

```bash
ffmpeg -i hero-original.mp4 \
  -filter_complex "[0:v]setpts=PTS/1.25[out]" -map "[out]" \
  -an -r 30 -c:v libx264 -preset slow -crf 19 \
  -pix_fmt yuv420p -movflags +faststart hero-once.mp4
```

O `-r 30` na saída não é opcional. Passar `fps=30` dentro do `-filter_complex`
não surte efeito aqui: a saída sai em 25 fps e cerca de 17% dos quadros do
original são descartados.

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
