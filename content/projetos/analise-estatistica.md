---
title: "Análise Estatística do Poder de Compra"
date: "2026-06-29"
cover: "/images/Vacas-no-Pasto.jpg"
categories:
  - Estatística
descripition: ""
---

### O preço do leite conta a história do poder de compra no campo brasileiro

Um estudo descritivo-exploratório sobre a distribuição e a evolução dos preços do leite cru no Brasil e em Minas Gerais, contrastando o cenário nacional da produção de origem animal com a Região Sul — construído inteiramente em R, a partir de dados públicos do IBGE/SIDRA.

**Disciplina:** EST 100 — Estatística Descritiva e Exploratória

**Instituição:** Universidade Federal de Viçosa (UFV)

**Ferramentas:** R · tidyverse · ggplot2 · LaTeX

**Fonte dos dados:** IBGE / Sistema SIDRA

---

## Contexto e objetivo

O agronegócio do leite é um termômetro sensível da economia rural brasileira — sujeito a sazonalidade, custo de insumos e disparidades regionais. Este projeto aplica ferramentas de estatística descritiva para transformar registros brutos do SIDRA em leitura estatística honesta sobre como esse mercado se comporta.

> A análise investiga a distribuição e a evolução temporal dos preços do leite cru, além do valor histórico da produção de materiais de origem animal, contrastando o cenário nacional com a Região Sul.

**Bases de dados utilizadas:**

| Base | Descrição | Fonte |
|---|---|---|
| Base A | Pesquisa Trimestral do Leite | IBGE/SIDRA — Tabela 1086 |
| Base B | Pesquisa da Pecuária Municipal | IBGE/SIDRA — Tabela 74 |

---

## Metodologia e reprodutibilidade

Todo o pipeline — da limpeza dos arquivos brutos do IBGE até os gráficos finais — roda em R, organizado para que qualquer pessoa possa reproduzir os resultados do zero, sem editar caminhos de arquivo manualmente.

**Dados brutos → tratados**
Os arquivos originais (.html / .csv) extraídos do IBGE passam por limpeza e estruturação em R, gerando bases tratadas prontas para análise, preservando a rastreabilidade entre dado bruto e dado final.

**Medidas descritivas completas**
Posição, dispersão, separatrizes, assimetria (via `e1071`) e correlação de Pearson, formatadas em tabelas limpas com `knitr` — além de índices ponderados para leitura comparativa entre regiões.

**Estrutura do projeto:**
**Estrutura do projeto:**

```text
projeto_grupo/
├── dados/
│   ├── brutos/          # arquivos originais IBGE (Base A e B)
│   └── tratados/        # bases limpas, geradas via script
├── codigos/
│   ├── dados-brutos-em-R/
│   ├── calculos-e-analises-itens-5.3-5.6/
│   └── graficos-itens-5.3-5.4/
├── relatorio/
│   ├── codigo-fonte/    # relatorio.tex
│   └── relatorio.pdf
└── apresentacao/
    └── slide-est100.pdf
```
---

## Cinco perguntas, cinco gráficos

Cada visualização responde a uma pergunta específica sobre o mercado, na ordem em que a análise foi construída — do panorama geral ao detalhe regional.

### 1. **Distribuição e composição** — Quem domina o setor de produção de origem animal?
![Distribuição da produção por tipo](/images/graficos/grafico-1.png)
### 2. **Comparação entre regiões** — Onde está concentrada a força produtiva, Brasil vs. Região Sul?
![Comparação Brasil vs Região Sul](/images/graficos/grafico-2.png)
### 3. **Evolução temporal** — Como o mercado de leite se comportou ao longo dos anos?
![Série temporal do preço do leite](/images/graficos/grafico-3.png)
### 4. **Relação bivariada** — O preço alto compensa a falta de volume produzido?
![Dispersão preço vs volume](/images/graficos/grafico-4.png)
### 5. **Taxas e índices** — Qual região expandiu seu principal motor produtivo mais rápido?
![Taxas de crescimento por região](/images/graficos/grafico-5.png)

---

## Ficha técnica

`R` · `RStudio` · `tidyverse` · `ggplot2` · `e1071` · `knitr` · `LaTeX` · `IBGE / SIDRA`

---

## Dados públicos, uso responsável de IA

Todos os dados utilizados são públicos, macroeconômicos e anonimizados — sem informação sensível de caráter pessoal. Ferramentas de IA foram usadas como apoio pontual (sintaxe de gráficos em ggplot2, revisão ortográfica, checagem de fórmulas); a interpretação estatística, a seleção de medidas e as conclusões do relatório são de autoria da equipe.

---

## Links

- 🔗 [Repositório no GitHub](https://github.com/SGVick7/Analise-Estat-stica-Poder-de-Compra)
- 📄 [README completo](https://github.com/SGVick7/Analise-Estat-stica-Poder-de-Compra/blob/main/README.md)
- 📜 Licença MIT

---

## Autores:

*Ana Victoria — [@SGVick7](https://github.com/SGVick7)*

*Pedro Lucas Domingues lima — [@PeuLucas77](https://github.com/PeuLucas77)*

*Luan Leal*

**Estudantes de Ciência de Dados, Universidade Federal de Viçosa (UFV)**

---

## Projeto Acadêmico

Este projeto foi desenvolvido como atividade acadêmica para aplicação prática de conceitos de Estatística Descritiva e Exploratória utilizando dados reais.