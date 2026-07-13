---
name: carrossel-instagram-generator
description: Use SEMPRE que o usuário mencionar carrossel Instagram, carrossel viral, carrossel educativo, post em slides, slide deck para Instagram, conteúdo em carrossel, post carrossel, fazer carrossel, gerar carrossel, criar carrossel, carrossel de vendas, carrossel de autoridade, mini ebook Instagram, conteúdo dividido em slides, post de 10 slides, deck para redes sociais, ou pedir estrutura de carrossel. Esta skill gera carrosséis de 8 a 10 slides com estrutura viral comprovada (hook, problema, consequência, valor, recap, CTA) prontos para postar, incluindo sugestões visuais para integração com Mirra MCP ou Nano Banana.
---

# Carrossel Instagram Generator

## Quando usar

Ative esta skill SEMPRE que o usuário pedir:
- "Faz um carrossel sobre X"
- "Quero um post em slides sobre Y"
- "Gera conteúdo de Instagram em carrossel"
- "Preciso de um deck viral para o Insta"
- "Como estruturar um carrossel educativo / de vendas / de autoridade"
- "Transforma esse texto / artigo / aula em carrossel"

Também ative quando o contexto for marketing de conteúdo orgânico, growth Instagram, infoprodutores, criadores, consultores, agências, ou quando o objetivo for engajamento (salvamentos, comentários, compartilhamentos).

## O que esta skill faz

Esta skill gera um carrossel de Instagram de **8 a 10 slides** seguindo a estrutura viral validada pelos maiores criadores do Brasil (Ícaro de Carvalho, Erico Rocha, Pedro Sobral, Bruno Perini, Diego Maia). A estrutura é:

| Slide | Função | Objetivo psicológico |
|-------|--------|----------------------|
| 1 | HOOK / Promessa | Parar o scroll, gerar curiosidade |
| 2 | Problema do leitor | Espelhar a dor, criar identificação |
| 3 | Consequência de não resolver | Amplificar urgência |
| 4-8 | Conteúdo de valor | Entregar a promessa (listas, frameworks, passos, exemplos) |
| 9 | Recapitulação visual | Facilitar o salvamento |
| 10 | CTA (salve, comente, perfil) | Converter engajamento |

Para CADA slide, a skill entrega:
- **Título** (máx. 6 palavras, alto contraste visual)
- **Texto principal** (máx. 30 palavras — caber bem no celular)
- **Sugestão visual** (descrição pronta para Mirra MCP, Nano Banana ou designer)
- **Observação de design** (cor de destaque, ícone, mood)

## Como usar (passo a passo)

1. **Coletar input do usuário**:
   - Tema central do carrossel
   - Público-alvo (nicho, dor principal)
   - Tom de voz (educativo, polêmico, comercial, inspiracional)
   - Objetivo (salvamentos, vendas, autoridade, lista)
   - Brand book (se houver — checar skill `brandbook-prompt-system`)

2. **Validar promessa do Slide 1**:
   - A promessa precisa ser específica, numérica e tangível
   - Evite "dicas para crescer" → use "7 erros que travam contas de 0 a 10k"

3. **Mapear o problema (Slide 2) e a consequência (Slide 3)**:
   - Problema: o que o leitor sente HOJE
   - Consequência: o que vai acontecer se ele continuar assim em 6/12 meses

4. **Estruturar o valor (Slides 4-8)** usando UM destes formatos:
   - Lista numerada (5 erros, 7 passos, 4 frameworks)
   - Antes vs Depois
   - Mito vs Verdade
   - Passo a passo cronológico
   - Framework com sigla (ex: método AIDA, PASTOR, AAA)

5. **Slide 9 (recap)**: lista curta dos pontos para o leitor SALVAR.

6. **Slide 10 (CTA)**: SEMPRE três ações:
   - Salve este post para não esquecer
   - Comente "X" se quiser o material complementar
   - Siga @perfil para mais conteúdo assim

7. **Gerar prompts visuais** para Mirra MCP / Nano Banana, um por slide.

## Formato de saída

```markdown
# CARROSSEL: [Título do tema]

**Público:** [nicho]
**Objetivo:** [salvamentos / vendas / autoridade]
**Tom:** [educativo / polêmico / comercial]

---

## SLIDE 1 — HOOK
**Título:** [6 palavras max]
**Texto:** [30 palavras max]
**Visual:** [prompt para Mirra/Nano Banana]
**Design:** [cor de destaque, ícone, mood]

## SLIDE 2 — PROBLEMA
[mesmo formato]

## SLIDE 3 — CONSEQUÊNCIA
[mesmo formato]

## SLIDES 4-8 — VALOR
[mesmo formato, com numeração interna]

## SLIDE 9 — RECAP
[mesmo formato]

## SLIDE 10 — CTA
[mesmo formato]

---

## LEGENDA DO POST (caption)
[200-400 caracteres, com 1 hook + 1 CTA + 5-10 hashtags estratégicas]

## HASHTAGS SUGERIDAS
[8-15 hashtags mix de volume alto/médio/nicho]

## MELHOR HORÁRIO DE POSTAGEM
[baseado no nicho do usuário — ver skill instagram-automation]
```

## Exemplos práticos

### Exemplo 1 — Tema: "Erros em tráfego pago para infoprodutores"

**SLIDE 1 — HOOK**
- Título: "7 erros que queimam seu budget"
- Texto: "Se você gasta R$ 100/dia em Meta Ads e não escala, provavelmente está cometendo pelo menos 4 destes 7 erros."
- Visual: "Smartphone com gráfico em queda vermelho, fundo escuro, neon roxo, estilo cinematográfico"
- Design: vermelho de alerta + branco

**SLIDE 2 — PROBLEMA**
- Título: "Você investe e não vende"
- Texto: "Sobe campanha, gasta R$ 500, recebe 2 leads frios. O ROAS não fecha. A culpa não é do algoritmo."

**SLIDE 3 — CONSEQUÊNCIA**
- Título: "Em 90 dias você quebra"
- Texto: "Quem queima budget sem método chega no terceiro mês descapitalizado e culpando o Meta. Vamos resolver isso."

(Slides 4-8: 5 erros específicos com solução cada)

**SLIDE 9 — RECAP**
- Título: "Salve para revisar"
- Texto: "1. Sem pixel ok  2. Público amplo demais ok  3. Criativo único ok  4. Sem teste ABO/CBO ok  5. Sem funil ok"

**SLIDE 10 — CTA**
- Título: "Quer auditoria gratuita?"
- Texto: "Comente AUDITORIA e mando um checklist com 23 pontos. Salve este post e siga @perfil para mais."

### Exemplo 2 — Tema: "Como cobrar mais como consultor"

(estrutura idêntica adaptada ao tema)

## Limitações / Quando NÃO usar

- **Não use** para posts de feed estático único (use skill de copy de post simples)
- **Não use** para reels ou vídeos (use skill `veo-videos`)
- **Não use** para temas sem promessa clara — carrossel sem hook morre
- **Não use** se o usuário quer mais de 10 slides (Instagram limita; sugerir dividir em 2 carrosséis)
- **Cuidado** com nichos regulados (saúde, financeiro, jurídico) — sempre adicionar disclaimer

## Integração com outras skills do ZION

- `nano-banana-criativos` — gerar imagens de cada slide
- `instagram-automation` — agendar e postar
- `brandbook-prompt-system` — aplicar identidade visual
- `manychat-claude-dm` — responder DMs gerados pelo CTA
- `trafego-pago-auditor` — se for carrossel sobre ads, validar dados
