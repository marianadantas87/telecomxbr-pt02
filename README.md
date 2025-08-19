📘 Previsão de Churn de Clientes na Empresa Telecom X
🎯 Objetivo do Projeto

A Empresa Telecom X busca reduzir a evasão de clientes (churn) por meio de análises estatísticas e modelos preditivos de Machine Learning.

O projeto foi conduzido pela equipe de análise de dados com os seguintes propósitos:

Identificar quem são os clientes com maior risco de evasão.

Descobrir quais variáveis mais influenciam esse comportamento.

Mapear os perfis de clientes que precisam de maior atenção e retenção.

Utilizar modelos preditivos para antecipar possíveis churns e auxiliar na tomada de decisão estratégica.

Com essas respostas, espera-se diminuir significativamente o churn e aumentar a fidelização de clientes.

📂 Estrutura do Projeto

A organização dos arquivos segue a seguinte estrutura:

📦 TelecomX-Churn
 ┣ 📜 README.md                 → Documentação do projeto
 ┣ 📓 notebook_analise.ipynb     → Notebook principal com todo o fluxo da análise
 ┣ 📂 data
 ┃ ┣ dados_originais.csv        → Dados brutos fornecidos
 ┃ ┗ dados_tratados.csv         → Dados tratados e prontos para modelagem
 ┣ 📂 visualizacoes
 ┃ ┣ churn_por_contrato.png     → Gráfico de churn por tipo de contrato
 ┃ ┣ churn_por_genero.png       → Gráfico de churn por gênero
 ┃ ┗ comparacao_modelos.png     → Comparação das métricas dos modelos
 ┗ 📂 modelos
   ┗ random_forest.pkl          → Exemplo de modelo treinado salvo

🛠️ Preparação dos Dados

Classificação das variáveis

Categóricas: Gênero, Tipo de Contrato, Saída de Clientes.

Numéricas: Valor do Contrato.

Codificação

Genero: Male = 0, Female = 1

Tipo de Contrato:

Month-to-month = 0

One year = 1

Two year = 2

Saida de Clientes (target): Não = 0, Sim = 1

Ajustes em colunas

Conversão da coluna Valor do Contrato para tipo numérico.

Divisão dos dados

train_test_split com stratify=y para manter a proporção de classes.

Conjuntos: 70% treino, 30% teste.

Justificativas

O dataset apresenta desbalanceamento (mais clientes ficam do que saem).

Aplicação de class_weight='balanced' (Logistic Regression, Random Forest)  para compensar esse problema.

📊 Análise Exploratória de Dados (EDA)

Alguns dos gráficos e insights obtidos:

Churn por tipo de contrato

Clientes month-to-month têm taxa de churn de ~41%, enquanto contratos anuais e bianuais têm churn muito menor.

Churn por gênero

Taxas praticamente iguais (25% vs 26%), mostrando que gênero não é determinante.


🤖 Modelagem Preditiva

Modelos testados:

Regressão Logística (class_weight='balanced')

Random Forest (class_weight='balanced')


Principais Resultados:

Random Forest → Melhor recall para clientes que saem (≈ 0.90), ideal para detectar churn.

Regressão Logística  → Equilíbrio entre precisão e recall.



▶️ Como Executar
Abra o Google Colab em:
👉 https://colab.research.google.com

Clique em "Carregar" e faça upload do arquivo parte2_telecomxbr.ipynb.

Instale as bibliotecas necessárias no início do notebook (se ainda não estiverem instaladas):

!pip install pandas matplotlib seaborn scikit-learn 

Execute as células do notebook em ordem.
