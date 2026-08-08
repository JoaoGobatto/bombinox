# Assets do site

Arquivos que o site espera e ainda não existem. Enquanto faltarem, as áreas
correspondentes mostram placeholder marcado — foto de banco genérica não entra,
por decisão de marca (`identidade/design-guide.md`).

## Vídeo do hero — `hero.mp4` ✅ em uso

Gerado no Google Flow: bomba desmontando.

| | |
|---|---|
| Resolução | 1280×720 (16:9) |
| Duração | 10,01 s |
| Codec | H.264 (`avc1`) + AAC — toca em todo navegador |
| Tamanho | 2,42 MB |

Roda `autoplay muted loop playsinline`. A trilha de áudio existe mas nunca toca;
removê-la economizaria alguns KB, se um dia o arquivo for reexportado.

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
