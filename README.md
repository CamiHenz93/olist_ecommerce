# 📊 Análise de E-Commerce Olist — Tratamento de Dados e Dashboard

> **Narrativa central:** Pedidos atrasados recebem nota média 47% menor que pedidos entregues no prazo.

---

## 📌 Sobre o Projeto

Este projeto faz parte do meu portfólio de analista de dados e tem como objetivo demonstrar habilidades em **tratamento de dados**, **modelagem** e **storytelling com dados**, utilizando uma base pública real do e-commerce brasileiro.

A análise parte de uma pergunta de negócio simples:

> *O prazo de entrega influencia a satisfação dos clientes?*

E a resposta, provada pelos dados, é clara: **sim, e muito.**

---

## 🗂️ Estrutura do Projeto

```
projeto_olist/
│
├── projeto_olist.xlsx        # Base tratada com Power Query
│   ├── olist_orders_dataset       # Pedidos tratados
│   ├── olist_order_reviews_dataset # Avaliações tratadas
│   ├── olist_order_items_dataset  # Itens tratados
│   ├── Antes x Depois             # Documentação visual do tratamento
│   └── Tratamento_dados           # Log de decisões e Resumo Executivo
│
└── olist_dashboard.pbix      # Dashboard Power BI com 3 páginas
```

---

## 🔧 Ferramentas Utilizadas

- **Excel** — Power Query para tratamento e transformação de dados
- **Power BI** — Modelagem de dados, DAX e visualizações

---

## 📁 Fonte dos Dados

Base pública disponível no Kaggle:
[Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

- 9 arquivos CSV
- ~100 mil pedidos reais
- Período: 2017 a 2018

---

## 🧹 Tratamento de Dados

O tratamento foi realizado no **Power Query do Excel** e documentado em detalhes nas abas `Antes x Depois` e `Tratamento_dados`.

### Resumo do tratamento

| Tabela | Problema | Ação |
|---|---|---|
| orders | 6 status distintos | Filtrado apenas `delivered` |
| orders | ~1.100 nulos em datas de envio | Mantidos — nulo legítimo |
| orders | 8 linhas com erro de cálculo | Removidas |
| orders | Colunas de atraso e classificação ausentes | Criadas via fórmula |
| orders | `ano_mes` ausente | Criado no formato `yyyy-MM` |
| reviews | 88% de nulos em títulos | Substituídos por "Sem título" |
| reviews | 56% de nulos em comentários | Substituídos por "Sem comentário" |
| order_items | Ticket médio e % de frete ausentes | Colunas criadas |

**Total:** ~308.000 registros processados, 5 colunas criadas, ~142.000 nulos tratados.

---

## 📊 Dashboard Power BI

O dashboard tem 3 páginas com narrativa progressiva:

### Página 1 — Visão Geral
Panorama geral do negócio com os 4 KPIs principais.

| KPI | Valor |
|---|---|
| Total de pedidos entregues | 96.478 |
| Média de dias de atraso | -10,96 (adiantados) |
| Nota média de satisfação | 4,09 / 5 |
| Ticket médio por item | R$ 140,64 |

### Página 2 — Entregas
Análise da pontualidade das entregas ao longo do tempo.

- **93,22%** dos pedidos chegam no prazo
- Correlação visível entre atraso e queda na satisfação
- Pedidos com atraso acima de 20 dias tendem a nota abaixo de 2

### Página 3 — Satisfação
Prova da narrativa central com dados.

- Pedidos **no prazo**: nota média **4,29**
- Pedidos **atrasados**: nota média **2,27**
- Diferença de **47%** na satisfação

---

## 💡 Principais Insights

1. **Atrasos destroem a satisfação** — a diferença de 2 pontos na nota entre pedidos no prazo e atrasados é estatisticamente expressiva numa escala de 1 a 5.

2. **A Olist é conservadora nos prazos** — a média de -10,96 dias mostra que, na maioria dos casos, as entregas chegam quase 11 dias antes do estimado, o que protege a satisfação.

3. **Frete pode ser desproporcional** — identificamos casos onde o frete chega a 481% do valor do produto, um ponto de atenção para a estratégia de precificação.

---

## 👩‍💻 Autora

**Camila Fernanda Henz dos Santos**

[LinkedIn](linkedin.com/in/camila-henz-114715202/) | [GitHub](https://github.com/)
