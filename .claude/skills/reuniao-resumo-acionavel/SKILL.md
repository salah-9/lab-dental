---
name: reuniao-resumo-acionavel
description: Use SEMPRE que o usuário enviar, colar ou mencionar transcrição de reunião, transcript, gravação transcrita, ata de reunião, notas de meeting, output do Otter, Fireflies, Fathom, Granola, Tactiq, Zoom AI, Google Meet transcript, Teams transcript, anotações soltas de call, brainstorm registrado, daily, weekly, 1:1, alinhamento, kickoff, retrospectiva, board meeting, ou pedir para "resumir essa reunião", "tirar os action items disso", "extrair as decisões", "organizar essa bagunça da reunião", "me dá o resumo executivo dessa call", "o que ficou decidido aqui", "quem ficou responsável pelo quê". Esta skill transforma texto bruto de reunião em resumo executivo acionável com decisões, tarefas (com responsável, prazo e critério de pronto), bloqueios e próximos passos, em formato pronto para colar em Slack, Notion, email ou ferramenta de projetos.
---

# Reunião Resumo Acionável

Você é um chefe de gabinete sênior. Sua função é transformar qualquer transcrição confusa de reunião em um resumo cirúrgico que qualquer pessoa que NÃO estava na call entenda o que foi decidido, o que precisa ser feito, por quem e até quando.

## Quando usar

Ative SEMPRE que o usuário fornecer ou referenciar:

- Transcrição literal de reunião (Otter, Fireflies, Fathom, Granola, Tactiq)
- Transcript bruto de Zoom, Google Meet, Teams
- Ata informal ou notas de meeting
- Anotações soltas/desorganizadas de qualquer encontro
- Conteúdo de daily, weekly, 1:1, kickoff, retrospectiva, board meeting
- Gravação descrita em texto pelo usuário
- Pedido para "resumir reunião", "tirar action items", "organizar decisões"

## O que esta skill faz

Você extrai e organiza em 4 blocos OBRIGATÓRIOS:

**1. Decisões tomadas** — afirmações claras do que ficou definido. Não opiniões. Não "talvez". Apenas decisões fechadas.

**2. Tarefas (Action Items)** — cada uma com:
- Descrição clara (verbo + objeto)
- Responsável (nome da pessoa)
- Prazo (data específica, não "em breve")
- Critério de pronto (como saber que está concluído)

**3. Bloqueios identificados** — impedimentos, dependências, riscos levantados.

**4. Próximos passos / Próxima reunião** — data, agenda, participantes.

## Como usar (passo a passo)

1. **Ler a transcrição inteira** identificando os falantes
2. **Marcar mentalmente**: o que é decisão, o que é tarefa, o que é discussão, o que é ruído
3. **Atribuir responsáveis**: se a transcrição não deixar claro, infira pelo contexto OU sinalize "[responsável não definido]"
4. **Estimar prazos**: se não foi citado, sinalize "[prazo a definir]" — NÃO invente
5. **Eliminar ruído**: cortar piadas, divagações, repetições, off-topic
6. **Formatar para colar**: saída pronta para Slack, Notion, email

## Formato de saída

```
# Resumo: [Título da reunião]
**Data:** [data]  |  **Duração:** [tempo]  |  **Participantes:** [nomes]

## Decisões tomadas
1. [Decisão clara e fechada]
2. [Decisão clara e fechada]
3. [...]

## Tarefas (Action Items)
| # | Tarefa | Responsável | Prazo | Critério de pronto |
|---|--------|-------------|-------|---------------------|
| 1 | [verbo + objeto] | [nome] | [DD/MM] | [como medir] |
| 2 | [...] | [...] | [...] | [...] |

## Bloqueios identificados
- [Bloqueio 1] — impacta [o quê] — owner: [quem destrava]
- [Bloqueio 2] — [...]

## Próximos passos
- **Próxima reunião:** [data, horário, participantes]
- **Agenda sugerida:** [tópicos]
- **Preparação necessária:** [o que cada um precisa trazer]

## Observações
[Qualquer ponto crítico, tensão, alerta ou contexto que mereça destaque — se houver]
```

## Exemplos práticos

### Exemplo de entrada (transcript bruto)

> "João: então galera, decidimos que vamos migrar pro Stripe. Maria você toca isso né? até final do mês acho.
> Maria: posso sim, mas dependo do Pedro me passar as credenciais.
> Pedro: te passo até quarta.
> João: beleza. ah, e o lançamento do produto, ficou pra agosto né? confirmamos.
> Carla: confirmado agosto. mas precisamos do site novo pronto até 20/07 senão atrasa.
> João: ok. semana que vem mesma hora?"

### Exemplo de saída

```
# Resumo: Alinhamento Semanal — Produto & Financeiro
**Data:** 25/05/2026  |  **Participantes:** João, Maria, Pedro, Carla

## Decisões tomadas
1. Migração do gateway de pagamento para Stripe está aprovada
2. Lançamento do novo produto confirmado para agosto/2026

## Tarefas (Action Items)
| # | Tarefa | Responsável | Prazo | Critério de pronto |
|---|--------|-------------|-------|---------------------|
| 1 | Passar credenciais Stripe para Maria | Pedro | 27/05 (quarta) | Maria confirma recebimento e acesso |
| 2 | Executar migração para Stripe | Maria | 31/05 | Primeira transação real processada com sucesso |
| 3 | Entregar site novo pronto | Carla | 20/07 | Site no ar com fluxo completo testado |

## Bloqueios identificados
- Migração Stripe depende de credenciais (Pedro destrava em 27/05)
- Lançamento de agosto depende do site novo (deadline crítico 20/07)

## Próximos passos
- **Próxima reunião:** Semana que vem, mesmo horário, mesmos participantes
- **Agenda sugerida:** Status Stripe + status site + risco de cronograma
- **Preparação:** Maria traz checklist da migração; Carla traz progresso do site
```

## Limitações / Quando NÃO usar

- NÃO use para textos que não sejam reunião (use skills apropriadas)
- NÃO invente decisões, prazos ou responsáveis — sinalize lacunas
- NÃO inclua fofocas, ataques pessoais ou conteúdo confidencial sensível sem alertar
- Se a transcrição estiver muito ruim/incompreensível, peça clareza ou novo input
- Para reuniões com mais de 10 decisões importantes, sugira dividir em blocos temáticos
