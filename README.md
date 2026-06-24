# skl-briefing-saude-digital

**Versão:** v1.1 — 2026-06-24
**Tipo:** S07 — Skill
**Mantenedor:** victorarimatea
**Visibilidade:** Público
**Status:** Ativo

---

## O que é esta skill

Skill de inteligência periódica em saúde digital para o Diretor de Transformação Digital
da DTD/SETIS/SES-DF. Gera um briefing estruturado, atualizado e classificado
taxonomicamente sobre novidades em saúde digital — cobrindo notícias, regulações,
mercado e tecnologia. Projetada para uso 1–2x por dia, mobile-first, com gestão
de histórico contínuo dentro da conversa.

---

## O que o briefing entrega

Cada execução produz quatro seções de monitoramento e dois blocos editoriais:

| Seção | Conteúdo |
|---|---|
| 📰 Notícias & Publicações | Novidades do setor — fontes brasileiras e internacionais |
| ⚖️ Regulações & Políticas | ANVISA, CFM, LGPD, RNDS, FDA, OMS |
| 📈 Mercado & Negócios | Investimentos, fusões, movimentos de healthtechs |
| 💻 Tecnologia | IA na saúde, interoperabilidade, wearables, telemedicina |
| 💡 Destaque do Dia | Item mais estratégico do briefing — com análise editorial genuína |
| 🗂️ Índice Taxonômico | Todos os códigos M02 utilizados, agrupados por Parte da taxonomia |

Cada item recebe obrigatoriamente entre 1 e 3 tags taxonômicas (`🏷️ 3.1 · 3.5 · 18.2`).
Item sem tag não entra no briefing.

---

## Diferencial de design: gestão de histórico

A skill foi projetada para funcionar em **conversa única contínua**, acumulando o
histórico de todos os briefings anteriores. Isso habilita:

- **Detecção de recorrência** — temas que reaparecem são sinalizados com 🔁
- **Ajuste automático de janela** — gap de dias sem briefing amplia a busca automaticamente
- **Comandos de histórico** — consultas sobre o acumulado de sessões anteriores

### Comandos disponíveis

| Comando | O que faz |
|---|---|
| *"todas as vezes que [tema] apareceu"* | Lista cronológica de todas as menções ao tema |
| *"relatório de [tema]"* | Mini-relatório com contexto, linha do tempo e impacto |
| *"tudo que temos sobre o tópico 3.1"* | Todos os itens com aquela tag taxonômica |
| *"destaque de cada briefing"* | Lista os Destaques do Dia de todos os briefings anteriores |
| *"o que mudou sobre [tema] desde [data]"* | Comparação entre dois momentos |
| *"monta o resumo mensal"* | Briefing mensal consolidado do mês corrente |
| *"quais tópicos mais apareceram este mês"* | Ranking dos top 10 códigos taxonômicos |

---

## Dependências

| ID | Repositório | Papel |
|---|---|---|
| M02 | `mat-saude-digital-taxonomia` | Taxonomia carregada obrigatoriamente antes de cada briefing |
| — | Ferramenta de busca web | Necessária para execução das queries de monitoramento |

---

## Como acionar

Cole no início da conversa do Claude:

```
Leia https://raw.githubusercontent.com/victorarimatea/skl-briefing-saude-digital/main/SKILL.md
e execute o briefing de hoje.
```

Ou simplesmente peça: *"me passa o briefing"*, *"o que tem de novo em saúde digital"*,
*"me atualize"*, *"resumo da semana"*, *"resumo do mês"*.

---

## Contexto institucional

**Unidade:** Diretoria de Transformação Digital — DTD
**Órgão:** Secretaria Executiva de Tecnologia da Informação em Saúde — SETIS
**Secretaria:** Secretaria de Estado de Saúde do Distrito Federal — SES-DF

---

## Navegação

| Arquivo | Conteúdo |
|---|---|
| [SKILL.md](./SKILL.md) | Instruções completas: contexto, passo a passo, formato de output, variações |
| [INDICE.md](./INDICE.md) | Índice de todos os arquivos do repositório |
| [backlog-versoes.md](./backlog-versoes.md) | Histórico de versões e exposição de motivos |
