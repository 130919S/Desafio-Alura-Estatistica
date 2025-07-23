📊 Telecom X – Parte 2: Prevendo Churn de Clientes
Este projeto tem como objetivo prever a evasão de clientes (churn) da empresa Telecom X com base em variáveis comportamentais, contratuais e de uso dos serviços. A ideia é antecipar quais clientes estão mais propensos a cancelar seus serviços e propor estratégias de retenção com base nos dados.

🎯 Propósito da Análise
A análise foi conduzida para:

Identificar os principais fatores que influenciam o churn.

Construir modelos de machine learning que consigam prever com boa precisão quais clientes têm maior probabilidade de cancelar.

Gerar insights estratégicos para ajudar a empresa a reduzir a evasão de forma proativa.

🗂️ Estrutura do Projeto
bash
Copiar
Editar
📁 Telecom-X-Parte2/
├── 📄 TelecomX_Modelo_Preditivo.ipynb        # Notebook principal com todo o código e análises
├── 📄 TelecomX_Data.json                     # Dados brutos (formato original)
├── 📄 telecom_etl_final.csv                  # Dados tratados e prontos para modelagem
├── 📁 imagens/                               # (Opcional) Gráficos e visualizações usadas no notebook
└── 📄 README.md                              # Este arquivo
⚙️ Etapas do Projeto
📌 1. Preparação dos Dados
Leitura e normalização de um arquivo JSON com estrutura aninhada.

Tratamento de colunas irrelevantes, como o customerID, que foi removido por não contribuir para a predição.

Separação das variáveis entre:

Categóricas: contrato, tipo de internet, forma de pagamento etc.

Numéricas: tempo de permanência (tenure), valor mensal, total gasto etc.

📌 2. Encoding
As variáveis categóricas foram transformadas em variáveis numéricas usando One-Hot Encoding, o que facilitou a aplicação dos algoritmos de machine learning.

📌 3. Balanceamento de Classes
Como havia desequilíbrio entre clientes que evadiram (churn) e os que permaneceram, foi aplicado o SMOTE, uma técnica que cria exemplos sintéticos da classe minoritária para equilibrar o conjunto de dados.

📌 4. Normalização
As variáveis numéricas foram padronizadas para modelos que são sensíveis à escala, como Regressão Logística.

📌 5. Separação Treino/Teste
O dataset foi dividido em:

70% para treino

30% para teste

Isso garante uma avaliação mais justa dos modelos.

🤖 Modelos Criados
Foram testados dois modelos principais:

Regressão Logística – Requer normalização. Útil para interpretar a influência de cada variável.

Random Forest – Não precisa de normalização e se mostrou bastante robusto nos testes.

As métricas avaliadas foram:

Acurácia

Precisão

Recall

F1-score

Matriz de confusão

📊 Exemplos de Gráficos e Insights
Durante a análise exploratória (EDA), identificamos alguns padrões importantes:

Clientes com contrato mensal têm muito mais chance de cancelar.

Pagamentos por débito automático estão associados a maior churn.

Clientes que usam fibra óptica também têm maior propensão a sair.

O tempo de permanência (tenure) é inversamente proporcional à evasão: quanto mais tempo o cliente está na empresa, menor a chance de churn.

Visualizações utilizadas:

Gráficos de barras (countplot)

Boxplots para comparar distribuições

Matriz de correlação (heatmap)

🚀 Como Executar o Projeto
Clone ou baixe este repositório.

Abra o arquivo TelecomX_Modelo_Preditivo.ipynb no Google Colab ou Jupyter Notebook.

Certifique-se de instalar as bibliotecas abaixo:

!pip install pandas scikit-learn matplotlib seaborn imbalanced-learn
Faça o upload do arquivo TelecomX_Data.json ou use a versão .csv já tratada (telecom_etl_final.csv) se quiser pular a etapa de ETL.

📌 Observações Finais
Este projeto é uma ótima demonstração de como aplicar técnicas de ciência de dados para resolver um problema real de negócios. Além de treinar e comparar modelos, também geramos insights valiosos para ajudar a Telecom X a reter seus clientes com base em dados.
