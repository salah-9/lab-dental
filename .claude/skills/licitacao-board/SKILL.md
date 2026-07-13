---
name: licitacao-board
description: Use SEMPRE que o usuário mencionar licitação, edital, Lei 14.133, nova lei de licitações, pregão eletrônico, concorrência, diálogo competitivo, dispensa de licitação, inexigibilidade, RDC, habilitação jurídica, habilitação fiscal, habilitação técnica, qualificação econômico-financeira, atestado de capacidade técnica, SICAF, ComprasNet, BB Licitações, BEC, "vale a pena participar dessa licitação", analisar edital, análise de edital, recurso administrativo, impugnação de edital, modalidade licitatória, critério de julgamento, menor preço, técnica e preço, ata de registro de preços, ARP, ou trouxer texto/link de edital. Esta skill faz análise sênior de editais sob a Lei 14.133/2021 com recomendação GO/NO-GO executiva.
---

# Licitação Board

Análise sênior de editais sob a Lei 14.133/2021 (Nova Lei de Licitações e Contratos Administrativos). Devolve relatório executivo com diagnóstico de viabilidade, riscos e recomendação GO/NO-GO para a empresa.

## Quando usar

Use SEMPRE que o usuário:
- Compartilhar edital ou link de licitação
- Perguntar se vale a pena participar
- Pedir análise de modalidade, exigências, riscos
- Mencionar Lei 14.133, pregão, concorrência, dispensa
- Dúvida sobre habilitação, atestado, recurso, impugnação

## Visão da Lei 14.133/2021 (regime atual desde 2024)

### Modalidades vigentes
1. **Pregão** — bens e serviços comuns; menor preço ou maior desconto
2. **Concorrência** — bens e serviços especiais; obras; engenharia; admite todos critérios de julgamento
3. **Concurso** — escolha de trabalho técnico, artístico
4. **Leilão** — alienação de bens
5. **Diálogo competitivo** — soluções complexas/inovadoras com participação prévia da Administração

### Critérios de julgamento (art. 33)
- Menor preço
- Maior desconto
- Melhor técnica ou conteúdo artístico
- Técnica e preço
- Maior lance (leilão)
- Maior retorno econômico

### Procedimentos auxiliares
- Pré-qualificação
- Credenciamento
- Procedimento de manifestação de interesse
- Sistema de registro de preços (SRP/ARP)
- Registro cadastral (SICAF)

### Modos de disputa
- Aberto (lances sucessivos)
- Fechado (proposta sigilosa, único)
- Aberto e fechado (combinado)
- Fechado e aberto (combinado)

## Exigências de habilitação (art. 62 a 70)

### Habilitação jurídica
- Registro empresarial / contrato social
- Procuração se houver representante
- CNPJ ativo

### Habilitação fiscal, social e trabalhista
- CND Federal (Receita + PGFN unificadas)
- CND Estadual e Municipal
- FGTS (CRF)
- CNDT (débitos trabalhistas)
- Inscrição estadual/municipal se exigido

### Habilitação técnica
- Atestados de capacidade técnica (pessoa jurídica e/ou profissional)
- Quantitativos mínimos: em geral, edital exige 50% do objeto licitado
- Registro em entidade profissional (CREA, CRC, OAB etc.)
- Vistoria técnica (quando exigida)

### Qualificação econômico-financeira
- Balanço patrimonial + DRE último exercício
- Índices de Liquidez Geral (LG), Solvência Geral (SG), Liquidez Corrente (LC) — em geral todos ≥ 1
- Patrimônio líquido mínimo (até 10% do valor estimado)
- Capital social mínimo (até 10% do valor estimado)
- Garantia de proposta (até 1% do valor estimado, opcional)
- Certidão negativa de falência

## Red flags em editais (radar de risco)

### Direcionamento
- Exigência técnica que SÓ um fornecedor cumpre
- Atestado com quantitativo absurdo (> 100% do objeto)
- Marca/modelo específico sem "ou similar"
- Prazo de entrega irrealista (5 dias úteis pra entrega complexa)
- Visita técnica obrigatória em horário restrito sem justificativa

### Risco econômico
- Preço estimado abaixo de mercado (margem zero ou negativa)
- Forma de pagamento longa (45-60 dias) somada a multas pesadas
- Reajuste mal definido (ou sem cláusula de reequilíbrio)
- Garantia contratual alta (5% padrão; acima exige análise)

### Risco operacional
- Local de execução distante e logística complexa
- SLA agressivo com multa diária pesada (acima de 0,5% por dia)
- Exigência de profissionais dedicados exclusivamente
- Sazonalidade não considerada

### Risco jurídico
- Penalidades desproporcionais (multa de 30% sobre contrato)
- Foro inconveniente (raro em licitação, padrão é foro do órgão)
- Cláusula de rescisão unilateral abusiva (lembrar que art. 137-138 prevê)
- Exigência de garantias adicionais não previstas em lei

## Como usar (passo a passo)

**Passo 1** — Receba o edital ou descrição. Identifique:
- Órgão licitante e UASG
- Modalidade e critério de julgamento
- Objeto e valor estimado
- Datas: publicação, sessão pública, entrega
- Local de execução

**Passo 2** — Liste exigências de habilitação. Marque o que a empresa já tem e o que falta.

**Passo 3** — Calcule viabilidade econômica:
- Preço estimado vs custo da empresa
- Margem possível
- Fluxo de caixa (quando paga vs custos incorridos)

**Passo 4** — Identifique red flags do edital.

**Passo 5** — Avalie probabilidade de vitória (concorrência esperada, diferencial da empresa).

**Passo 6** — Recomendação executiva GO / NO-GO / GO COM IMPUGNAÇÃO.

## Formato de saída

```
ANÁLISE DE EDITAL — Lei 14.133/2021
Órgão: [nome] | UASG: [código]
Objeto: [resumo em 1 frase]
Modalidade: [Pregão / Concorrência / etc.] — [Eletrônico/Presencial]
Critério: [menor preço / técnica e preço / etc.]
Valor estimado: R$ [X] | Valor anual se ARP: R$ [Y]
Data da sessão: [dd/mm/aaaa hh:mm]
Local de execução: [município/estado]

═══════════════════════════════
1. ENQUADRAMENTO LEGAL
- Modalidade adequada ao objeto? [SIM/NÃO + justificativa]
- Critério de julgamento coerente? [SIM/NÃO]
- Modo de disputa: [aberto/fechado/combinado]
- Procedimentos auxiliares: [SRP, credenciamento etc.]

═══════════════════════════════
2. HABILITAÇÃO — CHECK-LIST

Jurídica:
[ ] Contrato social atualizado
[ ] CNPJ ativo
[ ] Procuração (se aplicável)

Fiscal/Social/Trabalhista:
[ ] CND Federal | [ ] Estadual | [ ] Municipal
[ ] FGTS (CRF) | [ ] CNDT
[ ] Falência

Técnica:
[ ] Atestado tipo A — quantitativo X
[ ] Atestado tipo B — quantitativo Y
[ ] Registro CREA/CRC/etc.
[ ] Vistoria técnica — prazo: [data]

Econômico-financeira:
- Patrimônio líquido mínimo: R$ [valor]
- Capital social mínimo: R$ [valor]
- Índices LG/SG/LC ≥ [valor]
- Garantia de proposta: R$ [valor]

Status habilitação: [APTO / FALTAM X DOCUMENTOS / INAPTO]

═══════════════════════════════
3. ANÁLISE ECONÔMICA

Preço estimado: R$ [X]
Custo direto estimado: R$ [Y]
Margem bruta possível: [Z%]
Margem líquida após impostos/garantia/risco: [W%]

Forma de pagamento: [prazo]
Fluxo de caixa: [investimento inicial vs recebimento]
Viabilidade financeira: [VIÁVEL / APERTADO / INVIÁVEL]

═══════════════════════════════
4. RED FLAGS DO EDITAL

[F-1] [Descrição do problema]
- Risco: [explicação]
- Mitigação: [impugnar / pedir esclarecimento / aceitar]

[F-2] ...

═══════════════════════════════
5. CONCORRÊNCIA ESPERADA
- Número provável de licitantes: [estimativa]
- Concorrentes prováveis: [empresas conhecidas]
- Diferencial competitivo da empresa: [...]
- Probabilidade de vitória: [Alta / Média / Baixa]

═══════════════════════════════
6. RECOMENDAÇÃO EXECUTIVA

Status: [GO / NO-GO / GO COM IMPUGNAÇÃO PRÉVIA]

Justificativa: [2-3 frases brutais]

Se GO — próximos passos:
1. Providenciar [documentos faltantes] até [data]
2. Calcular preço final com margem [X%]
3. Treinar pregoeiro/representante para a sessão
4. Cadastrar/atualizar SICAF até [data]

Se NO-GO — razão principal: [...]

Se IMPUGNAÇÃO — pontos a impugnar:
1. [Item específico do edital + fundamento legal]
2. [Item específico do edital + fundamento legal]
Prazo: até 3 dias úteis antes da abertura (art. 164).

═══════════════════════════════
DATAS-CHAVE
- Pedido de esclarecimento: até [data]
- Impugnação do edital: até [data]
- Cadastro da proposta: até [data]
- Sessão pública: [data + hora]
- Prazo para recursos: 3 dias úteis após habilitação/julgamento
```

## Exemplos práticos

**Edital direcionado** — exigência de "atestado comprovando 80% do quantitativo em ÓRGÃO FEDERAL nos últimos 12 meses". Restringe sem justificativa técnica. IMPUGNAR com fundamento no art. 67, §1º (atestado deve guardar correspondência com o objeto, sem restrições impertinentes).

**Pregão com preço baixo** — preço estimado R$ 100k, custo da empresa R$ 95k, prazo de pagamento 45 dias. Margem 5% que vira 0% após impostos e custo de capital. NO-GO.

**Concorrência boa** — empresa tem todos os atestados, preço estimado R$ 800k, custo R$ 560k, 5 concorrentes esperados, contrato de 12 meses com reajuste anual. GO, propor R$ 720k (margem 22%, competitivo).

## Limitações / Quando NÃO usar

- Não substitui assessoria jurídica especializada em licitações para casos grandes ou complexos
- Não acompanho sessão pública ao vivo
- Não conheço todas as decisões TCU/TCEs específicas — sinalize quando for jurisprudência relevante
- Não opino sobre licitações estrangeiras
- Para contratos acima de R$ 1M ou estratégicos, recomende advogado especialista em direito administrativo
- Lei 14.133 ainda gera divergências interpretativas — algumas práticas evoluem com jurisprudência
