# Briefing — vídeo de fundo do hero

Para gerar no Google Flow (Veo). Escrito depois de pesquisar referências de
hero com vídeo e a documentação de prompting do Veo.

---

## 1. Por que o vídeo do desmonte não funcionou

Quatro motivos independentes. Vale entender antes de gerar o próximo, porque
três deles se repetem em qualquer vídeo com a mesma estrutura.

**A mensagem é o contrário da que vendemos.** A Bombinox vende robustez,
durabilidade e confiança. Um equipamento se desmontando sozinho comunica o
oposto, mesmo que a intenção seja mostrar engenharia.

**A estrutura não permite loop.** O vídeo tem começo e fim — sai de montado e
chega em desmontado. Todo formato de repetição esbarra nisso: o loop nativo
corta seco, o vai-e-volta remonta a bomba de trás para frente, e a versão que
congela no fim deixa a peça desmontada em tela para sempre. Não é problema de
implementação, é da narrativa.

> A documentação do Veo é explícita: para um vídeo repetir bem, ele precisa
> estar em **estado estável** — movimento contínuo que não constrói nem resolve
> nada. Chuva caindo, fogo tremendo, água correndo. Nada que tenha clímax.

**É onde a IA erra mais.** Modelo de vídeo acerta fluido, luz e textura;
erra montagem mecânica precisa — rosca, flange, conexão sanitária, vedação.
Comprador técnico repara. Num fabricante que vende por especificação, detalhe
mecânico errado custa credibilidade.

**A bomba não é nossa.** O equipamento do vídeo não é um produto Bombinox.

---

## 2. O princípio que resolve

> Gerar o que a IA faz bem **e** que também é verdade sobre a Bombinox.

| A IA acerta | A IA erra |
|---|---|
| líquido, fluxo, viscosidade, respingo | montagem mecânica precisa |
| luz, reflexo, brilho no metal | rosca, flange, conexão sanitária |
| macro de textura — inox escovado, condensação | texto, logo, manômetro com número |
| movimento lento e contínuo de câmera | mão humana em tarefa precisa |
| vapor, partícula, gota | manter um produto específico coerente |

A sorte é que as duas listas se resolvem sozinhas aqui: **a Bombinox move
fluido**. Bombeamento sanitário é literalmente líquido em movimento dentro de
inox — exatamente a zona forte do modelo, e exatamente o que a empresa faz.
Não é contorno, é o assunto certo.

---

## 3. Conceitos, em ordem de recomendação

### 🥇 1. Fluxo em inox — **recomendado**

Macro de creme branco correndo dentro de tubulação sanitária polida, luz
batendo na superfície. Fluxo constante.

- **Por que:** é o produto em ação sem mostrar o produto. Fluido + inox +
  higiene, os três pilares da marca.
- **Loop:** perfeito. Fluxo é estado estável por definição.
- **Risco:** baixo. Nenhuma mecânica complexa em quadro.

### 🥈 2. Superfície de inox com luz viajando

Macro extremo de inox espelhado, faixa de luz suave atravessando devagar,
revelando o grão do metal.

- **Por que:** abstrato, premium, e coloca o material da marca em primeiro
  plano. Deixa o texto do hero respirar.
- **Loop:** perfeito.
- **Risco:** praticamente zero — não há nada técnico para errar.
- **Contra:** não mostra produto nem processo.

### 🥉 3. Rotor girando

Close no rotor polido girando dentro da carcaça aberta, pás pegando luz.

- **Por que:** círculo é a geometria central da marca — o próprio logo é um
  rotor estilizado.
- **Loop:** bom. Rotação é estado estável.
- **Risco:** médio. O modelo pode inventar um rotor implausível.

### 4. Vórtice em tanque

Plano de cima, líquido branco girando devagar em tanque de inox espelhado.

- **Por que:** de novo a geometria circular, e lê como processo alimentício.
- **Loop:** ótimo. Câmera parada, só o líquido gira.
- **Risco:** baixo.

### 5. Condensação em inox

Macro de gotas escorrendo em inox escovado.

- **Por que:** frio, limpo, asséptico. Ótimo para **outras seções**, não para o
  hero — é atmosfera, não assunto.
- **Loop:** ótimo. **Risco:** baixo.

### 6. Travelling pela planta

Câmera avançando devagar por uma planta de processamento limpa, tanques e
tubulação de inox dos dois lados.

- **Por que:** mostra escala e contexto industrial.
- **Loop:** exige cenário uniforme ao longo do percurso.
- **Risco:** o mais alto da lista. Tubulação inventada, em plano aberto, é onde
  o modelo mais escorrega.

---

## 4. Prompts prontos

Escritos em inglês — o Veo responde melhor. Seguem a estrutura de 5 partes que
a documentação recomenda (composição, sujeito/ação, ambiente, câmera, estilo) e
todos terminam reforçando estado estável e `seamless loop`.

### 1. Fluxo em inox

```
Extreme close-up, shallow depth of field. Thick white cream flows continuously
through a polished stainless steel sanitary pipe with a clamp fitting, the
liquid catching soft highlights as it moves. The surrounding surfaces are
brushed and mirror-polished stainless steel, spotlessly clean, with fine
condensation. Bright, even studio lighting from the upper left, cool neutral
white balance, no colored gels. The camera holds a slow, steady dolly to the
right, never stopping, never arriving. The flow is constant and unchanging from
the first frame to the last — no beginning, no end, a seamless loop. Photoreal,
high-end industrial product cinematography, crisp detail on the metal grain,
clean and hygienic mood. No text, no logos, no people.
```

### 2. Superfície de inox

```
Macro shot of a mirror-polished stainless steel surface filling the frame, fine
circular brush grain visible. A soft band of white light travels slowly and
continuously across the metal, revealing the texture as it passes. Faint
reflections of a bright clean room drift in the polish. Neutral cool white
balance, no color casts. The camera performs a slow continuous lateral drift at
constant speed, never stopping. Nothing builds, nothing resolves — the motion is
a steady state that could continue forever, a seamless loop. Photoreal, high-end
product cinematography, extremely clean, hygienic and precise. No text, no
logos, no people, no visible machinery.
```

### 3. Rotor girando

```
Close-up of a polished stainless steel centrifugal impeller spinning steadily
inside an open sanitary pump housing, curved vanes catching soft highlights as
they rotate. Clean brushed metal surfaces surround it, spotless, faint
condensation. Bright even studio lighting, cool neutral white balance. The
camera holds a slow, steady orbit around the impeller at constant speed. The
rotation is continuous and unchanging — no start-up, no slow-down, a seamless
loop. Photoreal industrial cinematography, crisp metal detail, clean and
technical mood. No text, no logos, no people.
```

### 4. Vórtice em tanque

```
Overhead close-up of a clean stainless steel vessel. Thick white liquid turns in
a slow steady vortex, the surface catching soft highlights as it rotates.
Mirror-polished walls surround the liquid. Bright even lighting, cool neutral
white balance. The camera holds still directly above, only the liquid moves. The
rotation is constant from the first frame to the last — a seamless loop.
Photoreal, high-end food-processing cinematography, hygienic and precise. No
text, no logos, no people.
```

### 5. Condensação

```
Extreme macro of condensation beading and running slowly down a brushed
stainless steel surface. Droplets catch bright highlights, the metal grain
visible behind them. Bright even studio lighting, cool neutral white balance.
The camera drifts upward very slowly at constant speed. Continuous and
unchanging — a seamless loop. Photoreal, clean, hygienic and cold. No text, no
logos, no people.
```

### 6. Travelling pela planta

```
Slow tracking shot moving forward through a spotless food-processing plant. Rows
of polished stainless steel tanks and sanitary piping line both sides, bright
and clean. Even overhead lighting, cool neutral white balance. The camera moves
forward at a slow constant speed, never stopping, never arriving anywhere. The
scene is uniform along its whole length so the motion reads as endless — a
seamless loop. Photoreal industrial cinematography, crisp, organized, hygienic.
No text, no logos, no people.
```

---

## 5. Regras de geração

**Enquadramento.** O texto do hero ocupa a metade esquerda. Manter o terço
esquerdo calmo — fundo, superfície lisa, área sem detalhe. O assunto vive do
centro para a direita.

**Claro, não escuro.** O hero hoje é claro: headline em grafite sobre lavagem
branca. Vídeo claro encaixa direto. Se você trouxer um vídeo escuro e dramático
funciona também, mas aí eu preciso inverter o hero para texto branco — me avise
antes, não é ajuste de uma linha.

**Sem texto, sem logo, sem pessoas.** Texto e logo o modelo escreve errado.
Pessoa exige mão e rosto, onde ele mais falha — e a direção fotográfica pede
técnico em roupa de trabalho, difícil de acertar.

**Formato.** 16:9, na maior resolução que o plano oferecer. O vídeo atual é 720p
e fica suave em monitor grande; 1080p resolve.

**Gere de 4 a 6 variações por conceito.** Vídeo de IA tem alta variância — a
terceira tentativa costuma ser muito melhor que a primeira, com o mesmo prompt.

---

## 6. O que eu faço depois que você gerar

Tenho ffmpeg completo disponível, então me manda o arquivo bruto que eu cuido de:

- **emenda do loop** — crossfade nos últimos quadros, se o corte ficar visível
- **reenquadramento** — crop e reposicionamento para o assunto cair à direita
- **velocidade** — acelerar ou desacelerar
- **compressão** — alvo de 1,5 a 2,5 MB, sem perda visível
- **poster** — extração do primeiro quadro
- **correção de cor** — neutralizar dominante para bater com a paleta

Sobe em `site/assets/` pelo GitHub, como você fez com as fotos dos produtos.

---

## 7. Uma alternativa que vale considerar

Nenhum vídeo gerado por IA vai bater, em credibilidade, meia hora de filmagem
real dentro da fábrica. Um celular num estabilizador rendendo planos de bomba em
operação, tubulação, solda, acabamento — material que **é** a Bombinox, sem
risco de detalhe técnico errado e sem a questão de mostrar equipamento de
terceiro.

Não precisa escolher: a IA resolve o hero agora, a filmagem real substitui
quando existir. Mas vale colocar na fila.

---

## 8. Bônus — o desmonte tem um lugar certo

O vídeo que você já gerou não serve como fundo em loop, mas serve muito bem em
**scroll-scrub**: a posição do vídeo amarrada à rolagem da página. A pessoa
rola, a bomba desmonta; rola de volta, ela remonta. É a técnica que a Apple usa
nas páginas de produto.

Repare que ali o problema vira qualidade: um vídeo com começo e fim é
exatamente o que o scroll-scrub precisa, porque quem controla a linha do tempo é
o visitante, não o autoplay.

Caberia bem numa seção de produto ou numa página "Dados técnicos" — não no hero.
Custa mais para implementar e exige cuidado com desempenho no celular, mas o
material já existe. Vale guardar a ideia.

---

## Fontes

- [How to Make Seamless Looping Videos with Veo 3](https://www.veo3ai.io/blog/veo-3-seamless-looping-video-guide-2026)
- [Veo 3.1 Prompting Guide — VEED](https://www.veed.io/learn/veo-3-1-prompts)
- [Veo 3.1 Prompting Guide — Invideo](https://invideo.io/blog/google-veo-prompt-guide/)
- [Veo 3 Prompt Guide — Leonardo.Ai](https://leonardo.ai/news/mastering-prompts-for-veo-3)
- [30 hero section examples from real websites — Marketer Milk](https://www.marketermilk.com/blog/hero-section-examples)
- [Best Hero Video Websites — Webflow](https://webflow.com/made-in-webflow/hero-video)
- [Inspiring Websites with Video Backgrounds — Muffin Group](https://muffingroup.com/blog/websites-with-video-backgrounds/)
- [The 10 best manufacturing website designs — Blend B2B](https://www.blendb2b.com/resources/best-manufacturing-website-designs)
- [11 Best Industrial Website Design Examples — Thomas](https://blog.thomasnet.com/best-industrial-website-design-examples)
