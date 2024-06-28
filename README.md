## 🔮 Prevendo o Futuro do Seu Estoque: Com SageMaker Canvas (No-Code)

👋 Aqui está, o projeto da Inteligência Artificial, através do **SageMaker Canvas**, pode transformar a maneira como você gerencia seu estoque, sem a necessidade de escrever uma única linha de código. 

### ✨ A Era da Previsão Inteligente

Imagine um mundo onde você pode antecipar a demanda dos seus produtos com precisão, evitando as dores de cabeça de rupturas de estoque ou o desperdício de produtos parados no depósito. Com o SageMaker Canvas, essa visão se torna realidade!

Este projeto prático e totalmente *no-code* irá guiá-lo na criação de um modelo de Machine Learning capaz de prever a quantidade de estoque necessária para o final de 2024. Prepare-se para tomar decisões estratégicas de reposição de estoque, otimizar seus recursos e impulsionar seus resultados!

### 🧰 Ferramentas da Missão

* **SageMaker Canvas:** A plataforma intuitiva da AWS que permite construir modelos de ML poderosos com interface visual de arrastar e soltar.
* **Dataset Histórico:** O arquivo `dataset-1000-com-preco-promocional-e-renovacao-estoque.csv` (disponível neste repositório), contendo informações valiosas sobre seus produtos e suas vendas passadas.

### 🗺️ Desvendando o Dataset: Conheça Seus Dados

O sucesso da sua previsão depende de um bom entendimento dos seus dados históricos. Nosso dataset é composto pelas seguintes colunas:

* **ID_PRODUTO:**  O RG do seu produto, um identificador único que o diferencia dos demais.
* **DATA_EVENTO:**  A data em que cada registro foi realizado, permitindo acompanhar a evolução do estoque ao longo do tempo.
* **PRECO:**  O preço do produto em cada data, um fator crucial para entender a influência do preço na demanda.
* **FLAG_PROMOCAO:**  Uma bandeira que sinaliza se o produto estava em promoção (1 para Sim, 0 para Não), revelando o impacto das promoções nas vendas.
* **QUANTIDADE_ESTOQUE:**  A quantidade do produto em estoque em cada data, nossa variável-alvo para a previsão.

### 🧭 Navegando pelo SageMaker Canvas: Construindo Seu Modelo Preditivo

1. **Importação: Conectando o Canvas aos Seus Dados:**

   - Acesse o SageMaker Canvas e clique em "Import Data".
   - Selecione o arquivo `dataset-1000-com-preco-promocional-e-renovacao-estoque.csv`, que pode estar no seu computador ou no Amazon S3.
   - O Canvas, como um detetive experiente, irá analisar o arquivo, identificar as colunas e seus tipos de dados automaticamente, preparando o terreno para a análise.

2. **Definindo o Alvo: O Que Queremos Prever?**

   - Selecione a coluna `QUANTIDADE_ESTOQUE` como o alvo da sua previsão. É como dizer ao Canvas: "Ei, foque em prever essa informação!".

3. **Análise Exploratória: Desvendando os Segredos dos Seus Dados (Opcional):**

   - O Canvas oferece um conjunto de ferramentas para você se familiarizar com seus dados:
     - **Estatísticas Descritivas:**  Descubra a média, valores mínimos e máximos, e outras informações importantes sobre cada coluna.
     - **Tratamento de Valores Faltantes:**  Identifique e decida como lidar com os dados ausentes, garantindo a qualidade da sua análise.
     - **Criação de Novas Colunas:**  Extraia informações adicionais dos seus dados, como o mês e o ano da coluna `DATA_EVENTO`, para ter uma visão mais completa.

4. **Construindo o Modelo: Dando Vida à Inteligência Artificial:**

   - Clique em "New Model" e dê um nome inspirador ao seu modelo. Seja criativo! "Mestre do Estoque", "Oráculo das Vendas"... a escolha é sua!
   - O Canvas, com sua inteligência artificial, irá sugerir algoritmos de Machine Learning adequados ao seu objetivo. Você pode experimentar diferentes opções, como `Time Series Forecasting` para previsões de séries temporais ou `Linear Regression` para encontrar relações entre as variáveis.
   -  Após escolher o algoritmo, clique em "Train Model" e observe o Canvas trabalhar. Ele dividirá seus dados em conjuntos de treinamento e validação, ajustando os parâmetros do modelo para garantir a melhor performance.

5. **Previsões: Olhando para o Futuro:**

   - Com o modelo treinado, defina a data de previsão como `31/12/2024`.
   - Clique em "Generate Predictions" e veja o Canvas gerar as previsões de estoque para cada um dos seus produtos na data escolhida. 

### 🔎 Resultados e Insights: Decifrando as Previsões (Simulação)

Após a etapa de previsão, o Canvas apresenta os resultados em formato de tabelas e gráficos interativos, facilitando a visualização e o entendimento das informações. 

#### Estoque Atual vs. Previsão para 31/12/2024

| ID_PRODUTO | Estoque Atual (08/02/2024) | Previsão de Estoque (31/12/2024) | Análise e Recomendações |
|---|---|---|---|
| 1000 | 24 | 62 | A demanda pelo produto 1000 se manterá estável. A previsão indica que você precisará de 38 unidades adicionais até o final de 2024. |
| 1001 | 37 | 115 | A demanda pelo produto 1001 está em crescimento. Você precisará de 78 unidades adicionais para atender a demanda projetada para o final de 2024.  |
| 1002 | 100 | 35 | A demanda pelo produto 1002 está diminuindo. A previsão indica um excesso de estoque. Avalie promoções ou reajuste a produção para evitar perdas. |
| 1003 | 14 | 80 | A demanda pelo produto 1003 se manterá estável. A previsão indica que você precisará de 66 unidades adicionais até o final de 2024. |
| 1004 | 72 | 150 | A demanda pelo produto 1004 está crescendo rapidamente. Você precisará de 78 unidades adicionais para evitar rupturas no estoque. |
| ... | ... | ... | ... |

#### Métricas de Precisão (Simulação):

* **Avg wQL:** 0.060:  Indica a precisão do modelo em prever diferentes níveis de estoque (quantis).
* **MAPE:** 0.149: Um erro médio de 14.9%, considerado bom para previsões de estoque.
* **WAPE:** 0.103: Similar ao MAPE, mas ponderado pela quantidade real de estoque.
* **RMSE:** 5.977:  O desvio padrão médio das previsões, relativamente baixo nesse caso.
* **MASE:** 0.310:  Indica que o modelo é significativamente mais preciso que um modelo "ingênuo".

**Analisando as Previsões:**

As previsões e métricas de precisão fornecem um panorama completo da situação do seu estoque no futuro. Você pode identificar:

* **Produtos com alta demanda:**  Tome medidas para garantir a disponibilidade desses produtos, evitando rupturas e perda de vendas.
* **Produtos com baixa demanda:**  Ajuste a produção, realize promoções ou busque alternativas para evitar o excesso de estoque.
* **Tendências de mercado:**  Observe o comportamento geral das previsões para entender as tendências do mercado e adaptar suas estratégias.

### 🚀 Próximos Passos: Do Canvas para a Ação

* **Integre com seus sistemas:** Conecte as previsões do Canvas ao seu sistema de gestão de estoque para automatizar as decisões de reposição.
* **Monitore em tempo real:**  Acompanhe as vendas e o estoque em tempo real para identificar desvios das previsões e tomar ações corretivas rapidamente.
* **Aprimore seu modelo:**  Experimente diferentes algoritmos, adicione novas variáveis ao seu dataset (ex: dados de marketing, sazonalidade, eventos externos) e continue treinando seu modelo para aumentar a precisão das previsões.
