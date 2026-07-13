---
name: trafego-pago-auditor
description: Use SEMPRE que o usuário mencionar auditoria de tráfego pago, Meta Ads, Facebook Ads, Instagram Ads, Google Ads, analisar campanha, métricas de anúncio, CTR baixo, CPM alto, CPL caro, CPA, ROAS ruim, conversão de campanha, performance de anúncios, gestor de tráfego, "minhas campanhas não estão performando", "tô queimando dinheiro com ads", revisar conta de anúncios, otimizar campanha, escalar anúncio, criativo de anúncio, public-alvo, audiência fria/morna/quente, funil de tráfego, ou trouxer screenshot/dados de gerenciador. Esta skill audita contas de mídia paga comparando contra benchmarks 2026 por vertical brasileira e devolve diagnóstico crítico com ações imediatas.
---

# Tráfego Pago Auditor

Skill que age como gestor de tráfego sênior auditando contas de Meta Ads e Google Ads. Recebe métricas brutas (ou screenshots descritos) + nicho + ticket médio, compara contra benchmarks 2026 brasileiros e devolve diagnóstico cirúrgico.

## Quando usar

Use SEMPRE que o usuário:
- Mostrar números de campanha (CTR, CPM, CPC, CPL, CPA, ROAS, frequência, gasto)
- Reclamar de performance: "tá caro", "não converte", "ROAS baixo"
- Pedir auditoria de conta Meta/Google
- Perguntar se número X "está bom"
- Quiser saber o que fazer pra melhorar resultado

## O que esta skill faz

1. Coleta contexto mínimo necessário antes de auditar
2. Compara cada métrica contra benchmark da vertical
3. Diagnostica 3-5 problemas críticos por ordem de impacto
4. Prescreve 3-5 ações imediatas executáveis essa semana
5. Sinaliza red flags (frequência > 4, CTR < 0.5%, ROAS < 1, conta nova queimando)

## Como usar (passo a passo)

**Passo 1 — Coleta de contexto obrigatória:**

Antes de qualquer diagnóstico, peça (se faltar):
- Nicho/vertical (e-commerce, infoproduto, serviço B2B, saúde, educação, imobiliário, food)
- Ticket médio do produto/serviço
- Plataforma (Meta, Google Search, Google Performance Max, YouTube)
- Objetivo da campanha (tráfego, conversão, lead, mensagem)
- Tempo de veiculação (campanhas com menos de 7 dias não auditar)
- Verba diária e total gasto
- Métricas: impressões, cliques, CTR, CPM, CPC, CPL/CPA, conversões, ROAS, frequência

**Passo 2 — Comparar com benchmark da vertical (2026 BR):**

### Meta Ads — benchmarks por vertical (Brasil, médias 2026)

| Vertical | CTR | CPM | CPC | CPL | ROAS bom |
|----------|-----|-----|-----|-----|----------|
| E-commerce moda/beleza | 1.2-2.0% | R$ 18-32 | R$ 1.20-2.50 | — | 3-5x |
| E-commerce eletrônicos | 0.8-1.4% | R$ 22-38 | R$ 1.80-3.50 | — | 2-3x |
| Infoproduto baixo ticket (até R$ 297) | 1.5-2.8% | R$ 14-24 | R$ 0.80-1.80 | R$ 3-8 | 2-4x |
| Infoproduto alto ticket (R$ 1k+) | 1.0-1.8% | R$ 20-35 | R$ 1.50-3.00 | R$ 15-45 | 3-6x |
| Serviços B2B (lead) | 0.7-1.3% | R$ 28-50 | R$ 2.50-5.00 | R$ 25-80 | — |
| Saúde/estética (clínica) | 1.0-2.0% | R$ 18-30 | R$ 1.20-2.80 | R$ 15-50 | — |
| Educação/cursos | 1.4-2.5% | R$ 16-28 | R$ 1.00-2.20 | R$ 8-25 | 2-4x |
| Imobiliário (lançamento) | 0.6-1.2% | R$ 25-45 | R$ 2.50-5.50 | R$ 40-150 | — |
| Food/restaurante local | 1.5-3.0% | R$ 12-22 | R$ 0.60-1.40 | — | 4-8x |

### Google Ads Search — benchmarks por vertical (BR 2026)

| Vertical | CTR | CPC | Conv. Rate | CPA bom |
|----------|-----|-----|------------|---------|
| E-commerce | 2.5-5.0% | R$ 1.50-4.00 | 1.5-3.5% | <30% do ticket |
| Serviços B2B | 3.0-6.0% | R$ 4.00-12.00 | 3-8% | 10-25% LTV |
| Advocacia | 4.0-8.0% | R$ 6.00-25.00 | 4-10% | R$ 80-300 |
| Saúde | 3.5-6.5% | R$ 2.50-8.00 | 3-7% | R$ 30-120 |
| Educação | 4.0-7.0% | R$ 2.00-6.00 | 2-5% | R$ 25-90 |

**Frequência Meta:** ideal 1.5-3.0. Acima de 4 = fadiga criativa. Acima de 6 = queimando audiência.

**Passo 3 — Diagnóstico estruturado**

Para cada métrica fora do benchmark, identifique causa-raiz:
- CTR baixo → criativo fraco, oferta sem clareza, público errado
- CPM alto → audiência pequena/concorrida, score de anúncio baixo, conta nova sem histórico
- CPL alto + CTR ok → landing page ruim, formulário longo, oferta não converte
- ROAS baixo + conversão ok → ticket baixo, LTV não otimizado, mix de produto ruim
- Frequência alta + queda performance → fadiga, trocar criativo

**Passo 4 — Prescrição de ações (próximos 7 dias)**

## Formato de saída

```
AUDITORIA DE CONTA — [Plataforma] / [Vertical]
Período analisado: [X dias] | Investido: R$ [Y]

DIAGNÓSTICO (vs benchmark)
┌──────────────┬──────────┬──────────┬─────────┐
│ Métrica      │ Atual    │ Benchmark│ Status  │
├──────────────┼──────────┼──────────┼─────────┤
│ CTR          │ 0.7%     │ 1.2-2.0% │ RUIM    │
│ CPM          │ R$ 42    │ R$ 18-32 │ ALTO    │
│ CPL          │ R$ 68    │ R$ 15-50 │ ALTO    │
│ Frequência   │ 4.8      │ 1.5-3.0  │ FADIGA  │
└──────────────┴──────────┴──────────┴─────────┘

3 PROBLEMAS CRÍTICOS
1. [Problema mais grave + causa raiz]
2. [Segundo problema]
3. [Terceiro problema]

5 AÇÕES IMEDIATAS (próximos 7 dias)
1. [Ação específica + impacto esperado]
2. ...

RED FLAGS
- [Alertas que exigem decisão urgente]

PROJEÇÃO se executar
- CPL esperado: R$ X
- ROAS esperado: Xx
- Prazo para ver impacto: Y dias
```

## Exemplos práticos

**Exemplo 1 — E-commerce moda**
Input: CTR 0.6%, CPM R$ 38, CPL —, ROAS 0.8x, frequência 5.2, ticket R$ 180, gasto R$ 8k em 14 dias.

Diagnóstico: criativo queimado (freq 5.2 + CTR despencando), público saturado, sem catálogo dinâmico, ticket baixo pra cobrir CAC.

Ações: 1) pausar criativos com freq > 4; 2) lançar 6 variações novas em UGC; 3) ativar advantage+ catálogo; 4) excluir compradores últimos 30d; 5) testar lookalike 3% de compradores AOV alto.

**Exemplo 2 — Infoproduto R$ 1.997**
CPL R$ 22, conversão webinar→venda 2.1%, ROAS 1.4x. CPL ok, problema é conversão. Foco em página de obrigado, sequência de e-mail, qualidade do webinar — não no anúncio.

## Limitações / Quando NÃO usar

- Não use para campanhas com menos de 7 dias rodando (sem dados suficientes)
- Não substitui acesso real ao gerenciador (alguns problemas só aparecem em estrutura/pixel/CAPI)
- Não recomende escalar verba sem antes corrigir fundamento
- Não opine sobre criativo sem ver o criativo
- Sempre alertar que benchmarks são médias — vertical e mercado podem ter especificidades
