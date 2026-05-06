---
name: carrossel
description: >
  Cria carrosséis completos para Instagram com a identidade visual da marca escolhida.
  Gera texto editorial, HTMLs estilizados e renderiza em PNG via Playwright (1080x1350px).
  Suporta as 3 marcas: Mayresse Arquitetura, Mayresse Lima e Inside Mayresse.
  Use quando o usuário mencionar "carrossel", "carousel", "slides instagram",
  "faz um carrossel", ou pedir pra transformar um tema em carrossel.
---

# /carrossel — Criação de Carrossel

## Setup (primeira vez)

Antes de criar, checar 4 coisas. Se tudo OK, pular pro workflow.

### 1. Marca

Identificar qual das 3 marcas o carrossel é para. Se não estiver claro no pedido, perguntar:

> "Esse carrossel é pra qual marca?
> 1. Mayresse Arquitetura (@mayressearquitetura)
> 2. Mayresse Lima (@mayresse.lima)
> 3. Inside Mayresse (@insidemayresse)"

Conforme a marca escolhida, usar o design guide e pasta de saída correspondentes:

| Marca | Design guide | Pasta de saída |
|---|---|---|
| Mayresse Arquitetura | `marca/mayresse-arquitetura/design-guide.md` | `conteudo/mayresse-arquitetura/carrosseis/[tema]/` |
| Mayresse Lima | `marca/mayresse-lima/design-guide.md` | `conteudo/mayresse-lima/carrosseis/[tema]/` |
| Inside Mayresse | `marca/inside-mayresse/design-guide.md` | `conteudo/inside-mayresse/[tema]/` |

### 2. Estilo de design dos slides

Ler `.claude/skills/carrossel/references/design-carrossel.md`.

Se contiver `<!-- estilo: pendente -->`, perguntar:

> "Como quer o visual dos slides?
> 1. **Minimalista:** limpo, muito espaço em branco, elegante — combina com o DNA da Mayresse
> 2. **Elaborado:** texturas, composições ousadas, impactante no feed
> 3. **Tweet:** simula um post do Twitter, fundo branco, foto de perfil + @handle"

Conforme a resposta, substituir o conteúdo de `design-carrossel.md` pelo arquivo correspondente:
- Minimalista → copiar `references/design-minimalista.md`
- Elaborado → copiar `references/design-elaborado.md`
- Tweet → copiar `references/design-tweet.md`

Se NÃO contiver `<!-- estilo: pendente -->`, o estilo já foi escolhido — não perguntar de novo.

Se escolher **tweet**, perguntar também nome, @handle, foto de perfil e badge verificado. Salvar na seção `## Perfil do autor` do design guide da marca.

**Sugestão padrão:** minimalista (já está configurado e bate com o DNA visual da Mayresse).

### 3. Tom de voz

Ler `_contexto/preferencias.md` — já configurado.

### 4. Playwright

```bash
npx playwright screenshot --help 2>/dev/null && echo "OK" || echo "INSTALAR"
```

Se precisar instalar:
```bash
npx playwright install chromium
```

---

## Dependências

- **Design guide da marca:** conforme tabela acima
- **Regras de design dos slides:** `.claude/skills/carrossel/references/design-carrossel.md`
- **Contexto:** `_contexto/empresa.md`
- **Tom de voz:** `_contexto/preferencias.md`
- **Playwright CLI:** `npx playwright screenshot`

---

## Workflow em 3 Fases

### Fase 1 — Texto

1. Ler `_contexto/preferencias.md` pra calibrar tom
2. Ler `_contexto/empresa.md` pra entender contexto e público
3. Ler o design guide da marca escolhida para entender voz e estilo
4. Se o input for um link, buscar o conteúdo:
   - Links normais: WebFetch direto. Se falhar, usar Jina Reader (`https://r.jina.ai/URL`)
   - Links do X/Twitter: substituir domínio por `api.fxtwitter.com`
   - Links do Instagram: WebFetch não funciona — pedir pro usuário colar o texto
   - Links do YouTube: usar `/yt-transcript` se disponível
5. Se mencionar algo desconhecido, pesquisar antes de escrever — nunca chutar

6. **Briefing rápido** — perguntar numa mensagem só:
   > "Antes de escrever, me confirma:
   > - Quantos slides? (padrão: 8-10)
   > - Vai ter imagem na capa ou dentro dos slides? Se sim, quantas?
   >   - Se tiver: joga na pasta `[pasta-de-saída]/imagens/` e me diz os nomes
   >   - Se não tiver: faço design visual sem foto
   > - CTA do último slide? (ex: 'segue pra mais', 'fala com a gente', 'link na bio')
   > - Tipo: dica, tendência, opinião forte, bastidores, projeto, ou outro?"

   Se o usuário responder tudo junto, usar bom senso pros campos que faltaram.

7. **Planejar a espinha dorsal e mostrar:**

   > **Espinha dorsal do carrossel:**
   >
   > **Ângulo:** [a tese ou opinião forte]
   >
   > **Tensão central:** [a fricção ou dado surpreendente]
   >
   > **Mecanismo:** [por que isso acontece]
   >
   > **Provas:** [2-3 evidências concretas]
   >
   > **Virada:** [o que muda pra quem lê]
   >
   > **5 opções de capa:**
   > A: [título] / [subtítulo]
   > B: [título] / [subtítulo]
   > C: [título] / [subtítulo]
   > D: [título] / [subtítulo]
   > E: [título] / [subtítulo]
   >
   > Qual capa prefere? A narrativa tá no caminho certo?

   **CHECKPOINT 1:** Aguardar aprovação da capa e direção narrativa antes de escrever.

8. **Escrever os slides** seguindo o arco:

   - **Slide 1 (Capa):** capa escolhida no checkpoint
   - **Slide 2 (Hook):** fato ou situação que cria tensão. Termina preparando o próximo
   - **Slides 3-4 (Mecanismo):** por que isso acontece. Dados concretos: número + fonte + ano
   - **Slides 5-7 (Provas):** um ponto por slide, cada um aprofundando uma camada diferente
   - **Slides 8-9 (Virada):** o que isso significa pra quem lê — conexão prática, não resumo
   - **Slide final (CTA):** ação + menção à marca com frase-ponte

   **Regras de texto:**
   - Cada slide é um parágrafo fluido, não lista disfarçada (2-4 frases com conectivos naturais)
   - Artigos sempre presentes: "um espaço", "a arquitetura", "os projetos"
   - Toda afirmação factual: dado + fonte + ano. Se não tiver dado verificável, opinião forte e honesta
   - Sem travessões (—)
   - Sem cacoetes: "e isso muda tudo", "no fim das contas", "cada vez mais", "em um mundo onde", "simplesmente", "basicamente", "ecossistema", "mindset"
   - Sem aberturas genéricas: "hoje vamos falar sobre", "neste carrossel você vai"
   - Sem fechamentos fracos: "continue no próximo", "swipe pra ver mais", "espero que tenha gostado"

9. Gerar legenda Instagram:
   - Gancho nos primeiros 125 caracteres
   - 2-3 parágrafos curtos
   - CTA no final
   - 5-10 hashtags relevantes (incluir hashtags da marca: #mayressearquitetura ou da submarca correspondente)

10. Mostrar texto completo de todos os slides + legenda no chat

11. Salvar em `[pasta-de-saída]/carousel-text.md`

**CHECKPOINT 2:** Aguardar aprovação do texto antes de seguir pro visual.

---

### Fase 2 — Visual (HTMLs + PNGs)

1. Ler o design guide da marca escolhida
2. Ler `.claude/skills/carrossel/references/design-carrossel.md` pra regras de layout
3. Criar HTMLs seguindo as regras — inline CSS only, Google Fonts via `<link>`
4. Salvar em `[pasta-de-saída]/instagram/`
5. Renderizar slide 1 primeiro:
   ```bash
   npx playwright screenshot --viewport-size=1080,1350 --full-page "file:///caminho/absoluto/slide-01.html" "slide-01.png"
   ```

**CHECKPOINT:** Mostrar slide 1. Se aprovado, renderizar os demais. Se pedir ajuste, editar HTML e re-renderizar só aquele.

Salvar PNGs em `[pasta-de-saída]/instagram/`.

---

### Fase 3 — Versão TikTok/Reels vertical (opcional)

Após finalizar o Instagram, perguntar:
> "Quer a versão vertical também? (1080x1920, formato Reels/TikTok/Shorts)"

Se sim:
- Adaptar HTMLs: height 1920px, mais padding, espaçamento ajustado
- Bottom safe zone: 230px livres embaixo (UI do TikTok sobrepõe)
- Renderizar:
  ```bash
  npx playwright screenshot --viewport-size=1080,1920 --full-page "file:///caminho/absoluto/slide-01.html" "slide-01.png"
  ```
- Salvar em `[pasta-de-saída]/tiktok/`

---

## Output final

```
conteudo/[marca]/carrosseis/[tema]/
  carousel-text.md       ← texto aprovado + legenda
  imagens/               ← fotos do usuário (se houver)
  instagram/
    slide-01.html → slide-01.png
    slide-02.html → slide-02.png
    ...
  tiktok/ (se solicitado)
    slide-01.html → slide-01.png
    ...
```

---

## Geração de imagens (se não tiver foto)

### Pollinations.ai (gratuito, sem cadastro)

```bash
curl -L "https://image.pollinations.ai/prompt/[descrição]?width=1080&height=720&nologo=true" -o imagens/foto-01.jpg
```

Mostrar pro usuário aprovar antes de usar no slide. Se não servir, sugerir gerar no Canva, Kling ou Midjourney e jogar na pasta `imagens/`.

---

## Regras

- Texto aprovado no Checkpoint 2 não muda na Fase 2
- Sempre mostrar slide 1 antes de renderizar os demais
- Ajuste no visual = editar HTML + re-renderizar só aquele slide
- Regras de design vivem em `references/design-carrossel.md` — editar lá se quiser mudar o visual
- Se o setup já foi feito antes, não repetir as perguntas — ir direto pro workflow
