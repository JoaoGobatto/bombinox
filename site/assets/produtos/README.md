# Fotos dos produtos

Suba os arquivos aqui com **exatamente** estes nomes. O HTML já aponta para
eles — nenhuma mudança de código é necessária.

| Arquivo | Produto | Como identificar |
|---|---|---|
| `bomba-duplo-parafuso.png` | Bomba duplo parafuso | motor **azul/turquesa**, corpo alongado |
| `bomba-lobulos.png` | Bomba de lóbulos | motor **cinza-esverdeado**, cabeçote redondo com parafusos |
| `triblender.png` | Triblender / misturadores | funil cônico sobre base tubular |

Enquanto um arquivo faltar, o card mostra a etiqueta "foto pendente" com o nome
esperado. O `<img>` se remove sozinho, então não aparece ícone de imagem
quebrada.

`.jpg` também funciona — nesse caso troque a extensão no `src` dentro de
`site/index.html`.

## Formato

- Produto recortado em fundo branco (ou PNG com fundo transparente, melhor
  ainda — a placa do card tem um leve degradê)
- Proporção livre: a imagem é encaixada por dentro de uma área 4:3 com
  `object-fit: contain`, sem corte nem distorção
- Largura útil de ~520px no desktop; 900–1200px de lado maior já cobre telas
  retina sem pesar
