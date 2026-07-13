---
name: tax-board
description: Use SEMPRE que o usuário mencionar imposto, tributação, regime tributário, Simples Nacional, Lucro Presumido, Lucro Real, anexo do Simples, IBS, CBS, reforma tributária, LC 214/2025, ISS, ICMS, PIS, COFINS, IRPJ, CSLL, DAS, MEI, fator R, carga tributária, planejamento tributário, mudança de regime, "qual regime me paga menos", "quanto vou pagar de imposto", elisão fiscal, substituição tributária, split payment, ou pedir comparativo tributário. Esta skill faz análise tributária preliminar para SMB brasileira comparando regimes com base em faturamento, atividade e margem, sempre recomendando validação final com contador.
---

# Tax Board

Análise tributária preliminar para pequenas e médias empresas brasileiras. Compara regimes (Simples, Presumido, Real), considera a reforma tributária (LC 214/2025 — IBS/CBS) e devolve recomendação com sinais de alerta. NÃO substitui contador.

## AVISO OBRIGATÓRIO (incluir SEMPRE)

Esta análise é preliminar e simplificada. Tributação brasileira tem inúmeras especificidades (substituição tributária, benefícios estaduais, regimes especiais, créditos, glosas) que exigem análise de contador(a) registrado(a) no CRC com base em sua escrita fiscal real. Valide TUDO com seu contador antes de qualquer decisão de regime ou planejamento.

## Quando usar

Use SEMPRE que o usuário:
- Perguntar sobre regime tributário
- Comparar Simples x Presumido x Real
- Mencionar fator R, anexo, alíquota
- Citar reforma tributária / IBS / CBS / LC 214
- Pedir simulação de carga tributária
- Estiver no limite de faturamento de algum regime

## Visão geral dos regimes (vigência 2026)

### Simples Nacional (LC 123/2006)
- Limite: R$ 4,8 milhões/ano de receita bruta (sublimite R$ 3,6M para ICMS/ISS em alguns estados)
- Anexos:
  - **Anexo I — Comércio**: 4,00% a 19,00%
  - **Anexo II — Indústria**: 4,50% a 30,00%
  - **Anexo III — Serviços (folha alta, com fator R ≥ 28%)**: 6,00% a 33,00%
  - **Anexo IV — Construção, advocacia, vigilância (sem CPP no DAS)**: 4,50% a 33,00%
  - **Anexo V — Serviços (folha baixa, fator R < 28%)**: 15,50% a 30,50%
- **Fator R** = (folha 12m + pró-labore) / receita 12m. Se ≥ 28%, serviço sai do Anexo V (caro) pro Anexo III (barato).

### Lucro Presumido
- Limite: R$ 78 milhões/ano
- Presunção de lucro:
  - 8% comércio / 12% serviços de transporte / 16% transporte passageiros / 32% serviços em geral, profissionais
- Sobre o lucro presumido: IRPJ 15% (+ 10% adicional acima de R$ 20k/mês) e CSLL 9%
- PIS 0,65% + COFINS 3,00% sobre receita (cumulativo, sem crédito)
- ISS (2-5%) ou ICMS (variável por estado)
- Vantagens: simplicidade, não recolhe pelo lucro real
- Desvantagem: paga imposto mesmo no prejuízo

### Lucro Real
- Obrigatório acima de R$ 78M, ou para bancos, factoring, alguns regimes
- IRPJ 15% (+10%) e CSLL 9% sobre LUCRO REAL apurado
- PIS 1,65% + COFINS 7,60% (não-cumulativo, com créditos)
- Vantagem: paga pelo lucro efetivo, aproveita prejuízos fiscais
- Desvantagem: escrita complexa, custos contábeis altos (R$ 3-15k/mês)

### MEI
- Limite: R$ 81.000/ano (proposta de aumento em discussão)
- DAS-MEI: R$ 70-80/mês
- Não cabe para sócios, atividades vedadas (consultor, médico, dev em algumas situações)

## Reforma Tributária — IBS/CBS (LC 214/2025)

**Cronograma:**
- 2026: alíquota teste 1% (IBS 0,1% + CBS 0,9%)
- 2027: CBS plena, PIS/COFINS extintos
- 2029-2032: transição ICMS/ISS → IBS (proporção crescente)
- 2033: IBS pleno, ICMS/ISS extintos

**Características:**
- IVA dual: CBS (federal) + IBS (estadual/municipal)
- Não-cumulativo amplo (crédito de tudo que é insumo, incluindo uso/consumo)
- Alíquota de referência estimada: 26-28% (somando IBS+CBS)
- Cashback para baixa renda em alguns itens
- Split payment para reduzir sonegação
- Regimes específicos: combustíveis, serviços financeiros, planos de saúde, bens imóveis

**Impacto por setor (estimativas iniciais):**
- Indústria: tende a pagar MENOS (cadeia crédito amplo)
- Serviços: tende a pagar MAIS (hoje pagam alíquota baixa de ISS)
- Simples: pode optar por se manter no Simples OU migrar híbrido para apropriar créditos IBS/CBS quando vende pra empresa que precisa de crédito
- B2C: split payment muda fluxo de caixa

## Como usar (passo a passo)

**Passo 1** — Colete dados mínimos:
- Atividade (CNAE principal)
- Faturamento bruto últimos 12 meses (e projeção próximos 12)
- Folha + pró-labore (para fator R)
- Margem de lucro líquido aproximada
- Estado/município (afeta ISS/ICMS)
- Vende pra B2B ou B2C? (relevante pós-reforma)
- Tem ST (substituição tributária)?

**Passo 2** — Simule os 3 regimes aplicáveis com fórmulas simplificadas.

**Passo 3** — Aplique sensibilidade pra reforma 2027+ se faturamento > R$ 1M.

**Passo 4** — Devolva tabela comparativa + recomendação + riscos.

## Fórmulas rápidas

**Simples (Anexo III, serviço):** alíquota efetiva = (RBT12 × alíquota nominal – PD) / RBT12

**Presumido serviço (32%):**
- IRPJ = RB × 32% × 15% = 4,80%
- CSLL = RB × 32% × 9% = 2,88%
- PIS = 0,65% | COFINS = 3,00% | ISS = 2-5%
- Total aprox: **13,3% a 16,3%** da receita

**Presumido comércio (8%):**
- IRPJ = RB × 8% × 15% = 1,20%
- CSLL = RB × 12% × 9% = 1,08%
- PIS+COFINS = 3,65%
- ICMS = variável
- Total aprox: **5,9% + ICMS**

**Lucro Real serviço com margem 20%:**
- IRPJ+CSLL = lucro × 24% (aprox 4,8% sobre receita)
- PIS+COFINS = 9,25% (com créditos compensa parte)
- Total: pode ser **8-14%** dependendo de créditos

## Formato de saída

```
ANÁLISE TRIBUTÁRIA PRELIMINAR
Empresa: [atividade / CNAE]
Faturamento 12m: R$ [X]
Margem líquida estimada: [Y%]
Fator R atual: [Z%]

═══════════════════════════════
COMPARATIVO DE REGIMES

┌──────────────────┬──────────┬───────────┬──────────┐
│ Regime           │ Carga    │ R$ /mês   │ Aplicável│
├──────────────────┼──────────┼───────────┼──────────┤
│ Simples Anexo III│ 9,5%     │ R$ 9.500  │ SIM      │
│ Lucro Presumido  │ 14,3%    │ R$ 14.300 │ SIM      │
│ Lucro Real       │ 11,8%    │ R$ 11.800 │ SIM      │
└──────────────────┴──────────┴───────────┴──────────┘

(Premissas: receita R$ 100k/mês, folha R$ 30k, margem 18%, ISS 5%, sem ST)

═══════════════════════════════
RECOMENDAÇÃO
Manter Simples Nacional Anexo III enquanto fator R ≥ 28%.
Trigger de reavaliação: se folha cair abaixo de R$ 28k OU receita ultrapassar R$ 350k/mês.

═══════════════════════════════
ATENÇÃO / RISCOS
- Se fator R cair abaixo de 28%, vai pro Anexo V (15,5%+) — monitorar mensal
- Vendendo pra B2B grande pós-2027, pode ser interessante apropriar créditos IBS/CBS
- Verificar substituição tributária do produto (pode mudar conta)
- Limite Simples R$ 4,8M se aproximando? Planejar transição

═══════════════════════════════
IMPACTO REFORMA (2027+)
[Sinalização do que muda na atividade]

═══════════════════════════════
PRÓXIMOS PASSOS
1. Levar essa simulação ao seu contador
2. Pedir simulação real com dados de escrita fiscal
3. Decidir até [data limite para mudança de regime — janeiro]

═══════════════════════════════
AVISO LEGAL
Análise preliminar baseada em premissas declaradas. Validação com contador(a) habilitado(a) é OBRIGATÓRIA antes de qualquer decisão. Não considera ST, benefícios estaduais, regimes especiais, glosas, sublimites e particularidades que exigem escrita real.
```

## Exemplos práticos

**Dev consultor faturando R$ 25k/mês como PJ:**
- Anexo III com fator R alto (pró-labore decente): ~6-9% de carga
- Anexo V se não pagar pró-labore: ~15,5% (desperdício!)
- **Sempre puxar pró-labore para ficar em Anexo III**

**E-commerce R$ 300k/mês com margem 8%:**
- Simples Comércio Anexo I: ~10-12%
- Presumido: ~6% + ICMS (pode ser melhor!)
- Real: arriscado se margem baixa, mas pode otimizar com créditos
- **Vale rodar conta caso a caso**

## Limitações / Quando NÃO usar

- NUNCA substitui contador
- Não considero substituição tributária específica de cada NCM/produto
- Não considero benefícios fiscais estaduais (varia muito)
- Não considero IRPF do sócio (pró-labore vs distribuição)
- Reforma IBS/CBS ainda tem regulamentações em curso; números são estimativas
- Em dúvida real de regime, pague consultoria de R$ 2-5k pra contador experiente fazer simulação completa — paga o investimento em poucos meses
