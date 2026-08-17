# Plano de valor do site

O que já foi feito, o que depende de você e o que vem depois — ordenado por
impacto em receita, não por esforço.

---

## O diagnóstico

O site estava bonito e **sem caminho de venda**. Todo botão apontava para
âncora vazia, não havia como pedir orçamento, o header tinha um carrinho com
badge zero sugerindo e-commerce inexistente, e o link compartilhado no WhatsApp
ou LinkedIn saía sem imagem nem descrição.

Para indústria B2B, valor de site = **lead qualificado**. Beleza sem conversão
não vale nada.

---

## 1. Já implementado

### Conversão
- **Seção de contato** com CTA que abre e-mail **já preenchido** com os campos
  que qualificam o pedido: equipamento, aplicação, produto bombeado, vazão,
  pressão, material, empresa e país. Transforma "oi, quero um orçamento" em RFQ
  técnica — sem exigir backend nenhum.
- **Telefone clicável e botão de orçamento no header**, no lugar do carrinho e
  da busca que não faziam nada.
- **Âncoras reais** em toda a navegação.

### Prova
- **Barra de números** abaixo do hero: +20 anos exportando, AISI 304/316L,
  5 segmentos, projetos sob medida.
- **Seção Aplicações** com os cinco segmentos — que antes só apareciam soltos no
  meio de um parágrafo.

### SEO e compartilhamento
- Title e description mirando **"bomba centrífuga sanitária"** + localização —
  termo que o próprio blog de vocês já disputa.
- **Open Graph e Twitter Card**: o link agora aparece com imagem e descrição.
- **JSON-LD** de fabricante com endereço, telefones, e-mail e linha de produtos.
- `robots.txt`, `sitemap.xml` e **favicon** (o site não tinha nenhum).

### Acessibilidade
- Link de salto para o conteúdo e supressão dos vídeos para quem pede menos
  movimento no sistema.

---

## 2. Só depende de você — custo zero, maior retorno

Ordenado por impacto. Os quatro primeiros valem mais que qualquer vídeo novo.

| # | O que preciso | Por que vale |
|---|---|---|
| 1 | **Faixas técnicas por produto** — vazão (m³/h), pressão, temperatura, tipo de conexão, rotação | É a primeira coisa que engenheiro de processo procura. Sem isso ele sai e pede em outro lugar. Maior lacuna do site hoje. |
| 2 | **WhatsApp comercial** | No B2B industrial brasileiro é o canal que mais converte. Hoje não existe no site. |
| 3 | **Certificações** — ISO, 3-A, FDA, CE, o que houver | Destrava exportação e compra de multinacional. Se existe e não está no site, está sendo desperdiçado. |
| 4 | **Países atendidos** ou número de países | "Exporta há mais de 20 anos" é vago. "Exporta para 18 países" é prova. |
| 5 | **URLs das redes sociais** | Três ícones do rodapé são links mortos hoje. |
| 6 | **Domínio final do site** | `canonical` e `og:url` estão em `bombinox.com.br` e precisam casar com o endereço real antes de publicar. |
| 7 | **Logo em vetor** (`.ai`, `.svg` ou `.eps`) | Header e rodapé usam texto provisório. Existe `identidade/logo-simbolo-extraido.png` como referência para redesenho. |
| 8 | **Catálogo em PDF**, se existir | Vira isca de captura: download em troca do e-mail. |
| 9 | **Ano de fundação e tamanho da equipe** | Alimenta o JSON-LD e a página institucional. |

---

## 3. Para criar no Google Flow — vídeo

**Aviso honesto:** o hero já tem vídeo que funciona. Mais vídeo de IA rende
menos que os itens da seção 2. Se for gerar, gere estes:

### 🥇 Fundo da seção "Exportação Bombinox"
Hoje é só texto sobre fundo escuro. Um vídeo sutil por trás eleva muito a
percepção de porte.

```
Slow tracking shot moving forward through a spotless food-processing plant at
night, lit only by cool overhead work lights. Rows of polished stainless steel
tanks and sanitary piping line both sides, reflections travelling along the
metal. Dark, low-key lighting with deep shadows, cool neutral white balance, no
people. The camera moves forward at a slow constant speed, never stopping. The
scene is uniform along its whole length so the motion reads as endless — a
seamless loop. Photoreal industrial cinematography, crisp, organized, hygienic.
No text, no logos, no people.
```

> **Low-key é obrigatório.** A seção é escura; vídeo claro estoura o contraste e
> mata a leitura do texto.

### 🥈 Hero alternativo — "Fluxo em inox"
Para comparar com o atual. O conceito está detalhado em
`video-hero-briefing.md`, mas **regere em versão escura**:

```
Extreme close-up, shallow depth of field, dark low-key studio. Thick white cream
flows continuously through a polished stainless steel sanitary pipe with a clamp
fitting, a single hard rim light travelling along the wet metal. Deep shadows,
black background falling off to nothing, cool neutral white balance. The camera
holds a slow, steady dolly to the right, never stopping. The flow is constant
and unchanging from the first frame to the last — a seamless loop. Photoreal,
high-end industrial product cinematography, clean and hygienic. No text, no
logos, no people.
```

**Regras que valem para os dois:** 16:9, maior resolução do plano, terço
esquerdo calmo, sem texto/logo/pessoas, e **gere 4 a 6 variações** — a terceira
tentativa costuma ser muito melhor que a primeira com o mesmo prompt.

---

## 4. Para criar no Gemini — imagem

### 🥇 Imagem de compartilhamento dedicada (1200×630)
Hoje o link compartilhado usa o quadro do vídeo, que é 16:9 e não foi desenhado
para isso. Uma peça própria muda a percepção de quem recebe o link.

```
Industrial brand card, 1200x630, deep purple (#40217A) background with subtle
dark vignette. Left half: bold white uppercase sans-serif headline "BOMBEAMENTO
SANITÁRIO EM AÇO INOX" over a thin white rule, with smaller text "AISI 304 e
316L". Right half: a polished stainless steel sanitary centrifugal pump,
photoreal, dramatic rim lighting, cut out against the purple. Clean, technical,
high contrast, generous negative space. No extra text, no watermark.
```

Salvar em `site/assets/og-card.jpg` que eu ligo no `<meta property="og:image">`.

### 🥈 Cinco imagens de segmento — seção Aplicações
Os cards hoje têm só ícone e texto. Com imagem de ambiente a seção ganha peso.
São **ambientes**, não equipamento — zona segura para IA, sem risco de detalhe
técnico errado.

Um prompt por segmento, mesma base:

```
Photoreal industrial interior, [SEGMENTO], dark low-key lighting, polished
stainless steel surfaces and sanitary piping, spotless and organized, cool
neutral white balance, no people, no text, no logos, shallow depth of field,
premium editorial photography. 4:3.
```

Trocando `[SEGMENTO]` por: `dairy and food processing line` · `beverage bottling
line` · `cosmetics manufacturing clean room` · `pharmaceutical clean room` ·
`chemical processing plant`.

Salvar em `site/assets/segmentos/` como `alimentos.jpg`, `bebidas.jpg`,
`cosmeticos.jpg`, `farmaceutico.jpg`, `quimico.jpg`.

### O que **não** pedir para a IA
- **Logo vetorizado.** Modelo de imagem não vetoriza com fidelidade. Isso é
  trabalho de designer, redesenhando a partir de
  `identidade/logo-simbolo-extraido.png`.
- **Equipamento Bombinox específico.** Detalhe mecânico é onde a IA erra, e o
  comprador técnico repara. Para produto, foto real.

---

## 5. O que eu construo depois — por ordem de valor

| # | Entrega | Por que vale |
|---|---|---|
| 1 | **Versão em inglês** | A empresa exporta há mais de 20 anos e o site é só em português. Provavelmente a maior receita não capturada hoje. |
| 2 | **Três páginas de produto** | Cada uma mira uma palavra-chave que o blog de vocês já disputa. Hoje "Saiba mais" leva ao contato porque não há para onde levar. |
| 3 | **Tabela técnica por produto** | Depende do item 1 da seção 2. É o que faz o engenheiro pedir orçamento em vez de sair. |
| 4 | **Formulário de verdade + WhatsApp flutuante** | O `mailto:` atual funciona, mas formulário converte mais e permite medir. |
| 5 | **Blog com os artigos existentes** | O conteúdo já existe no site antigo e hoje está fora do ar novo. É tráfego orgânico parado. |
| 6 | **Página de aplicações por segmento** | Cinco páginas, cinco portas de entrada no Google. |
| 7 | **Analytics e medição de conversão** | Sem isso não dá para saber o que está funcionando. |

---

## 6. Decisão pendente que afeta a marca inteira

O logo real da Bombinox é **azul-marinho** (`#1E276D`), não roxo — medido no
símbolo extraído das fotos de produto, e confirmado pelo rodapé e pelos botões
do site atual de vocês.

O site inteiro está em roxo `#40217A`, que veio do Brand ID e lá mesmo estava
marcado como "aproximação visual, não spec oficial".

**Trocar é uma linha** — a variável `--roxo` alimenta a paleta toda. Mas é
decisão de marca, não de código: ou o site adota a cor real, ou a marca assume o
roxo como evolução deliberada. Ficar no meio é o único caminho ruim.
