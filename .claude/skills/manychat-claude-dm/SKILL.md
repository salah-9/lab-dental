---
name: manychat-claude-dm
description: Use SEMPRE que o usuário mencionar ManyChat, responder DM Instagram, automação de mensagens diretas, chatbot Instagram, bot de atendimento, qualificação de lead via DM, resposta automática Instagram, webhook ManyChat, integração Claude com ManyChat, atendimento automatizado redes sociais, fluxo conversacional Instagram, persona de bot, escalação humana, ou pedir para configurar respostas automáticas no Instagram. Esta skill define o fluxo ManyChat → Claude → DM, com persona, regras de escalação humana, detecção de intenção (comercial, dúvida, reclamação) e templates prontos.
---

# ManyChat Claude DM

## Quando usar

Ative SEMPRE que o usuário pedir:
- "Quero responder DMs automaticamente"
- "Configura um bot no ManyChat"
- "Como integrar Claude no ManyChat"
- "Preciso qualificar leads no DM"
- "Faz uma persona para meu chatbot"
- "Cria fluxo de atendimento no Instagram"
- "Webhook do ManyChat para Claude"

Também ative quando o contexto for: alto volume de DMs, leads frios chegando via CTA de carrossel, atendimento pré-venda, FAQ recorrente, qualificação automatizada.

## O que esta skill faz

Esta skill **desenha e entrega** uma arquitetura completa de atendimento automatizado por DM no Instagram usando ManyChat + Claude API + um orquestrador (Make ou n8n).

A arquitetura:

```
[Lead manda DM no Insta]
        ↓
[ManyChat captura via Instagram Business API]
        ↓
[ManyChat envia webhook para Make/n8n]
        ↓
[Make/n8n chama Claude API com persona + histórico]
        ↓
[Claude retorna resposta + intenção detectada + sinalização de escalação]
        ↓
[Make/n8n devolve resposta para ManyChat]
        ↓
[ManyChat entrega no DM do lead]
        ↓
[Se escalou → notifica humano via Slack/WhatsApp]
```

A skill entrega:
- **Prompt de persona** customizado para o negócio
- **JSON de intenções** detectáveis
- **Regras de escalação humana**
- **Templates** das respostas iniciais (boas-vindas, qualificação, FAQ)
- **Configuração ManyChat** passo a passo
- **Cenário Make/n8n** com nós descritos

## Como usar (passo a passo)

### 1. Levantar contexto do negócio
- Nome da empresa / criador
- Vertical e produto/serviço
- Ticket médio e ciclo de vendas
- Tom de voz (formal/informal — escala 1-10)
- Volume médio de DMs/dia
- O que pode ser respondido pelo bot, o que precisa de humano
- Horário de atendimento humano (para escalação)

### 2. Definir persona

Estrutura do prompt-persona:

```markdown
Você é [NOME], assistente virtual de [EMPRESA].

OBJETIVO PRIMÁRIO: [qualificar lead / agendar reunião / responder dúvida / vender]

TOM:
- Escala formalidade: [1-10]
- Use: ["beleza", "tranquilo", "vamos lá"]
- Evite: ["chefia", "respeitável cliente", emoji excessivo]

INFORMAÇÕES QUE VOCÊ SABE:
- Produto: [descrição em 3 linhas]
- Preço: [se pode revelar / em qual condição]
- Diferenciais: [3-5 pontos]
- FAQ comum: [10 perguntas + respostas]

INFORMAÇÕES QUE VOCÊ NÃO SABE (escale):
- Casos jurídicos
- Reclamações formais
- Pedidos de desconto acima de [X]%
- Suporte técnico avançado

REGRAS:
- NUNCA invente preços não autorizados
- NUNCA prometa prazos sem confirmar
- SEMPRE pergunte o nome no primeiro turno
- APÓS 3 turnos sem progresso → escale
```

### 3. Mapear intenções detectáveis

Claude deve retornar JSON com intenção classificada:

```json
{
  "intent": "interesse_comercial | duvida_produto | reclamacao | suporte | spam | saudacao | outro",
  "confidence": 0.0-1.0,
  "lead_score": 0-100,
  "escalate_human": true|false,
  "escalation_reason": "string | null",
  "next_message": "texto da resposta",
  "tags_manychat": ["tag1","tag2"]
}
```

Regras-padrão de escalação:
- `intent == "reclamacao"` → escalar imediato
- `confidence < 0.5` por 2 turnos → escalar
- Cliente pede humano explicitamente → escalar
- Detectou risco jurídico (palavras: processo, advogado, Procon) → escalar
- Detectou risco reputacional (pedido de reembolso, ameaça pública) → escalar
- Lead score > 80 + ticket alto → escalar para closer humano

### 4. Templates de mensagens iniciais

```yaml
boas_vindas:
  texto: "Oi! Aqui é a [NOME] da [EMPRESA]. Vi que você chegou pelo nosso conteúdo, posso te ajudar em quê?"
  quick_replies: ["Quero saber mais", "Tenho dúvida", "Falar com humano"]

qualificacao_b2b:
  texto: "Pra eu te ajudar melhor: você trabalha sozinho ou tem time?"
  quick_replies: ["Sozinho", "2-5 pessoas", "5+ pessoas"]

oferta_inicial:
  texto: "Massa! Para esse cenário a gente tem o [PRODUTO]. Quer que eu te mande mais detalhe?"

faq_preco:
  condicao: "se intent == duvida_produto AND palavra-chave == preço"
  texto: "O investimento varia conforme [X]. Posso te chamar num call rápido pra entender? Tem 15min essa semana?"
```

### 5. Configuração ManyChat (passo a passo)

1. Conectar conta Instagram Business ao ManyChat
2. Criar **Flow** principal com gatilho "Default Reply"
3. Adicionar **External Request** apontando para webhook do Make/n8n
4. Mapear variáveis: `{{contact.first_name}}`, `{{last_input_text}}`, `{{contact.thread_id}}`
5. Receber resposta no campo customizado `bot_response`
6. Enviar `{{bot_response}}` como texto
7. Aplicar tags conforme `tags_manychat` retornadas
8. Se `escalate_human == true` → mover para sequência "Atendimento Humano" e notificar via Slack

### 6. Configuração Make/n8n (cenário)

Nós do cenário:
1. **Webhook trigger** (ManyChat envia)
2. **HTTP Request** para buscar histórico (últimos 10 turnos)
3. **OpenRouter/Anthropic** — chamar Claude com prompt-persona + histórico + nova mensagem
4. **JSON Parse** da resposta de Claude
5. **Router** baseado em `escalate_human`:
   - Se false → 6. Webhook de volta para ManyChat
   - Se true → 6a. Slack notification + 6b. Webhook ManyChat com mensagem de transferência
6. **Append** turno em banco (Airtable/Sheets) para histórico

## Formato de saída

A skill entrega um pacote estruturado:

```markdown
# Setup ManyChat + Claude — [EMPRESA]

## 1. Persona (cole no system prompt do Claude)
[prompt completo]

## 2. JSON Schema de resposta
[schema completo]

## 3. Templates de mensagem
[YAML de templates]

## 4. Regras de escalação
[lista de regras + ação]

## 5. Setup ManyChat
[passo a passo numerado]

## 6. Cenário Make/n8n
[nós descritos + JSON do cenário se possível]

## 7. KPIs para monitorar
- Taxa de resolução sem humano (alvo: 60-75%)
- Tempo médio de resposta (alvo: < 5s)
- Lead score médio
- Taxa de escalação correta
- NPS pós-atendimento
```

## Exemplos práticos

### Exemplo — Consultor financeiro pessoa física

Persona: "Sou a Marina, assistente do consultor Pedro. Tom informal mas respeitoso (escala 6). Objetivo: agendar diagnóstico gratuito de 30min."

Fluxo:
- DM chega: "Oi, vi seu carrossel sobre dívida"
- Bot: "Oi! Tudo certo? Aqui é a Marina, do escritório do Pedro. Conta rapidinho: a dívida é cartão, financiamento ou outra?"
- DM: "Cartão, uns 30k"
- Bot detecta `lead_score = 85` (valor + intenção clara), responde: "Entendi. A gente tem ajudado gente com esse perfil. Quer agendar 30min com o Pedro essa semana? É gratuito."
- Se sim → escala para humano agendar, com contexto.

### Exemplo — Loja de roupa pequena

Persona: foco em FAQ (frete, tamanho, troca). Escala para humano só em reclamação ou pedido especial.

## Limitações / Quando NÃO usar

- **Não use** para perfis com menos de 10 DMs/dia (over-engineering)
- **Não use** para vendas complexas B2B enterprise (precisa SDR humano)
- **Não use** sem ManyChat plano pago (necessário para Instagram Business + webhooks)
- **Cuidado** com setores regulados (saúde, financeiro): bot não pode dar diagnóstico nem conselho financeiro específico
- Instagram tem **janela de 24h** para responder via API após mensagem do usuário — bot precisa responder rápido ou perde a janela

## Integração com outras skills do ZION

- `carrossel-instagram-generator` — produz o conteúdo que gera os DMs
- `instagram-automation` — agenda os posts com CTA "comente X"
- `brandbook-prompt-system` — define o tom de voz da persona
- `crise-comunicacao` — se houver crise reputacional detectada nos DMs
- `mentor-coach-empresarial` — pode revisar dados de qualificação semanalmente
