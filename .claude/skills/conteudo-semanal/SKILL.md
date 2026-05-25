---
name: conteudo-semanal
description: >
  Planeja e produz os 5 conteúdos semanais da Mayresse Arquitetura para Instagram:
  2 carrosséis, 1 reel (roteiro), 2 posts de feed.
  Entrevista sobre o foco da semana, gera o plano completo com temas e ângulos,
  e produz cada peça com legenda, CTA e hashtags.
  Use quando o usuário pedir "conteúdo da semana", "planejar posts", "5 conteúdos",
  "pauta semanal", "o que postar essa semana" ou similar.
---

# /conteudo-semanal — Planejamento e Produção de Conteúdo

## Antes de começar

Ler:
1. `_contexto/empresa.md` — negócio e público
2. `_contexto/preferencias.md` — tom de voz
3. `_contexto/estrategia.md` — foco atual
4. `marca/mayresse-arquitetura/design-guide.md` — identidade visual e voz da marca

---

## Fase 1 — Briefing da semana

Fazer uma pergunta só:

> "Me conta sobre essa semana: tem algum projeto pra destacar, tema específico, evento, lançamento ou assunto que tá em alta no mercado? Ou quer que eu sugira os temas com base no posicionamento da Mayresse?"

Se o usuário der temas → usar como base.
Se pedir sugestão → propor temas alinhados ao posicionamento da marca (arquitetura autoral, experiência de morar, design contemporâneo, percepção de valor, bastidores de projetos).

---

## Fase 2 — Plano da semana

Montar e apresentar o plano com os 5 conteúdos:

```
SEMANA [DATA]

CARROSSEL 1
Tema: [tema]
Ângulo: [a tese ou opinião forte]
Formato: carrossel educacional/posicionamento
Plataforma: Instagram

CARROSSEL 2
Tema: [tema]
Ângulo: [a tese ou opinião forte]
Formato: carrossel educacional/posicionamento
Plataforma: Instagram

REEL
Tema: [tema]
Ângulo: [gancho + narrativa]
Formato: vídeo curto (30-60s)
Plataforma: Instagram Reels / YouTube Shorts / TikTok

POST DE FEED 1
Tema: [tema]
Ângulo: [frase de impacto ou pergunta]
Formato: imagem única com legenda forte
Plataforma: Instagram

POST DE FEED 2
Tema: [tema]
Ângulo: [frase de impacto ou pergunta]
Formato: imagem única com legenda forte
Plataforma: Instagram
```

Perguntar:
> "O plano tá bom ou quer ajustar algum tema? Se aprovar, qual quer produzir primeiro?"

**CHECKPOINT:** Aguardar aprovação do plano antes de produzir qualquer peça.

---

## Fase 3 — Produção de cada peça

Produzir conforme o tipo escolhido:

### Carrossel

Chamar a skill `/carrossel` com o tema e ângulo definidos no plano.
A pasta de saída segue o padrão: `conteudo/mayresse-arquitetura/carrosseis/semana-[data]-[tema]/`

### Reel (roteiro)

Gerar um roteiro estruturado:

```
REEL — [TEMA]
Duração sugerida: 30-60 segundos

GANCHO (0-3s):
[frase de abertura — tem que parar o scroll]

DESENVOLVIMENTO (3-45s):
[narrativa em blocos curtos — cada bloco = 1 corte visual]
- [ponto 1]
- [ponto 2]
- [ponto 3]

VIRADA (45-55s):
[insight ou revelação que fecha a narrativa]

CTA (55-60s):
[chamada pra ação — curta e direta]

SUGESTÃO VISUAL:
[o que mostrar em cada parte: espaços, projeto, detalhe construtivo, pessoa, texto na tela]

LEGENDA INSTAGRAM:
[legenda completa com gancho nos primeiros 125 caracteres, desenvolvimento e hashtags]
```

Salvar em `conteudo/mayresse-arquitetura/reels/semana-[data]-[tema]/roteiro.md`

### Post de feed

Gerar:
1. **Copy da legenda** — gancho forte nos primeiros 125 caracteres, 2-3 parágrafos, CTA, 5-8 hashtags
2. **Sugestão visual** — descrever o que a imagem deve mostrar (foto de projeto, detalhe, ambiente)
3. **Texto sobreposto** (se aplicável) — frase curta pra colocar sobre a imagem

Salvar em `conteudo/mayresse-arquitetura/carrosseis/semana-[data]-[tema]/post-feed.md`

---

## Fase 4 — Continuar ou encerrar

Após produzir cada peça, perguntar:

> "Próxima peça?"

Se sim, voltar pra Fase 3 com o próximo item do plano.
Se não, salvar o plano da semana completo em `conteudo/mayresse-arquitetura/semana-[data]/plano.md` com o status de cada peça (produzida / pendente).

---

## Regras de texto

- Sem travessões (—)
- Sem cacoetes: "e isso muda tudo", "no fim das contas", "cada vez mais", "simplesmente", "mindset", "ecossistema"
- Sem aberturas genéricas: "hoje vamos falar sobre", "neste post você vai"
- Sem fechamentos fracos: "espero que tenha gostado", "não esqueça de seguir"
- Legenda começa com gancho forte — não com apresentação da marca
- Hashtags sempre no final, nunca no meio do texto
- Tom: elegante, estratégico, contemporâneo — autoridade sem frieza

## Temas recorrentes da Mayresse Arquitetura

Usar como referência quando o usuário pedir sugestão:
- Arquitetura como experiência de vida, não apenas construção
- Morar bem e o que isso significa no contemporâneo
- Bastidores de projetos autorais
- Detalhes construtivos e escolhas de materiais
- Design internacional e referências de comportamento
- Percepção de valor e o que diferencia arquitetura de alto padrão
- O processo criativo por trás de um projeto
