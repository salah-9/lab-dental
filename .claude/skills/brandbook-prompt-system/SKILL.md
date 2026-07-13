---
name: brandbook-prompt-system
description: Use SEMPRE que o usuário mencionar brand book, manual da marca, identidade visual, design system, guia de marca, paleta de cores, tipografia da marca, voz da marca, tom de voz, dos and donts, persona da marca, consistência visual, sistema de design, brand guidelines, criar brand book, estruturar identidade, ou pedir para garantir consistência de marca em prompts e conteúdos. Esta skill converte a identidade da marca em prompt-system reutilizável (brand.md), com paleta HEX, tipografia, voz, persona, elementos gráficos e regras, anexável a qualquer outra skill ou prompt.
---

# Brandbook Prompt System

## Quando usar

Ative SEMPRE que o usuário pedir:
- "Cria um brand book pra minha marca"
- "Quero estruturar minha identidade"
- "Garanta que todo conteúdo siga minha marca"
- "Sistema de design da empresa"
- "Tom de voz para minha marca"
- "Persona da minha marca"
- "Quero um brand.md para anexar nos prompts"
- "Aplica minha identidade nesse conteúdo"

Também ative ANTES de gerar qualquer conteúdo de marca quando o usuário menciona consistência ou quando outras skills (carrossel, criativos, vídeos) vão produzir output que precisa respeitar a marca.

## O que esta skill faz

Esta skill cria um arquivo **`brand.md`** que funciona como **prompt-system permanente** da marca. Esse arquivo é anexável a QUALQUER outro prompt do Claude (ou Nano Banana, Veo, ChatGPT) para garantir consistência absoluta.

A skill também:
- Auditando uma marca existente: extrai brand book de site, posts, materiais
- Criando do zero: guia o usuário com perguntas estratégicas
- Atualizando: revisa, corrige inconsistências e versiona

O `brand.md` cobre 8 dimensões:
1. **Essência** — propósito, missão, posicionamento
2. **Persona da marca** — arquétipo, personalidade
3. **Voz e tom** — vocabulário SIM/NÃO, escala formalidade
4. **Paleta de cores** — HEX, RGB, uso (primária/secundária/apoio/alerta)
5. **Tipografia** — família, hierarquia, uso
6. **Elementos gráficos** — logo, ícones, padrões, ilustração
7. **Fotografia / imagem** — estilo, mood, exemplos
8. **Dos and Donts** — regras explícitas

## Como usar (passo a passo)

### 1. Decidir modo de operação
- **AUDITORIA**: usuário fornece materiais existentes (site, posts, PDF do BB)
- **CRIAÇÃO DO ZERO**: usuário não tem nada e quer estruturar
- **ATUALIZAÇÃO**: já tem `brand.md` e quer iterar

### 2. Para CRIAÇÃO DO ZERO — fazer perguntas-chave

Bateria de perguntas obrigatórias:
- Qual o nome da marca e o que ela vende?
- Para quem (público-alvo em 1 frase)?
- Qual problema resolve?
- Por que escolher você e não o concorrente?
- Se a marca fosse uma pessoa famosa, quem seria? Por quê?
- 3 marcas que você admira (e por quê)
- 3 marcas que você NÃO quer parecer (e por quê)
- 3 palavras que descrevem a marca
- 3 palavras que NÃO descrevem
- Você tem logo? Cores? Fonte? (se sim, anexar)
- Onde a marca aparece? (Instagram, site, apresentações, embalagem?)

### 3. Para AUDITORIA — extrair de materiais existentes
- Coletar URLs, prints, PDF
- Identificar paleta predominante (eyedropper conceitual)
- Identificar tipografia (Whatfontis-style description)
- Mapear tom de voz analisando 10 posts
- Mapear repetições visuais

### 4. Definir arquétipo da marca (12 arquétipos clássicos de Mark & Pearson)

| Arquétipo | Essência | Exemplos |
|-----------|----------|----------|
| Inocente | pureza, otimismo | Coca-Cola, Dove |
| Sábio | conhecimento, verdade | Google, Harvard |
| Explorador | liberdade, descoberta | Jeep, North Face |
| Fora-da-Lei | revolução, ruptura | Harley, Diesel |
| Mago | transformação | Apple, Tesla |
| Herói | coragem, conquista | Nike, FedEx |
| Amante | paixão, intimidade | Chanel, Victoria's |
| Bobo da Corte | diversão | Skol, Old Spice |
| Pessoa Comum | pertencimento | Ikea, Casas Bahia |
| Cuidador | proteção, serviço | Johnson, Volvo |
| Criador | imaginação | Lego, Adobe |
| Soberano | controle, status | Rolex, Mercedes |

### 5. Definir voz com escala 1-10

Eixos a definir:
- Formal (1) ↔ Casual (10)
- Sério (1) ↔ Engraçado (10)
- Respeitoso (1) ↔ Irreverente (10)
- Conservador (1) ↔ Ousado (10)
- Próximo (1) ↔ Aspiracional (10)

### 6. Definir paleta de cores funcional

Estrutura mínima:
- **Primária** (1-2 cores) — dominante, 60% do uso
- **Secundária** (1-2 cores) — 30% do uso
- **Apoio** (1-3 cores) — 10% do uso (acentos)
- **Neutros** (preto, branco, cinzas) — sempre
- **Alerta** (verde sucesso, vermelho erro, amarelo aviso) — funcional

Para cada cor: HEX, RGB, CMYK (se for impressão), nome interno, contexto de uso.

### 7. Definir tipografia

- **Display/Title** — fonte de impacto, hierarquia H1
- **Heading** — H2/H3, mais sóbria
- **Body** — texto corrido, máxima legibilidade
- **Caption/Legal** — fontes pequenas

Especificar: família, pesos disponíveis (regular, medium, bold), uso, alternativa web-safe.

### 8. Gerar o arquivo `brand.md` final

## Formato de saída — Template brand.md

```markdown
# Brand Book — [NOME DA MARCA]
Versão: 1.0 | Atualizado: [data]

> ANEXAR ESTE ARQUIVO COMO CONTEXTO EM TODOS OS PROMPTS QUE GERAM CONTEÚDO DA MARCA.

---

## 1. Essência

**Missão**: [1 frase — o que fazemos no mundo]
**Visão**: [1 frase — onde queremos chegar]
**Propósito**: [1 frase — por que existimos]
**Posicionamento**: [Para [público], somos a [categoria] que [benefício único] porque [razão de acreditar]]
**Promessa**: [1 frase — o que o cliente sempre vai receber]

## 2. Persona da Marca

**Arquétipo principal**: [ex: Mago]
**Arquétipo secundário**: [ex: Sábio]
**Se fosse uma pessoa**: [descrição em 3 linhas]
**Personalidade (5 traços)**: [confiante, criativa, prática, calorosa, irreverente]

## 3. Voz e Tom

**Escala formalidade (1-10)**: [ex: 4 — informal-profissional]
**Escala humor (1-10)**: [ex: 6 — leve, sem palhaçada]
**Escala ousadia (1-10)**: [ex: 7 — opina, tem posição]

### Palavras SIM
[lista 15-20 palavras/expressões que usamos]

### Palavras NÃO
[lista 15-20 que NUNCA usamos]

### Estrutura de frase preferida
- Frases curtas (média 12-18 palavras)
- Verbo no início
- Pronome "você" em 80% dos textos
- Evita: jargão técnico sem explicação, gerúndio, voz passiva

### Exemplos
- BOM: "Você precisa decidir. Hoje."
- RUIM: "É necessário que uma decisão seja tomada por parte do usuário em algum momento oportuno."

## 4. Paleta de Cores

### Primária
- **[Nome]**: #HEX | RGB(r,g,b) — uso em CTAs, logo, destaques principais

### Secundária
- **[Nome]**: #HEX | RGB(r,g,b) — uso em backgrounds, cards

### Apoio
- **[Nome]**: #HEX | RGB(r,g,b) — uso em acentos, ícones

### Neutros
- Preto marca: #HEX
- Off-white: #HEX
- Cinza 100/300/500/700: #HEX

### Funcionais
- Sucesso: #22C55E
- Erro: #EF4444
- Aviso: #F59E0B
- Info: #3B82F6

### Combinações proibidas
[liste pares que NÃO podem aparecer juntos]

## 5. Tipografia

| Nível | Família | Peso | Tamanho | Uso |
|-------|---------|------|---------|-----|
| Display | [família] | Bold 700 | 48-72px | Hero, capas |
| H1 | [família] | Bold 700 | 32-40px | Títulos principais |
| H2 | [família] | Semibold 600 | 24-28px | Subtítulos |
| H3 | [família] | Medium 500 | 20px | Seções |
| Body | [família] | Regular 400 | 16px | Texto corrido |
| Caption | [família] | Regular 400 | 12-14px | Legendas, footnotes |

**Web-safe alternativa**: [se Google Font cair, usar X]

## 6. Elementos Gráficos

- **Logo**: variações (horizontal, vertical, símbolo isolado), espaço de respiro mínimo, tamanho mínimo
- **Ícones**: estilo (linha, fill, duotone), espessura, biblioteca-base (Lucide, Phosphor, Material)
- **Ilustração**: estilo (flat, isométrica, mão livre, 3D)
- **Padrões/Patterns**: descrição se houver
- **Bordas/Cantos**: radius padrão (ex: 8px)
- **Sombras**: estilo (sutil, dura, neumorfismo)

## 7. Fotografia e Imagem

**Mood geral**: [ex: luminoso, próximo, autêntico]
**Iluminação preferida**: [natural lateral suave]
**Cores predominantes nas fotos**: [tons quentes / desaturados / vibrantes]
**Composição**: [centralizada / regra dos terços / minimalista]
**Pessoas mostradas**: [diversidade, faixa etária, vestuário, expressão]
**Cenários**: [ambientes representativos]
**EVITAR**: [stock genérico, poses artificiais, alto contraste agressivo]

**Prompt-padrão para Nano Banana**:
> [string pronta com paleta e estilo já incorporados]

**Prompt-padrão para Veo**:
> [string pronta com mood e iluminação já incorporados]

## 8. Dos and Donts

### FAÇA
- Use verbos no imperativo nos CTAs
- Mostre rosto humano em 60% das imagens
- Coloque o logo com respiro mínimo de 1x altura do símbolo
- Use no máximo 2 famílias tipográficas por peça

### NÃO FAÇA
- Não use o roxo primário com vermelho juntos
- Não use Comic Sans, jamais
- Não escreva títulos em CAIXA-ALTA inteira (apenas palavras pontuais)
- Não use stock genérico de "executivos sorrindo apertando mão"
- Não use gerúndio nos títulos ("Estamos transformando" → "Transformamos")

## 9. Aplicação por canal

| Canal | Adaptação |
|-------|-----------|
| Instagram Feed | Ratio 4:5, paleta cheia, voz casual escala 6 |
| Reels | Vertical 9:16, hook em 1,5s, voz escala 7 |
| LinkedIn | Voz escala 3, tom mais técnico |
| Site/Landing | Tipografia hierárquica clara |
| Email | Voz pessoal, escala 4-5 |
| WhatsApp/DM | Voz escala 8, frases curtíssimas |

## 10. Como usar este documento

1. Anexe este `brand.md` como contexto em QUALQUER prompt de geração de conteúdo
2. Refira por nome: "siga o brand.md anexo"
3. Quando algo for ambíguo, prevalece a regra mais restritiva
4. Atualize a versão quando mudar qualquer item (semver: MAJOR.MINOR.PATCH)
```

## Exemplos práticos

### Exemplo 1 — Marca de consultoria financeira "Próspera"

- Arquétipo: Sábio + Cuidador
- Voz escala: formalidade 5, humor 3, ousadia 4
- Cores primárias: Verde-floresta #0F5132, Areia #E8DCC4
- Tipografia: Inter Bold (títulos) + Inter Regular (corpo)
- Mood foto: pessoas reais, luz natural, ambientes simples
- Don't: nunca usar dólar/dinheiro como ícone principal

### Exemplo 2 — Marca jovem de cosméticos "Brisa"

- Arquétipo: Amante + Inocente
- Voz escala: formalidade 8, humor 6, ousadia 7
- Cores: Rosa-coral #FF6B8A, Bege-rosado #F5E1DC, Verde-menta #B8E0D2
- Tipografia: Playfair Display (títulos) + Inter (corpo)
- Mood foto: pele real, luz suave de fim de tarde, mulheres diversas

## Template em branco para o usuário preencher

Quando o usuário pedir "me dá só o template", entregue o esqueleto do brand.md acima com placeholders `[PREENCHER]` e perguntas guia em comentários.

## Limitações / Quando NÃO usar

- **Não use** para marcas de terceiros sem autorização (compliance + ética)
- **Não use** para "rebrandear" empresa estabelecida sem time de design — entregue como ponto de partida
- **Cuidado** com marcas em setores regulados (saúde, financeiro) — voz precisa passar por compliance
- O brand.md NÃO substitui um brand book profissional completo (com manual de aplicações, mockups, vídeos). É a **versão consumível por IA** dele.

## Integração com outras skills do ZION

Esta skill é a **camada-base** que TODAS as outras de mídia/conteúdo consomem:
- `carrossel-instagram-generator` — usa paleta, tipografia e voz
- `instagram-automation` — usa tom de voz no copy e hashtags
- `manychat-claude-dm` — usa voz da marca na persona do bot
- `nano-banana-criativos` — incorpora paleta e mood em prompts visuais
- `veo-videos` — incorpora mood, iluminação e áudio em prompts de vídeo
- `vision-premium-deck` — aplica identidade em decks
- `email-redator-executivo` — aplica tom de voz em emails
- `proposta-comercial-gerador` — aplica visual e voz em propostas
