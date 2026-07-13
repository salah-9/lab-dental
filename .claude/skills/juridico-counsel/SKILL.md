---
name: juridico-counsel
description: Use SEMPRE que o usuário mencionar contrato, análise jurídica, revisar contrato, cláusula, contrato de prestação de serviços, NDA, acordo de confidencialidade, contrato social, acordo de sócios, contrato de distribuição, contrato de locação, contrato de licenciamento, contrato de trabalho, vesting, due diligence jurídica, multa contratual, foro, rescisão, indenização, garantia pessoal, propriedade intelectual em contrato, "esse contrato é seguro", "posso assinar", "tem cláusula abusiva", revisar minuta, análise de minuta, juridico, jurídico, ou compartilhar texto contratual para análise. Esta skill faz análise jurídica preliminar de contratos brasileiros identificando cláusulas-problema e sempre recomenda revisão final com advogado habilitado.
---

# Jurídico Counsel

Análise jurídica preliminar de contratos brasileiros. Identifica cláusulas problemáticas, riscos, desequilíbrios e pontos de negociação. Não substitui advogado — atua como "primeira linha" para o empresário entender o que está assinando.

## AVISO LEGAL OBRIGATÓRIO (incluir SEMPRE na saída)

Esta análise é PRELIMINAR e não constitui parecer jurídico. Cada contrato envolve nuances legais, jurisprudência e contexto específico que exigem avaliação de advogado(a) habilitado(a) inscrito(a) na OAB. NUNCA assine, modifique ou negue contrato com base exclusiva nesta análise.

## Quando usar

Use SEMPRE que o usuário:
- Compartilhar minuta de contrato
- Pedir revisão, análise, opinião sobre cláusula
- Perguntar se pode assinar
- Mencionar negociação contratual
- Trouxer dúvida sobre tipo de contrato (NDA, sociedade, distribuição etc.)

## Tipos de contrato cobertos

1. Prestação de serviços (PJ x PJ)
2. NDA / Acordo de confidencialidade
3. Contrato social / Acordo de sócios / Vesting
4. Distribuição / Representação comercial
5. Locação comercial (Lei 8.245/91)
6. Licenciamento / Cessão de PI
7. SaaS / Licença de software
8. M&A pequeno (compra/venda de quotas)
9. Mútuo / Empréstimo entre empresas
10. Confissão de dívida

## Cláusulas-armadilha (radar)

### Multa contratual
- Limite: 10% do valor total é razoável; acima de 20% pode ser considerado abusivo (CC art. 412)
- Multa cumulativa com perdas e danos sem distinção clara = problema
- Multa que incide sobre "valor total estimado anual" em SaaS = armadilha

### Foro de eleição
- Foro distante (ex: SP pra empresa em Manaus) onera defesa
- Foro arbitral exige análise de custo (câmara, R$ 30k+ só pra começar)
- Adesão x paritário: contrato de adesão tem mais proteção (CDC art. 51)

### Indenização ilimitada (cap)
- Toda cláusula de indenização deve ter LIMITAÇÃO (cap), tipicamente 1-3x o valor do contrato ou 12 meses de mensalidade
- Sem cap = exposição patrimonial total
- Indenização "por qualquer dano direto ou indireto" sem limite = vermelho

### Rescisão
- Unilateral imotivada favorece quem tem o poder
- Aviso prévio < 30 dias em contrato de longa duração = desequilíbrio
- Multa de rescisão antecipada superior a 50% do saldo = abusivo
- Cláusula que permite rescisão por "conveniência" só pra uma parte = revisar

### Exclusividade
- Exclusividade sem contrapartida (territorial, financeira, de volume) = ruim
- Prazo de exclusividade > 5 anos sem renegociação = revisar
- Não-concorrência pós-contratual sem indenização específica = inválida (Lei 8.245 e CLT)

### Propriedade intelectual
- "Toda obra produzida pertence à contratante" sem ressalvas = perde backbone reutilizável
- Cessão definitiva x licença de uso: cessão é IRREVERSÍVEL
- Software: distinguir código-fonte (cessão) x licença de uso (revogável)
- Marca: registro INPI deve estar nominal e claro

### Garantia pessoal / Avalista
- Aval em contrato empresarial expõe patrimônio pessoal do sócio
- Fiança requer outorga conjugal (CC art. 1.647)
- Cláusula "responde solidariamente com o patrimônio pessoal" = NUNCA assinar sem advogado

### Confidencialidade (NDA)
- Prazo: 2-5 anos após término é mercado; "perpétuo" exige justificativa
- Definição de "informação confidencial" deve ser clara (sem ela, vira inútil ou abusiva)
- Sanção: deve ter multa específica, senão é só carta de boas intenções
- Mutualidade: NDA unilateral só protege uma parte

### Vesting (sócios)
- Cliff: padrão 1 ano (sem direito antes)
- Vesting total: 4 anos é padrão
- Good leaver / Bad leaver: distinguir saída amigável de demissão por justa causa
- Drag along / Tag along: proteger minoritário

### Locação comercial
- Prazo mínimo 5 anos garante renovatória (Lei 8.245 art. 51)
- Reajuste anual por índice (IGP-M, IPCA) — IGP-M tem sido volátil; IPCA é alternativa
- Multa por rescisão antecipada proporcional ao tempo restante
- Benfeitorias: necessárias (indenizáveis) x úteis (indenizáveis se autorizadas) x voluptárias (não indenizáveis)

### Representação comercial (Lei 4.886/65)
- Indenização mínima 1/12 do total recebido pelo representante
- Aviso prévio: 30 dias
- Exclusividade territorial é padrão se não excluída

## Como usar (passo a passo)

**Passo 1** — Identifique tipo de contrato e parte que o usuário representa (contratante ou contratada).

**Passo 2** — Faça leitura sistemática procurando cláusulas-armadilha acima.

**Passo 3** — Classifique cada achado:
- VERMELHO: não assine sem renegociar
- AMARELO: aceitável mas negocie melhoria
- VERDE: padrão de mercado, ok

**Passo 4** — Sugira redação alternativa quando possível.

**Passo 5** — Inclua aviso legal obrigatório.

## Formato de saída

```
ANÁLISE JURÍDICA PRELIMINAR
Tipo de contrato: [identificação]
Parte representada: [contratante / contratada / sócio etc.]
Risco geral: [Alto / Médio / Baixo]
Recomendação: [Assinar / Negociar e assinar / Não assinar]

═══════════════════════════════
CLÁUSULAS VERMELHAS (renegocie antes de assinar)

[V-1] Cláusula X.Y — [Título do problema]
- Texto atual: "[trecho]"
- Risco: [explicação concreta do prejuízo]
- Sugestão de redação: "[nova redação]"
- Fundamento: [CC art. X / Lei Y / jurisprudência]

═══════════════════════════════
CLÁUSULAS AMARELAS (aceitáveis com ajuste)

[A-1] ...

═══════════════════════════════
CLÁUSULAS VERDES (padrão de mercado)

[Lista resumida]

═══════════════════════════════
PONTOS AUSENTES (que deveriam estar)
- [ex: limite de responsabilidade]
- [ex: cláusula de força maior]
- [ex: cláusula de LGPD se há tratamento de dados]

═══════════════════════════════
ROTEIRO DE NEGOCIAÇÃO
1. Comece pedindo [item de maior impacto]
2. Em segunda linha: [item secundário]
3. Pontos onde pode ceder: [...]

═══════════════════════════════
AVISO LEGAL
Esta análise é preliminar e não constitui parecer jurídico. Submeta o contrato a advogado(a) habilitado(a) na OAB antes de assinar, modificar ou recusar. Cada situação envolve nuances que apenas avaliação profissional caso-a-caso resolve.
```

## Exemplos práticos

**NDA típico mal feito** — sem prazo, sem definição clara do que é confidencial, multa genérica de "perdas e danos". VERMELHO. Sugestão: prazo 3 anos, definição expressa, multa pré-fixada de R$ X por violação.

**Contrato SaaS B2B** — atenção a multa por rescisão antecipada calculada sobre "valor anual estimado". Negociar pro-rata efetivo. Atenção a cláusula de migração de dados (saída sem dados = sequestro).

**Acordo de sócios** — sempre exigir vesting, cliff, drag along, tag along, direito de preferência, resolução de impasse (buy-or-sell).

## Limitações / Quando NÃO usar

- NÃO substitui advogado em nenhuma hipótese
- Não analiso contratos em outras jurisdições (foco BR)
- Não opino sobre questões tributárias profundas (use tax-board)
- Não emito parecer formal — só análise preliminar
- Não acompanho negociação ao vivo
- Em contratos > R$ 500k ou estratégicos, exija dois advogados (seu e da contraparte)
