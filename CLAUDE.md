# MazyOS — Sistema operacional do negócio

Sua empresa roda em cima desse arquivo. Aqui ficam as regras de operação
do MazyOS — como o Claude lê o contexto, aprende com correções, mantém
tudo atualizado e cria skills novas conforme a operação evolui.

Esse arquivo é editável. Quando o `/instalar` rodar, ele complementa o
final dessa página com as regras específicas do seu negócio.

---

## Contexto do negócio

No início de toda conversa, ler os seguintes arquivos (quando existirem
e estiverem preenchidos):

1. `_memoria/empresa.md` — quem é o usuário, o que faz, como funciona o negócio
2. `_memoria/preferencias.md` — tom de voz, estilo de escrita, o que evitar
3. `_memoria/estrategia.md` — foco atual, prioridades, prazos

Usar essas informações como base pra qualquer resposta ou decisão. Ao
sugerir prioridades, formatos ou abordagens, considerar o foco atual
descrito em `estrategia.md`.

Pra qualquer tarefa visual (carrossel, post, landing page), consultar
`identidade/design-guide.md` como referência de estilo.

Não é necessário listar o que foi lido nem confirmar a leitura. Apenas
usar o contexto naturalmente.

---

## Fluxo de trabalho

Antes de executar qualquer tarefa, verificar se existe skill relevante
em `.claude/skills/`. Se encontrar, seguir as instruções da skill. Se
não encontrar, executar a tarefa normalmente.

Ao concluir uma tarefa que não tinha skill mas parece repetível (o
usuário provavelmente vai pedir de novo no futuro), perguntar:

> "Isso pode virar uma skill pra próxima vez. Quer que eu crie?"

Não perguntar pra tarefas pontuais ou perguntas simples. Só quando o
padrão de repetição for claro.

---

## Aprender com correções

Quando o usuário corrigir algo, melhorar uma resposta ou dar uma
instrução que parece permanente (frases como "na verdade é assim", "não
faça mais isso", "prefiro assim", "sempre que...", "evita...", "da
próxima vez..."), perguntar:

> "Quer que eu salve isso pra não precisar repetir?"

Se sim, identificar onde faz mais sentido salvar:

- **Sobre o negócio** (clientes, serviços, mercado) → `_memoria/empresa.md`
- **Sobre preferências e estilo** (tom de voz, formato, o que evitar) → `_memoria/preferencias.md`
- **Sobre prioridades e foco** (projetos, metas, prazos) → `_memoria/estrategia.md`
- **Regra de comportamento nessa pasta** → próprio `CLAUDE.md`

Salvar com uma linha nova clara, sem reformatar o arquivo inteiro.
Confirmar mostrando a linha adicionada.

Não perguntar se a correção for óbvia de contexto imediato (ex: "na
verdade o arquivo se chama X"). Só perguntar quando a informação tiver
valor duradouro.

---

## Manter contexto atualizado

Ao terminar uma tarefa que mudou algo relevante (cliente novo, skill
nova, mudança de foco, processo novo, ferramenta instalada, estrutura
alterada), perguntar:

> "Isso mudou algo no teu contexto. Quer que eu atualize a memória?"

Se sim, identificar o que atualizar:

- **Cliente, serviço, ferramenta, equipe** → `_memoria/empresa.md`
- **Mudança de prioridade ou foco** → `_memoria/estrategia.md`
- **Tom ou estilo** → `_memoria/preferencias.md`
- **Pasta, regra de organização, skill criada** → `CLAUDE.md`
- **Visual (cores, fontes, logo)** → `identidade/design-guide.md`

Mostrar o que vai mudar antes de salvar. Não reformatar o arquivo
inteiro, só adicionar ou editar a linha relevante.

**Quando NÃO perguntar:**
- Tarefas pontuais sem impacto no contexto (escrever um email avulso, criar um post)
- Perguntas simples ou conversas sem ação
- Mudanças já salvas pelo bloco "Aprender com correções"

**Dica:** rode `/atualizar` pra uma varredura completa quando houver dúvida.

---

## Criação de skills

Quando o usuário pedir skill nova:

1. Verificar se existe template relevante em `templates/skills/`. Se
   existir, usar como base e adaptar pro contexto
2. Perguntar se é específica desse projeto ou útil em qualquer:
   - Específica → `.claude/skills/nome-da-skill/SKILL.md` (local)
   - Universal → `~/.claude/skills/nome-da-skill/SKILL.md` (global)
3. Ler `_memoria/empresa.md` e `_memoria/preferencias.md` pra calibrar
   o conteúdo da skill ao contexto do negócio
4. Se a skill precisar de arquivos de apoio (templates, exemplos),
   criar dentro da pasta da skill
5. Seguir o fluxo da skill-creator nativa do Claude Code

---
---

# Bombinox — regras do negócio

> Aplicado pelo `/instalar` com o perfil **Empresa**.

## O que é esse workspace

Operação da Bombinox. Aqui ficam a memória do negócio, a identidade da marca e
tudo que o sistema produz — a começar pelo site.

O MazyOS foi instalado **na raiz** do repositório `JoaoGobatto/bombinox`, não
numa subpasta. Workspace, marca e site vivem num repo só.

**Estrutura de pastas:**
- `_memoria/` — quem é a empresa, como falamos, foco atual
- `identidade/` — marca aplicada em tudo que o sistema gera
- `marketing/` — campanhas, conteúdo, mídia paga
- `saidas/` — documentos pontuais
- `dados/` — arquivos a analisar
- `templates/` — moldes de perfil e de skills
- `scripts/` — utilitários
- `site/` — código do site institucional

Pastas de setor (`comercial/`, `financeiro/`, `rh/`, `operacoes/`, `projetos/`)
ainda não existem — criar sob demanda, na primeira vez que forem usadas, em vez
de deixar pasta vazia na raiz.

## Sobre a empresa

Bombinox é uma **indústria** — fabricante de equipamentos em aço inoxidável.
Produto principal: bombas centrífugas sanitárias. Portfólio complementar:
válvulas, conexões, misturadores e projetos especiais.

Atende alimentos, bebidas, cosméticos e farmacêutico — aplicações sanitárias
onde o equipamento tem contato com o produto. Material: AISI 304 e 316L
conforme a aplicação.

Tamanho da equipe e divisão em setores ainda não foram informados (ver
pendências em `_memoria/empresa.md`).

## O que mais fazemos aqui

- Site institucional — **frente ativa no momento**
- Conteúdo e campanhas de marketing
- Materiais comerciais e técnicos de produto

## Tom de voz

Técnico, direto e confiável. A autoridade vem da especificação, não do
superlativo. Ordem padrão: **especificação → aplicação → benefício**.

Evitar: superlativo vazio, marketês ("alavancar", "sinergia", "vamos juntos!"),
"caro cliente", emoji em comunicação comercial, promessa sem número, tom de
varejo. Detalhe completo em `_memoria/preferencias.md`.

## Regras do sistema

- **Todo output visual consulta `identidade/design-guide.md` antes de ser
  criado.** Roxo `#40217A` + branco + inox + geometria circular + sans-serif em
  caixa alta. Sem exceção.
- **Nunca usar foto de banco genérica** para representar equipamento. Sem foto
  real da Bombinox, usar placeholder explicitamente marcado — foto genérica
  viola a direção fotográfica da marca.
- **Ao reproduzir print de referência:** copiar estrutura, proporção,
  hierarquia e espaçamento fielmente; trocar a pele pela identidade Bombinox.
  Conteúdo genérico da referência vira equivalente Bombinox.
- **Não entrevistar o usuário.** Ele pediu explicitamente poucas perguntas.
  Executar com o contexto disponível, assumir o padrão sensato e sinalizar a
  suposição — em vez de bloquear pedindo confirmação. Perguntar só quando
  proceder de qualquer jeito inviabilizaria o trabalho.
- Site em HTML + CSS estático, sem build, Montserrat via Google Fonts
- Documentos pontuais em `saidas/`

## Ferramentas conectadas

- [ ] Notion
- [ ] Gmail
- [ ] Google Calendar
- [ ] Google Ads
- [ ] Meta Ads
- [ ] Slack

*(Marcar conforme for instalando os MCPs)*
