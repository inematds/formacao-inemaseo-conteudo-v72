# PLANO — inemaSEO 2 · Conteúdo: páginas que só você pode escrever (v7.2)

Curso 2 de 6 da Formação inemaSEO. Público: dono de site ou criador que já fez a fundação (curso 1). Ordem: 1 → 2 → 3 → 4 → 5 → 6.

Fontes (não alteradas): `~/projetos/inemaseo-metodo` (docs/METODO.md etapas 4–9, docs/CHECKLIST.md, templates/jsonld-entidade.json, jsonld-newsarticle.json, prompt-ficha-extrativa.md, prompt-texto-noticia.md, tools/validar_extracao.mjs), `~/projetos/inemaseo` (docs/ESTRATEGIA_REFERENCIA_ECOSSISTEMA.md, PLANO_EXECUCAO_SEO.md §4–5, COMO_CRIAR_PAGINA_IA.md; números só da lista "Casos reais" do BRIEF), `wifi/longrun/2026-10-19-formacao-inemaseo-v72/` (TENDENCIAS, REVISAO §4.1–4.2).

## As 8 aulas

| # | slug | aula | objetivo (≤ 160) | diagrama | prática ("pronto quando") | fonte |
|---|---|---|---|---|---|---|
| 1 | `entidade` | Entidade: quem está por trás | declarar uma Person e uma Organization com @id fixo e sameAs separado, e fazer o resto do site apontar para elas | autor + marca (@id) → páginas apontam por @id → sameAs → buscador e IA juntam numa entidade | 1) JSON-LD de entidade publicado e validado; 2) teste "o que é [marca]?" em 2 assistentes anotado (colisão de nome?) | METODO etapa 4; `jsonld-entidade.json`; §2.6, §2.8 |
| 2 | `territorio` | Um território por site | decidir onde mora cada tipo de conteúdo e escrever o mapa de canônicos: uma página dona por intenção | tipos de conteúdo → site principal / notícias / eventos → intenção → página dona → as outras linkam | 1) tabela de território dos seus sites; 2) mapa de 5 intenções com página dona e o que fazer com as concorrentes | METODO etapa 5; ESTRATEGIA §2; PLANO_EXECUCAO §5.4 |
| 3 | `palavra-chave` | Validar palavra-chave sem ferramenta paga | pontuar 10 palavras-chave com o score GO/NO-GO e agrupar as aprovadas por intenção | fontes grátis → score → GO / TALVEZ / NO-GO → clusters por intenção | 1) planilha com 10 termos pontuados; 2) clusters com 1 página dona cada | METODO etapa 6; PLANO_EXECUCAO §4.1; REVISAO §4.1 |
| 4 | `pilar-perguntas` | Pilar e páginas de pergunta | escrever uma página de pergunta com resposta direta no topo, seções em pergunta e FAQ visível, sem prometer rich result | pilar → páginas de pergunta → resposta direta → seções → FAQ visível | 1) rascunho de uma página de pergunta com resposta de 2–4 frases e dado próprio; 2) teste da troca aplicado | METODO etapa 6; `COMO_CRIAR_PAGINA_IA.md`; TENDENCIAS §1.4, FAQ |
| 5 | `fichas-dado-real` | Fichas com dado real | gerar fichas de catálogo extraídas da página real e descartar o item que falha na trava anti-invenção | página real → prompt extrativo → trava (título, palavras, números) → publica ou descarta | 1) 3 fichas extraídas com o prompt; 2) trava rodada com saída anotada, item reprovado descartado | `prompt-ficha-extrativa.md`, `validar_extracao.mjs`; §2.3, §2.7 |
| 6 | `links-internos` | Links internos e escada de links | ligar cada página nova ao pilar e às irmãs e editar 2–3 páginas antigas para apontar para ela no mesmo commit | home → pilares → perguntas → irmãs/catálogo; escada: nova ← 2–3 antigas | 1) mapa de links de uma página nova; 2) escada feita, conferida no raio-x (links no HTML) | METODO etapa 7; PLANO_EXECUCAO §5.3; §2.4 |
| 7 | `noticias` | Notícias com página própria | publicar notícia em URL própria com NewsArticle, corpo só com fatos da fonte e arquivo que nunca apaga | notícia → URL própria → NewsArticle → corpo 150–250 → arquivo permanente | 1) uma notícia no modelo com JSON-LD válido; 2) regra de arquivo escrita (noindex quando a fonte pede login) | METODO etapa 9; `jsonld-newsarticle.json`, `prompt-texto-noticia.md`; §2.6 |
| 8 | `sem-spam` | Conteúdo escalado e spam | reconhecer conteúdo escalado e esquemas de link e passar cada página pelo checklist dos 16 itens antes de publicar | atalhos → política de spam → risco; caminho certo → checklist 16 → cadência | 1) checklist dos 16 aplicado a uma página sua; 2) plano de cadência de 4 semanas (≤ 3 por cluster) | REVISAO §4.2; CHECKLIST; TENDENCIAS §spam |

Aula 8 fecha com `mapa` (4 degraus: entidade, território e pauta, páginas, guarda) + `gerador` (8 aulas).

## Simconversa da aula 8 — "o sócio quer publicar 500 artigos com IA"

Personagem: sócio de uma torrefação com loja online. Ficção rotulada; o que ensina vem de TENDENCIAS (política de scaled content abuse, guia de IA do Google, "humanizar" sem política de detector), REVISAO §4.2 e caso §2.3.

| fala | cliente | opções (nota → destino) |
|---|---|---|
| `abre` | "500 artigos por mês, um por palavra-chave" | liga (0 → `fim-queda`) · o que cada um teria de só nosso? (2 → `dado`) · "IA é proibida pelo Google" (1 → `mito`) |
| `mito` (desvio) | "proibida? todo mundo é punido?" | Google avalia valor, não ferramenta (1 → `dado`) · não usar IA nenhuma (0 → `fim-parado`) |
| `dado` | "a ferramenta reescreve o top 10 melhor" | derivado; IA organiza dado nosso (2 → `humaniza`) · reescrever bem passa (0 → `fim-queda`) · reduz para 100 (1 → `humaniza`) |
| `humaniza` | "e um humanizador para o detector?" | Google avalia valor, paráfrase em escala agrava (2 → `plano`) · garante (0 → `fim-queda`) |
| `plano` | "então qual o plano?" | ≤ 3 por cluster/semana + dado próprio + checklist + revisão (2 → `fim-bom`) · 5 sites com links cruzados (0 → `fim-rede`) |

Somas: direto 2+2+2+2 = 8; desvio 1+1+2+2+2 = 8 (não passa do direto). Máximo = 8.

## Decisões tomadas sozinho
- "Resposta direta de 40–60 palavras" (METODO etapa 6) vira "resposta de 2 a 4 frases" (COMO_CRIAR_PAGINA_IA) e é ensinada como clareza; Régua de 2026 diz que não há fonte que a sustente como fator de IA.
- CHECKLIST item 7 (`FAQPage` com FAQ real) mostrado adaptado: FAQ visível útil ao leitor; o rich result de FAQ acabou em 07/05/2026.
- Clusters por intenção sem script (não há um no inemaseo-metodo): planilha.
- Saída real do `validar_extracao.mjs` capturada em 19/10/2026 com uma fonte de exemplo (padaria), dentro de `saida` selo real.
- Números da ESTRATEGIA fora da lista "Casos reais" (catálogo, preços, comunidade) não entram.

## Resultado (19/10/2026)
- Portão: `validar.py` OK em PT/EN/ES (único link falho no `--links`: curso 3, ainda não publicado); `conferir-tela.cjs` 27 páginas × 2 larguras OK, simconversa percorrida (máx. 8).
- Imagens: 10/10 pelo Codex na 1ª tentativa; nenhuma reserva flux.
- Tradução: 1025 textos por idioma (Sonnet 5.5 pela assinatura), 0 sem tradução; glossário ampliado (território, escada de links, ficha, trava anti-invenção, conteúdo escalado, colisão de nome).
