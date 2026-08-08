# Estratégia

> O que importa agora. Prioridades, metas, prazos.
> O Claude usa isso pra decidir o que sugerir primeiro e o que adiar.

## Fase

Construção da presença digital. O Brand ID visual já está consolidado
(`identidade/design-guide.md`); a execução começa pelo site.

## Prioridade principal

**Construir o site da Bombinox.**

Método definido com o usuário:

- O usuário envia prints de referência de layout
- Cada print é reproduzido fielmente — estrutura, proporção, hierarquia,
  espaçamento e comportamento
- A pele é trocada pela identidade Bombinox: roxo `#40217A` no lugar da cor de
  destaque da referência, tipografia e formas conforme o design guide
- Conteúdo genérico da referência (foto de banco, logo de terceiro, lorem)
  vira equivalente Bombinox

**Stack:** HTML + CSS estático, sem build, fonte via Google Fonts (Montserrat).
Escolhido por permitir bater o layout dos prints mais rápido e abrir direto no
navegador.

**Ritmo de trabalho:** o usuário pediu explicitamente para não ser
entrevistado com muitas perguntas. Executar com o contexto disponível, assumir
o padrão sensato e sinalizar a suposição — em vez de bloquear pedindo
confirmação.

## O que pode esperar

- Preenchimento das pendências de contexto em `_memoria/empresa.md`
  (equipe, ferramentas, ticket, canais)
- Calibração do tom de voz com amostra de escrita real
- Conteúdo de marketing (carrossel, campanha, SEO) — depois do site

## Contexto com prazo

*(nenhum prazo informado)*

---

## Bloqueios ativos

**Assets da marca ausentes.** Dois itens travam a fidelidade visual do site e
precisam vir do usuário:

1. **Arquivo do logo** — `.svg` ou `.png`, mais a versão para fundo escuro se
   existir. Destino: `identidade/logo.svg` / `identidade/logo.png`
2. **Fotos reais dos equipamentos** — bombas, válvulas, conexões,
   misturadores, em inox

Enquanto não chegarem, usar placeholders explicitamente marcados. Não
substituir por foto de banco genérica: viola a direção fotográfica da marca.

## Candidatas a virar skill

Ainda não mapeadas — o usuário não informou qual tarefa repete toda semana.
Rodar `/mapear-rotinas` quando fizer sentido.

---

## Histórico de decisões

- **Workspace achatado.** O MazyOS foi instalado na raiz do repositório
  `JoaoGobatto/bombinox` em vez de ficar numa subpasta com git próprio.
  Workspace, identidade da marca e site vivem num repo só, com push
  funcionando. (Opção A, escolhida pelo usuário.)
