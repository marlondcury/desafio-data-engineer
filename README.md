# Análise do E-commerce Brasileiro (Olist)

Este projeto explora o dataset da Olist, um marketplace brasileiro, com o objetivo de extrair insights relevantes sobre o comportamento de clientes, vendas, entregas, pagamentos e avaliações.

## Projeto:
[Projeto](Brazilian_E_CommerceFinal.ipynb)

##  Dataset

O dataset é composto por múltiplos arquivos CSV que representam diferentes aspectos do processo de venda online, como pedidos, itens, pagamentos, avaliações, localização geográfica, entre outros.

Fonte: [Kaggle - Brazilian E-Commerce Public Dataset by Olist](https://www.kaggle.com/datasets/olistbr/brazilian-ecommerce)

##  Como Executar

1. Instale os pacotes necessários:
    ```bash
    pip install pandas numpy matplotlib seaborn plotly kagglehub
    ```

2. Execute o notebook `Brazilian_E_Commerce.ipynb` em ambiente compatível com Jupyter Notebook (recomenda-se o [Google Colab](https://colab.research.google.com/)).

3. Os dados são automaticamente baixados com o `kagglehub`.

##  Metodologia

O notebook está estruturado da seguinte forma:

1. **Importação de bibliotecas e dados**
2. **Inspeção das tabelas individualmente**
3. **Análise descritiva com foco em:**
   - Volume de vendas por categoria
   - Tempos médios de entrega
   - Avaliações dos clientes e fatores que influenciam a nota
4. **Visualizações interativas com Plotly e estáticas com Seaborn/Matplotlib**
5. **Soluções para problemas de negócio com técnicas de machine learning e clustering**

##  Principais Resultados

- A categoria mais vendida foi `cama_mesa_banho` e `beleza_saude`.
- A média de tempo de entrega é de aproximadamente 12 dias, com picos em regiões mais afastadas.
- Clientes que recebem pedidos mais rápido tendem a dar notas maiores nas avaliações.
- A geolocalização revelou padrões de concentração de vendedores e compradores no Sudeste.

## Decisões Técnicas

- A função `inspect_dataframe()` foi criada para padronizar a inspeção dos DataFrames.
- Foram priorizadas visualizações de fácil interpretação, usando `plotly.express` para interatividade.

##  Solução de Problemas de Negócio (25 pontos)

###  1. Análise de Retenção
- **Critério de cliente recorrente:** clientes que fizeram **mais de um pedido** no período analisado.
- **Taxa de recorrência:** aproximadamente **3%** dos clientes retornaram para uma segunda compra.
- **Insights:**
  - Clientes recorrentes tendem a avaliar melhor os pedidos.
  - Estratégias de fidelização podem focar nos estados e categorias com maior taxa de recompra.
  - Incentivos como frete grátis ou cupons podem aumentar o retorno.

###  2. Predição de Atraso na Entrega
- **Definição de atraso:** `order_delivered_customer_date > order_estimated_delivery_date`.
- **Features utilizadas:**
  - Tempo de processamento
  - Tipo de produto, valor do pedido, número de itens
- **Modelos aplicados:** Regressão Logística e Random Forest
- **Resultado:** Acurácia de 90%, F1-score de 0.90 para ambas as classes
- **Conclusão:** O modelo pode prever atrasos com boa confiança e servir como ferramenta de suporte para logística.

###  3. Segmentação de Clientes
- **Técnica:** K-Means Clustering
- **Variáveis:** ticket médio, frequência de compra, tempo médio de entrega, avaliação média

- **Ações:** campanhas personalizadas, ofertas e melhorias logísticas.

###  4. Análise de Satisfação
- **Fatores analisados:** categoria do produto, tempo de entrega, valor da compra
- **Principais achados:**
  - Tempo de entrega é o maior fator de insatisfação.

##  Visualizações e Dashboards 

 **Dashboard Geral**

 **Mapa de Calor**
**Avaliação vs Tempo de Entrega**

**Dashboard de Vendedores**


---
