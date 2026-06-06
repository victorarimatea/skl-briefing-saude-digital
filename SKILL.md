---
name: briefing-saude-digital
description: >
  Gera um briefing completo e atualizado sobre saúde digital para o Diretor de Transformação Digital.
  Use esta skill SEMPRE que o usuário pedir: "briefing", "me atualize", "o que tem de novo", "novidades de hoje",
  "resumo do dia", "me passa o briefing", ou qualquer variação que indique que ele quer ser atualizado sobre
  saúde digital, transformação digital em saúde, healthtech, regulações de saúde, ou tendências do setor.
  Também deve ser ativada para pedidos de "resumo semanal" ou "resumo mensal" de saúde digital.
  Nunca responda esses pedidos sem antes executar esta skill.
  Esta skill depende da skill taxonomia-saude-digital — sempre carregar a taxonomia do GitHub antes de montar o briefing.
version: "v1.0"
---

# Briefing — Saúde Digital

**Versão:** v1.0 — 2026-06-04
**Repositório:** https://github.com/victorarimatea/skl-briefing-saude-digital
**Mantenedor:** victorarimatea
**Tipo:** S (Skill)
**ID:** S07

---

## Contexto

O usuário é **Diretor de Transformação Digital** na área da saúde. Ele precisa de um briefing periódico
(1–2x por dia) para nunca ser pego de surpresa por notícias, regulações, movimentos de mercado ou
avanços tecnológicos relevantes em saúde digital.

**Idiomas de busca:** Português e inglês.
**Idioma de entrega:** Sempre em português. Fontes em inglês são resumidas em PT com link original.
**Formato:** Mobile-first — seções claras, textos curtos, links clicáveis.

---

## Passo 0 — Carregar a Taxonomia (OBRIGATÓRIO)

**Antes de qualquer busca**, carregar a taxonomia vigente do GitHub:

```
https://raw.githubusercontent.com/victorarimatea/mat-saude-digital-taxonomia/main/taxonomia.md
```

Ler e manter em contexto a estrutura completa de partes, capítulos e subtópicos.
Esta taxonomia será usada para classificar cada item do briefing com tags `🏷️`.

> Se o fetch falhar, prosseguir com o briefing e sinalizar ao final:
> ⚠️ *"Taxonomia não carregada — itens sem tag neste briefing."*

---

## Gestão de Histórico e Continuidade

Esta skill foi projetada para funcionar em **conversa única contínua**, acumulando histórico de todos os briefings anteriores. Isso permite rastreamento de temas, detecção de repetições e relatórios consolidados.

### Antes de cada briefing: verificar o histórico

1. **Identificar a data do último briefing** na conversa. Se não houver briefing anterior, tratar como primeiro acesso.
2. **Calcular o gap** entre o último briefing e hoje:
   - Gap de 1 dia → janela de busca normal (últimas 24–48h)
   - Gap de 2–4 dias → ampliar janela para cobrir todos os dias perdidos; mencionar no briefing: *"Cobrindo [N] dias desde o último briefing ([data])"*
   - Gap de 5+ dias → ampliar para a semana completa; entregar briefing no formato semanal automaticamente
3. **Verificar temas recorrentes**: se um item encontrado já apareceu em briefing anterior, sinalizá-lo com 🔁 e indicar quando foi a primeira menção. Isso evita redundância e mostra evolução do tema.

### Comandos de histórico disponíveis

O usuário pode pedir a qualquer momento:

- *"Todas as vezes que [tema] apareceu"* → listar cronologicamente todas as menções ao tema nos briefings anteriores da conversa
- *"Relatório de [tema] do mês"* → consolidar todas as entradas de um tema em um mini-relatório com linha do tempo
- *"Destaque de cada briefing"* → listar apenas os itens "Destaque do Dia" de todos os briefings anteriores
- *"O que mudou sobre [tema] desde [data]?"* → comparar o estado do tema entre dois momentos
- *"Monta o resumo mensal"* → gerar briefing mensal consolidando todos os briefings do mês corrente
- *"Quais tópicos da taxonomia mais apareceram este mês?"* → contar frequência de tags `🏷️` nos briefings da conversa e rankear os top 10 tópicos

### Início de novo ciclo mensal

Conversas muito longas podem atingir limites de contexto. A cada início de mês, o usuário pode abrir uma nova conversa. Nesse caso, orientar o usuário a começar com:
> *"Continuando o monitoramento de saúde digital. Resumo do mês anterior: [colar o briefing mensal gerado]"*

Isso preserva a continuidade temática sem perder o fio histórico.

---

## Instruções de Execução

### 1. Carregar taxonomia (ver Passo 0 acima)

### 2. Realizar as buscas

Execute buscas simultâneas cobrindo os 4 temas abaixo. Use termos em PT e EN.
Priorize fontes dos **últimos 7 dias**. Para regulações, aceite até 30 dias.
**Adapte a janela temporal** conforme o gap calculado na seção de histórico acima.

**Queries sugeridas por tema** (adapte conforme o dia/contexto):

**📰 Notícias & Publicações**
- `saúde digital notícias 2026`
- `digital health news today`
- `healthtech Brasil novidades`
- `transformação digital saúde publicações recentes`

**⚖️ Regulações & Políticas**
- `ANVISA regulação saúde digital`
- `CFM telemedicina resolução`
- `LGPD saúde dados 2026`
- `RNDS interoperabilidade atualização`
- `FDA digital health guidance 2026`
- `WHO digital health policy`

**📈 Mercado & Negócios**
- `healthtech investimento Brasil 2026`
- `healthtech startup funding 2026`
- `fusão aquisição saúde digital`
- `digital health market trends`

**💻 Tecnologia**
- `inteligência artificial saúde 2026`
- `AI healthcare breakthrough`
- `prontuário eletrônico interoperabilidade`
- `telemedicina tecnologia inovação`
- `wearables saúde lançamento`

### 3. Filtrar e selecionar

Para cada tema, selecione **3 a 5 itens** mais relevantes e recentes.
Priorize: fontes oficiais, grandes veículos, publicações científicas, anúncios de empresas relevantes.
Descarte: conteúdo antigo (>30 dias sem relevância especial), clickbait, repetições.

### 4. Classificar cada item na taxonomia

Para cada item selecionado, identificar os **1 a 3 códigos taxonômicos** mais relevantes da taxonomia carregada no Passo 0.

**Regras de classificação:**
- Usar o código mais específico disponível (subtópico X.Y, não apenas o capítulo X)
- Quando um item se encaixa em mais de um tópico, listar todos — separados por ` · `
- Em caso de dúvida entre dois tópicos, escolher o mais próximo do assunto central da notícia
- Máximo de 3 tags por item para manter clareza

**Exemplo:**
> Notícia sobre FDA aprovando algoritmo de IA para leitura de ECG → `🏷️ 3.1 · 3.5 · 18.2`

### 5. Montar o briefing

Use exatamente o formato abaixo. Mantenha textos curtos — o usuário lê no celular.

---

## Formato de Output

```
📋 BRIEFING — SAÚDE DIGITAL
[Data de hoje, por extenso]
[Se gap > 1 dia: "📅 Cobrindo [N] dias — desde o briefing de [data anterior]"]

━━━━━━━━━━━━━━━━━━━━━━━━━━━

📰 NOTÍCIAS & PUBLICAÇÕES

• [🔁 se tema já apareceu antes] [Título resumido em PT]
  [1–2 frases explicando o que é e por que importa]
  [Se 🔁: "(primeira menção: [data])"]
  🏷️ [código1] · [código2]
  🔗 [Link]

• [próximo item...]

━━━━━━━━━━━━━━━━━━━━━━━━━━━

⚖️ REGULAÇÕES & POLÍTICAS

• [Título resumido em PT]
  [1–2 frases explicando o que é e por que importa para o setor]
  🏷️ [código1] · [código2]
  🔗 [Link]

━━━━━━━━━━━━━━━━━━━━━━━━━━━

📈 MERCADO & NEGÓCIOS

• [Título resumido em PT]
  [1–2 frases: quem, quanto, impacto]
  🏷️ [código1] · [código2]
  🔗 [Link]

━━━━━━━━━━━━━━━━━━━━━━━━━━━

💻 TECNOLOGIA

• [Título resumido em PT]
  [1–2 frases: o que é, maturidade, relevância prática]
  🏷️ [código1] · [código2]
  🔗 [Link]

━━━━━━━━━━━━━━━━━━━━━━━━━━━

💡 DESTAQUE DO DIA
[Um parágrafo curto (3–5 frases) com o item mais estratégico do briefing — aquele que o Diretor de
Transformação Digital definitivamente não pode ignorar hoje. Explique por quê é o mais relevante.]
🏷️ [códigos do item destaque]

━━━━━━━━━━━━━━━━━━━━━━━━━━━

🗂️ ÍNDICE TAXONÔMICO DO BRIEFING
[Lista compacta de todos os códigos utilizados neste briefing, agrupados por Parte da taxonomia]
Ex:
  Parte II — Tecnologias Habilitadoras: 3.1, 3.3, 3.5, 4.2, 5.1
  Parte VII — Regulação, Mercado e Inovação: 18.2, 19.2

━━━━━━━━━━━━━━━━━━━━━━━━━━━
🔄 Próximo briefing: [manhã/tarde, dependendo do horário atual]
```

---

## Variações de Pedido

### Briefing semanal
Se o usuário pedir *"resumo da semana"* ou *"briefing semanal"*:
- Aumente para 5–7 itens por seção
- Adicione uma seção extra: **📊 PANORAMA DA SEMANA** com 1 parágrafo analítico por tema
- Adicione: **📊 TOP TÓPICOS DA SEMANA** — os 5 códigos taxonômicos que mais apareceram
- Título: `📋 BRIEFING SEMANAL — SAÚDE DIGITAL`

### Briefing mensal
Se o usuário pedir *"resumo do mês"* ou *"briefing mensal"*:
- Foque nos 3 movimentos mais importantes por seção
- Adicione: **🗓️ LINHA DO TEMPO DO MÊS** — lista cronológica dos principais eventos
- Adicione: **📊 MAPA TAXONÔMICO DO MÊS** — ranking dos tópicos mais movimentados com contagem de aparições
- Ideal para compartilhar com equipe ou liderança

### Busca por tema no histórico
Se o usuário pedir *"todas as vezes que [tema] apareceu"* ou *"o que temos sobre [tema]"*:
- Percorra todos os briefings anteriores na conversa
- Liste cronologicamente cada aparição: data, seção, título, tag e link
- Finalize com um parágrafo de síntese: como o tema evoluiu ao longo do tempo

### Busca por tópico taxonômico
Se o usuário pedir *"tudo que temos sobre o tópico 3.1"* ou *"o que apareceu em [código]"*:
- Percorrer todos os briefings anteriores na conversa
- Listar todos os itens que receberam aquela tag, em ordem cronológica
- Útil para montar dossiês temáticos

### Relatório consolidado
Se o usuário pedir *"relatório de [tema]"* ou *"resumo de todos os destaques"*:
- Agrupe todas as entradas relevantes por subtema
- Inclua linha do tempo e tags taxonômicas
- Formato ideal para compartilhar com equipe ou liderança
- Faça buscas adicionais sobre aquele item específico
- Entregue um mini-relatório de 1 página com contexto, impacto e próximos passos possíveis

---

## Notas de Qualidade

- **Nunca invente notícias.** Se não encontrar resultado recente para um tema, diga: *"Nada relevante encontrado nas últimas 24h nesta categoria."*
- **Sempre inclua o link.** Item sem link não entra no briefing.
- **Sempre inclua a tag 🏷️.** Item sem classificação taxonômica não entra no briefing (salvo falha de fetch da taxonomia).
- **Traduza títulos** em inglês para PT, mas preserve o link original.
- **Tom:** Direto, executivo. Sem enrolação. O usuário é especialista — não precisa de explicações básicas.
- **Destaque do Dia** deve ter opinião editorial genuína — não repita um item aleatório, escolha o mais estratégico de verdade.
