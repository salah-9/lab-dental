---
name: veo-videos
description: Use SEMPRE que o usuário mencionar Veo, Google Veo, gerar vídeo com IA, criar vídeo, vídeo de produto, reel orgânico, ads de tráfego em vídeo, depoimento simulado, criativo em vídeo, vídeo cinematográfico, vídeo UGC, animar imagem, transformar foto em vídeo, prompt de vídeo, ou pedir para fazer/produzir vídeo curto. Esta skill estrutura prompts para Veo seguindo Cena + Movimento de câmera + Duração + Estilo + Iluminação + Áudio, com templates para ads, reels, vídeo produto e depoimento, mais boas práticas de edição e legendagem.
---

# Veo Videos

## Quando usar

Ative SEMPRE que o usuário pedir:
- "Gera um vídeo de…"
- "Quero um reel sobre…"
- "Faz um ad em vídeo para Meta/TikTok"
- "Cria um vídeo de produto"
- "Anima essa imagem"
- "Quero um depoimento simulado"
- "Vídeo cinematográfico curto"
- "Prompt para o Veo"

Também ative quando o usuário tem uma imagem (gerada por `nano-banana-criativos`) e quer animar.

## O que esta skill faz

Esta skill estrutura **prompts de geração de vídeo** para o modelo **Veo (Google)**, com fórmula consolidada:

```
[Cena descrita] + [Movimento de câmera] + [Duração] + [Estilo] + [Iluminação] + [Áudio sugerido]
```

Entrega:
- Prompt principal estruturado
- Variações por estilo (cinematográfico, UGC, comercial)
- Plano de edição pós-Veo (cortes, transições, legenda)
- Especificação técnica (duração, ratio, FPS)
- Sugestão de trilha/SFX

## Como usar (passo a passo)

### 1. Definir o objetivo do vídeo

| Objetivo | Duração ideal | Plataforma alvo |
|----------|---------------|-----------------|
| Ad performance | 5-15s | Meta, TikTok, YouTube Shorts |
| Reel orgânico | 7-30s | Instagram, TikTok |
| Vídeo produto | 10-20s | E-commerce, landing |
| Depoimento simulado | 15-30s | Funil de aquecimento |
| Vídeo institucional | 30-60s | Site, LinkedIn |
| Hero de landing | 5-10s loop | Hero section silenciosa |

### 2. Preencher os 6 elementos

**Cena descrita** — sujeito + ação + cenário em uma frase rica.
- Ruim: "homem usando produto"
- Bom: "Empresário brasileiro de 35 anos, camisa social azul, abre laptop sobre mesa de madeira em escritório com vista para janela ao amanhecer"

**Movimento de câmera** — escolha intencional:
- `dolly in` (aproximação suave) — revelar detalhe
- `dolly out` (afastamento) — revelar contexto
- `pan left/right` — varredura horizontal
- `tilt up/down` — varredura vertical
- `tracking shot` — câmera acompanha o sujeito
- `static` — sem movimento (vídeo estilo entrevista)
- `orbital` — câmera circula o produto (ideal mockup)
- `whip pan` — corte com pan rápido (energia)
- `crane up` — câmera sobe (grandiosidade)

**Duração** — 5, 8, 10, 15 segundos (Veo gera blocos curtos).

**Estilo** — define a "cara":
- `cinematográfico` — anamórfico, color grading filme
- `comercial` — clean, alto contraste, cores saturadas
- `UGC` — vertical, levemente granulado, autêntico
- `documental` — natural, sem polimento exagerado
- `editorial fashion` — alto fashion, poses estáticas
- `tech minimalista` — branco e neon, futurista

**Iluminação**:
- "luz natural lateral suave"
- "luz dura de estúdio com gel azul"
- "golden hour à direita"
- "luz volumétrica de neon no chão"
- "iluminação prática (luminárias visíveis na cena)"

**Áudio sugerido** (Veo 3+ gera áudio nativo):
- "trilha lo-fi suave"
- "house upbeat 110 BPM com kick marcado"
- "som ambiente de escritório + cliques de teclado"
- "voz feminina, tom confiante, fala: 'Você merece mais'"
- "silêncio dramático com risers crescendo"

### 3. Aplicar template específico

## Templates por tipo de vídeo

### Template 1 — Ad de Tráfego (Meta/TikTok)

```
[Sujeito do público-alvo] [vivendo a dor por 2s] e então [descobrindo a solução por 3s]
e [reagindo positivamente por 3s, mostrando o resultado por 5s — 13s total],
movimento de câmera: corte de close estático para tracking shot conforme reação,
duração 15s,
estilo comercial alto contraste cores saturadas,
iluminação dura frontal com rim light colorido,
áudio: música upbeat 120 BPM + voiceover feminino 'A solução estava aqui' nos últimos 4s,
ratio 9:16, 1080x1920, 30fps.
```

### Template 2 — Reel Orgânico (Instagram)

```
[Cena cotidiana relatable do público] com [pequeno detalhe inesperado/cômico],
movimento de câmera handheld natural com leve shake autêntico,
duração 10s,
estilo UGC granulado autêntico tipo gravado em iPhone,
iluminação natural ambiente sem setup,
áudio: trend sonora ou diálogo curto com gancho na primeira palavra,
ratio 9:16, 1080x1920, 30fps,
mood acolhedor próximo do espectador.
```

### Template 3 — Vídeo de Produto (e-commerce)

```
[Produto detalhado — material, cor, tamanho] em [superfície premium combinando com brand],
movimento de câmera orbital 360° lento e suave,
duração 8s loop perfeito,
estilo product cinematic premium,
iluminação softbox principal + 2 fills + rim light dourado,
áudio: ambient cinematic crescendo sutil,
ratio 1:1, 1920x1920, 60fps (slow motion suave),
foco macro nos detalhes texturais.
```

### Template 4 — Depoimento Simulado

```
[Pessoa do perfil do cliente ideal — idade, gênero, etnia, vestuário casual],
sentada em casa/escritório com fundo desfocado natural,
olhando ligeiramente fora da câmera (como em entrevista),
gesticulando moderadamente enquanto fala,
movimento de câmera: static com leve breath shake,
duração 15s,
estilo documental entrevista,
iluminação natural de janela à esquerda + softbox leve à direita,
áudio: voz [feminina/masculina, sotaque brasileiro neutro] dizendo: '[script de 30-40 palavras]',
ratio 9:16, 1080x1920, 30fps,
mood sincero e próximo.

IMPORTANTE: deixar claro na publicação que é dramatização (compliance Meta).
```

### Template 5 — Hero de Landing Page

```
[Cena conceitual abstrata relacionada à promessa do produto],
movimento de câmera: dolly in lento e contínuo,
duração 6s em loop perfeito (frame inicial = frame final),
estilo cinematic minimalista,
iluminação volumétrica suave,
áudio: nenhum (vídeo será mutado por padrão na landing),
ratio 16:9, 1920x1080, 30fps,
mood premium e contemplativo.
```

## Boas práticas de edição pós-Veo

1. **Corte inicial** — sempre cortar 0,3-0,5s do início (Veo abre meio "frio")
2. **Hook visual nos primeiros 1,5s** — Reels/TikTok decidem retenção aí
3. **Legendas grandes e centralizadas** — 70% assiste sem som
4. **Transições por J-cut/L-cut** se combinar clips — som puxa o próximo
5. **Color grading consistente** — usar LUT da marca (se houver) no DaVinci/Premiere/CapCut
6. **Final com CTA visual** — 1-2 últimos segundos: texto + logo + ação
7. **Exportar em H.264 8-12 Mbps** — qualidade alta sem bloat

### Ferramentas de edição recomendadas
- **CapCut** — rápido, ideal para Reels/TikTok
- **Premiere Pro** — pipeline profissional
- **DaVinci Resolve** — color grading avançado
- **Descript** — corte por transcrição (rapidíssimo)

## Formato de saída

```markdown
# Vídeo Veo: [nome do projeto]

## Objetivo: [ad/reel/produto/depoimento/hero]
## Plataforma: [Meta/TikTok/YouTube/Site]
## Ratio + Duração: [9:16 / 15s]

## PROMPT VEO
[prompt completo]

## VARIANTE A — [estilo 1]
## VARIANTE B — [estilo 2]
## VARIANTE C — [estilo 3]

## PLANO DE EDIÇÃO PÓS-VEO
1. Cortar [X]s do início
2. Adicionar legenda: "[texto]"
3. Transição: [tipo]
4. Trilha sonora: [sugestão de track]
5. CTA final: "[texto + cor]"

## EXPORTAÇÃO
- Codec: H.264
- Bitrate: 10 Mbps
- FPS: 30 ou 60
- Audio: AAC 192 kbps

## CHECKLIST
- [ ] Hook nos primeiros 1,5s
- [ ] Legenda legível
- [ ] CTA claro no final
- [ ] Brand element visível (logo/cor)
- [ ] Compliance da plataforma
```

## Exemplos práticos

### Exemplo 1 — Ad de curso online

```
Mulher brasileira 30 anos sentada com notebook em sofá olhando frustrada para tela por 2s,
expressão muda para descoberta ao clicar em algo por 3s,
sorri amplamente e levanta os braços comemorando por 3s,
mostra notebook com gráfico crescente para câmera por 7s,
câmera: estática close-up que abre para plano médio na comemoração,
duração 15s,
estilo comercial Meta Ads,
luz natural de janela + leve rim light,
áudio: música upbeat house 118 BPM + voz feminina 'Eu mudei minha vida em 90 dias' nos últimos 4s,
9:16, 1080x1920, 30fps.
```

### Exemplo 2 — Produto: tênis esportivo

```
Tênis esportivo preto e neon verde flutuando ligeiramente sobre superfície de concreto polido,
câmera: órbita 360° lenta no eixo Y,
duração 8s loop perfeito,
estilo product cinematic Nike-like,
luz softbox 3 pontos + rim light verde acompanhando a cor do tênis,
áudio: synth ambient cinematic crescendo,
1:1, 1920x1920, 60fps slow motion,
foco macro detalhes do solado e malha.
```

## Limitações / Quando NÃO usar

- **Não use** para vídeos com diálogo longo entre múltiplas pessoas — Veo ainda tem limites
- **Não use** para conteúdo que precisa replicar marca registrada visualmente (logos exatos)
- **Cuidado** com depoimentos: SEMPRE deixar claro que é dramatização (lei + políticas Meta/TikTok)
- **Não use** para vídeos longos (> 60s) — Veo é otimizado para shorts; para institucional longo use ferramentas como Runway + edição manual
- **Não substitua** atores reais quando o cliente exigir autenticidade verificável (UGC nativo)
- Verificar limites de uso comercial dependendo do plano Veo contratado

## Integração com outras skills do ZION

- `nano-banana-criativos` — gerar primeiro frame ou keyframes
- `carrossel-instagram-generator` — vídeo pode ser o slide 1 (capa animada)
- `instagram-automation` — publicar como reel
- `brandbook-prompt-system` — manter consistência visual/sonora
- `trafego-pago-auditor` — gerar variantes para teste A/B em campanhas
- `vision-premium-deck` — animação de capa de apresentação
