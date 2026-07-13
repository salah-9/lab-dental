---
name: instagram-automation
description: Use SEMPRE que o usuário mencionar postar no Instagram, agendar post, automatizar Instagram, publicar carrossel, publicar reel, agendamento automático, postagem programada, melhor horário para postar, fila de postagens, calendário editorial Instagram, publicar via API, Composio Instagram, Rube MCP Instagram, automação de redes sociais, ou pedir para enviar/subir/publicar conteúdo no Instagram. Esta skill orquestra postagens automáticas via Composio/Rube MCP com aprovação humana obrigatória, calculando melhor horário por nicho brasileiro, validando hashtags (8-15), checando duplicidade e respeitando limites da API.
---

# Instagram Automation

## Quando usar

Ative SEMPRE que o usuário pedir:
- "Posta isso no Instagram"
- "Agenda esse carrossel para terça às 19h"
- "Quero programar 7 posts da semana"
- "Sobe esse reel no meu perfil"
- "Qual o melhor horário para postar?"
- "Automatiza minha publicação"
- "Cria um calendário editorial e agenda tudo"

Também ative quando o usuário já gerou um conteúdo (via skills `carrossel-instagram-generator`, `nano-banana-criativos`, `veo-videos`) e quer publicar.

## O que esta skill faz

Esta skill é a **camada de execução** de postagens no Instagram. Ela:

1. Recebe o pacote de conteúdo (caption + hashtags + mídia + horário sugerido)
2. Valida o pacote contra regras de qualidade e limites técnicos
3. Calcula o **melhor horário de postagem** baseado em vertical brasileira
4. Apresenta o **preview de aprovação humana** (obrigatório — nunca posta sem confirmação)
5. Executa a postagem via **Composio MCP** ou **Rube MCP**
6. Registra log em planilha/notion (se configurado)
7. Retorna URL do post publicado

**Importante**: Esta skill NUNCA posta sem aprovação humana explícita. O fluxo aprovação → publicação é INVIOLÁVEL.

## Como usar (passo a passo)

### 1. Receber o pacote de postagem

Inputs obrigatórios:
- `caption` (texto até 2.200 caracteres)
- `media` (array de URLs/paths de imagens ou vídeo)
- `tipo` (feed, carrossel, reel, story)
- `account` (handle do Instagram conectado via Composio)

Inputs opcionais:
- `hashtags` (se ausente, sugerir 8-15)
- `agendamento` (datetime; se ausente, calcular)
- `localizacao`
- `primeiro_comentario` (estratégia comum para hashtags)

### 2. Validar pacote

| Checagem | Regra |
|----------|-------|
| Caption length | ≤ 2.200 caracteres |
| Hashtags | 8 a 15 (mais que isso reduz alcance em 2026) |
| Mídia carrossel | 2 a 10 itens, ratio 1:1 ou 4:5 |
| Reel | 9:16, 3 a 90 segundos |
| Duplicidade | Comparar caption com últimos 30 posts |
| Palavras banidas | Checar lista de termos que reduzem alcance |
| Menções | Validar handles citados |

### 3. Calcular melhor horário (se não fornecido)

Tabela base por nicho (horário Brasília):

| Vertical | Dias fortes | Janelas de pico |
|----------|-------------|-----------------|
| Infoproduto / Educação | Ter, Qua, Qui | 12h-13h, 19h-21h |
| Saúde / Bem-estar | Seg, Qua, Sex | 06h-08h, 18h-20h |
| Moda / Beleza | Qua, Qui, Sex, Sáb | 11h-13h, 20h-22h |
| Negócios / B2B | Ter, Qua, Qui | 08h-10h, 12h-14h |
| Alimentação / Gastronomia | Qui, Sex, Sáb, Dom | 11h-13h, 18h-20h |
| Imóveis | Seg a Sex | 09h-11h, 19h-21h |
| Advocacia / Contabilidade | Ter, Qua, Qui | 09h-11h, 14h-16h |
| Construção / Indústria | Seg a Sex | 07h-09h, 17h-19h |
| Lifestyle / Entretenimento | Sex, Sáb, Dom | 19h-23h |

Ajustar com base no histórico do perfil se disponível via Insights API.

### 4. Apresentar preview de aprovação

Sempre retornar um bloco assim ANTES de chamar o MCP:

```
================================================
APROVAÇÃO NECESSÁRIA — POSTAGEM INSTAGRAM
================================================
Conta: @[handle]
Tipo: [carrossel/reel/feed]
Agendado para: [data hora]

CAPTION:
[mostrar caption completa]

HASHTAGS (12):
#tag1 #tag2 ...

MÍDIA: [N arquivos / link de preview]

================================================
Responda APROVADO para publicar, ou indique ajustes.
================================================
```

### 5. Executar via MCP

Após aprovação:
- **Composio**: chamar tool `composio.instagram.create_post` com payload validado
- **Rube**: chamar workflow `rube.publish_instagram`
- Capturar `post_id` e `permalink` retornados

### 6. Registrar log

Estrutura sugerida (Google Sheets, Notion ou Airtable):
- Data/hora real de publicação
- Tipo, caption (primeiros 100 char), hashtags, mídia
- Permalink, post_id
- Status (sucesso/erro)
- Métricas iniciais (alcance, salvos, comentários) coletadas em D+1

## Formato de saída

```yaml
status: aguardando_aprovacao
preview:
  conta: "@vision.ai"
  tipo: "carrossel"
  agendado_para: "2026-05-27T19:00:00-03:00"
  caption: "..."
  hashtags: ["#tag1", "#tag2", ...]
  media_count: 10
  janela_recomendada: "Ter 19h-21h (vertical B2B)"
validacoes:
  caption_length: 1840
  hashtag_count: 12
  duplicidade: "OK — não há posts similares em 30 dias"
  palavras_banidas: "OK"
proxima_acao: "Aguardar APROVADO do usuário antes de chamar Composio MCP"
```

Após aprovação e execução:

```yaml
status: publicado
post_id: "17912345678901234"
permalink: "https://instagram.com/p/Cxyz123"
publicado_em: "2026-05-27T19:00:14-03:00"
log_registrado: true
```

## Exemplos práticos

### Exemplo 1 — Publicar carrossel gerado anteriormente

Usuário: "Posta o carrossel sobre tráfego pago que a gente fez agora há pouco no @vision.ai amanhã às 19h"

Skill:
1. Recupera caption + 10 slides + hashtags do contexto
2. Valida (1840 char, 12 hashtags, 10 mídias — OK)
3. Calcula que 19h terça é horário de pico B2B
4. Mostra preview de aprovação
5. Após APROVADO, chama `composio.instagram.create_post` com schedule
6. Retorna confirmação + permalink

### Exemplo 2 — Calendário editorial da semana

Usuário: "Tenho 7 carrosséis. Distribui na semana com melhor horário."

Skill:
- Seg 12h30 — Carrossel 1
- Ter 19h00 — Carrossel 2
- Qua 12h30 — Carrossel 3
- Qua 20h00 — Carrossel 4 (segundo do dia, vertical forte)
- Qui 19h00 — Carrossel 5
- Sex 12h00 — Carrossel 6
- Sáb 20h00 — Carrossel 7

Apresenta tabela única para aprovação em lote.

## Limitações / Quando NÃO usar

- **NUNCA** poste sem aprovação humana explícita
- Não use para perfis pessoais não-Business / não-Creator (API exige Business)
- Não use para Stories interativos com enquete/quiz (a API tem limitações severas)
- Não use para responder DMs (essa é função da skill `manychat-claude-dm`)
- Não use para Instagram Threads (skill separada)
- Conta deve estar conectada via Composio/Rube ANTES — não tenta autenticar

## Riscos de banimento e mitigação

- Não postar mais de 25 posts em 24h
- Não usar as MESMAS hashtags em 100% dos posts (rotacionar 30%)
- Não comentar/curtir em massa a partir desta conta automatizada
- Respeitar pause de 30 minutos entre posts agendados

## Integração com outras skills do ZION

- `carrossel-instagram-generator` — produz o conteúdo a postar
- `nano-banana-criativos` — gera as imagens
- `veo-videos` — gera reels
- `brandbook-prompt-system` — aplica identidade
- `manychat-claude-dm` — responde aos DMs gerados pelo post
- `trafego-pago-auditor` — pode disparar boost de post de alto desempenho
