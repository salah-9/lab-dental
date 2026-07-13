---
name: nano-banana-criativos
description: Use SEMPRE que o usuário mencionar Nano Banana, Gemini 2.5 Flash Image, gerar imagem com IA, criativo de anúncio, criativo para Meta Ads, mockup de produto, capa de ebook, foto de perfil profissional gerada por IA, ilustração para post, banner, criativo visual, prompt de imagem, imagem para Instagram, design gerado, ou pedir para criar/gerar/desenhar imagem. Esta skill estrutura prompts seguindo a fórmula Sujeito + Ação + Cenário + Estilo + Iluminação + Mood + Detalhe técnico, com templates específicos para anúncio Meta, ebook, mockup, perfil e ilustração.
---

# Nano Banana Criativos

## Quando usar

Ative SEMPRE que o usuário pedir:
- "Gera uma imagem para…"
- "Cria um criativo de anúncio"
- "Quero a capa do meu ebook"
- "Faz um mockup do meu produto"
- "Foto profissional para LinkedIn"
- "Ilustração para post de blog"
- "Banner para o site"
- "Imagem com Nano Banana / Gemini"

Também ative quando outra skill demandar visual (ex: `carrossel-instagram-generator` pedindo imagens para slides).

## O que esta skill faz

Esta skill estrutura **prompts visuais de alta qualidade** para o modelo **Nano Banana (Google Gemini 2.5 Flash Image)**, conhecido por excelência em:
- Realismo fotográfico
- Consistência de personagem entre cenas
- Edição preservando contexto
- Tipografia em imagens (limitada mas melhor que SDXL)

A fórmula que SEMPRE usamos:

```
[Sujeito] + [Ação/Pose] + [Cenário] + [Estilo visual] + [Iluminação] + [Mood] + [Detalhe técnico — câmera/lente]
```

A skill entrega:
- Prompt completo otimizado
- Negative prompt (o que evitar)
- Resolução e ratio sugeridos
- Variantes alternativas (3 opções)
- Pós-processamento recomendado

## Como usar (passo a passo)

### 1. Identificar o tipo de criativo

| Tipo | Ratio | Resolução | Uso |
|------|-------|-----------|-----|
| Anúncio Meta Feed | 1:1 ou 4:5 | 1080x1080 / 1080x1350 | Facebook/Instagram feed |
| Anúncio Stories/Reels | 9:16 | 1080x1920 | Stories, Reels ads |
| Capa de Ebook | 2:3 | 1600x2400 | Capa frontal A4 ou Kindle |
| Mockup de produto | 1:1 ou 4:3 | 2048x2048 / 2048x1536 | E-commerce, página de venda |
| Foto perfil profissional | 1:1 | 1024x1024 | LinkedIn, sites |
| Ilustração post blog | 16:9 | 1920x1080 | Header de artigo |
| Banner site (hero) | 21:9 ou 16:9 | 2560x1080 | Landing pages |

### 2. Preencher os 7 elementos da fórmula

**Sujeito**: quem/o que está na imagem. Específico (idade, gênero, etnia, vestuário, expressão).
- Ruim: "uma mulher"
- Bom: "mulher brasileira, 32 anos, cabelo castanho ondulado na altura dos ombros, blazer bege sobre camiseta branca, expressão confiante"

**Ação/Pose**: o que está fazendo.
- "segurando notebook aberto, gesticulando com a mão direita como em explicação"

**Cenário**: onde está.
- "escritório moderno minimalista, paredes brancas, mesa de madeira clara, plantas ao fundo desfocadas"

**Estilo visual**: tipo de imagem.
- Opções: "fotografia editorial", "ilustração flat", "3D render", "pintura digital", "estilo Pixar", "fotorrealismo cinematográfico", "ilustração linha fina minimalista"

**Iluminação**:
- "luz natural lateral suave de janela ao lado direito", "luz dourada de fim de tarde", "luz dura de estúdio com rim light azul", "iluminação volumétrica de neon roxo"

**Mood**:
- "atmosfera profissional e acolhedora", "energético e vibrante", "calmo e contemplativo", "futurista e tecnológico", "luxuoso e sofisticado"

**Detalhe técnico (câmera/lente)**:
- "Canon EOS R5, lente 85mm f/1.4, profundidade de campo rasa, foco no rosto"
- "shot em iPhone 15 Pro, estilo UGC, levemente granulado"
- "RED Komodo, lente anamórfica 50mm, bokeh oval"

### 3. Aplicar template específico (próxima seção)

### 4. Gerar negative prompt (o que NÃO queremos)
- "sem texto distorcido, sem mãos deformadas, sem watermark, sem rosto borrado, sem objetos flutuantes"

### 5. Sugerir variantes
Sempre entregar 3 versões: uma "segura", uma "criativa", uma "ousada".

## Templates por tipo de criativo

### Template 1 — Criativo de Anúncio Meta (Feed 1:1)

```
[Sujeito real do público-alvo, expressão emocional clara conectada à dor/desejo],
[ação que ilustra o benefício do produto],
[cenário que reforça o nicho — ex: escritório, cozinha, academia],
estilo fotografia comercial Meta Ads, alto contraste, cores saturadas,
iluminação dura frontal + rim light colorido,
mood [emoção desejada — sucesso, alívio, descoberta],
shot em Sony A7IV, lente 50mm f/1.8, foco no sujeito,
1:1, 1080x1080, 8K detalhe.

Negative: texto distorcido, mãos deformadas, marca d'água, rosto múltiplo.
```

### Template 2 — Capa de Ebook

```
Capa de ebook profissional,
[título do ebook em tipografia bold sans-serif centralizado],
fundo [gradiente cor da marca / cena conceitual relacionada ao tema],
[elemento visual simbólico do tema — ex: lâmpada para ideias, gráfico para finanças],
estilo design editorial limpo, hierarquia clara,
iluminação suave, mood premium e confiável,
ratio 2:3, 1600x2400, formato para Kindle e A4.

Negative: tipografia tremida, layout desalinhado, mais de 2 famílias de fonte.
```

### Template 3 — Mockup de Produto

```
Mockup fotorrealista de [produto detalhado — material, cor, dimensões],
posicionado em [superfície — mármore branco, madeira clara, fundo seamless cinza],
[opcional: elementos secundários — folha de planta, xícara, livro],
estilo product photography premium e-commerce,
iluminação softbox principal a 45° + fill light + reflexo no chão,
mood limpo e desejável,
shot em Hasselblad H6D, lente macro 100mm f/4, foco total no produto,
1:1, 2048x2048, sombras realistas.

Negative: produto distorcido, logotipo borrado, perspectiva errada.
```

### Template 4 — Foto de Perfil Profissional

```
Retrato profissional de [pessoa: gênero, idade, etnia, traços],
vestindo [look profissional — blazer, camisa social],
olhando diretamente para câmera com sorriso natural confiante,
fundo desfocado em tom neutro [cinza claro / off-white / azul-marinho],
estilo headshot corporativo LinkedIn premium,
iluminação butterfly (luz frontal alta) + reflector inferior,
mood acessível, competente, confiável,
shot em Canon EOS R5, lente 85mm f/1.8, bokeh suave,
1:1, 1024x1024, pele com textura natural preservada.

Negative: pele plástica, olhos assimétricos, dentes deformados, beleza artificial exagerada.
```

### Template 5 — Ilustração para Post de Blog

```
Ilustração [flat / line art / isométrica] sobre [tema],
composição [centralizada / em diagonal / com hierarquia clara],
paleta de cores [do brand book — ex: azul-marinho, coral, off-white],
estilo editorial moderno tipo Notion/Linear,
iluminação plana sem sombras duras,
mood [didático / inspiracional / técnico],
ratio 16:9, 1920x1080, vetorial limpo.

Negative: realismo fotográfico, sombras pesadas, gradientes ruidosos.
```

## Formato de saída

```markdown
# Criativo: [nome do projeto]

## Tipo: [anúncio Meta / capa ebook / mockup / perfil / ilustração]
## Ratio: [X:Y] — Resolução: [WxH]

## PROMPT PRINCIPAL
[prompt completo aplicando a fórmula]

## NEGATIVE PROMPT
[elementos a evitar]

## VARIANTE A — Segura
[versão conservadora]

## VARIANTE B — Criativa
[versão com twist]

## VARIANTE C — Ousada
[versão experimental]

## PÓS-PROCESSAMENTO RECOMENDADO
- Ajuste de cor: [ex: aumentar saturação 10%]
- Crop: [se necessário]
- Texto sobreposto: [se aplicável, em qual ferramenta — Canva/Figma]

## CHECKLIST DE QUALIDADE
- [ ] Sujeito reconhecível e bem-posicionado
- [ ] Iluminação coerente
- [ ] Sem deformações nas mãos/rosto
- [ ] Ratio correto para uso final
- [ ] Aderência ao brand book (se aplicável)
```

## Exemplos práticos

### Exemplo 1 — Anúncio Meta para curso de inglês

```
Mulher brasileira, 28 anos, cabelo cacheado preso, fone de ouvido sobre cabeça,
olhando para notebook com expressão de descoberta e sorriso aberto,
sentada em sofá bege em sala com luz natural,
estilo fotografia comercial Meta Ads, alto contraste, cores quentes,
luz dourada lateral de janela à esquerda + leve rim light atrás,
mood de conquista e leveza,
shot em Sony A7IV, lente 50mm f/1.8, foco nos olhos,
1:1, 1080x1080.
```

### Exemplo 2 — Mockup de garrafa de suplemento

```
Mockup fotorrealista de pote preto fosco de suplemento, label dourado minimalista,
posicionado em superfície de mármore preto,
ao lado folha de eucalipto e medidor de aço inox,
estilo product photography premium,
iluminação softbox 45° + fill suave + reflexo sutil no mármore,
mood premium e confiável,
shot em Hasselblad, macro 100mm f/4,
1:1, 2048x2048.
```

## Limitações / Quando NÃO usar

- **Não use** Nano Banana para vídeo (use skill `veo-videos`)
- **Não use** para gerar texto longo na imagem — IA ainda erra ortografia em prompts longos
- **Não use** para imagens de pessoas reais conhecidas (questão ética + legal)
- **Cuidado** com nichos regulados (saúde, financeiro) — imagens de "antes/depois" podem violar políticas Meta
- Para variações exatas do mesmo personagem entre múltiplas cenas, use o recurso de **consistência de personagem** do Nano Banana fornecendo imagem de referência

## Integração com outras skills do ZION

- `carrossel-instagram-generator` — gera imagens para cada slide
- `instagram-automation` — publica as imagens
- `veo-videos` — animar imagens estáticas em vídeo
- `brandbook-prompt-system` — aplicar paleta e estilo da marca em TODOS os prompts
- `trafego-pago-auditor` — gerar variações criativas para testes A/B
- `vision-premium-deck` — gerar imagens para slides de apresentação
