Detecção de Fraude em Cartões de Crédito
Projeto de Machine Learning para identificação de transações fraudulentas utilizando XGBoost e SHAP para explicabilidade das decisões do modelo.

 Sobre o Projeto
Fraudes em cartões de crédito causam bilhões de dólares em prejuízo anualmente. Este projeto aborda um dos maiores desafios do setor financeiro: identificar transações fraudulentas em tempo real, lidando com um dataset altamente desbalanceado onde menos de 0,2% das transações são fraudes.
O diferencial deste projeto está na camada de explicabilidade — além de detectar fraudes, o modelo é capaz de justificar cada decisão utilizando SHAP values, algo exigido por regulações financeiras no mundo real.

Dataset

Fonte: Credit Card Fraud Detection - Kaggle
Tamanho: 284.807 transações
Período: Setembro de 2013, titulares de cartões europeus
Desbalanceamento: apenas 0,17% das transações são fraudes (492 casos)
Features: 28 componentes PCA anonimizados (V1-V28) + Time + Amount


Tecnologias Utilizadas

Python
Pandas & NumPy
Matplotlib & Seaborn
Scikit-learn
XGBoost
SHAP


Etapas do Projeto

Análise Exploratória (EDA) — distribuição das classes, análise de valores por tipo de transação
Pré-processamento — normalização do Amount, remoção de features irrelevantes
Modelagem — XGBoost com tratamento de desbalanceamento via scale_pos_weight
Avaliação — Matriz de Confusão, F1-Score, Curva ROC
Explicabilidade — SHAP summary plots para interpretação global e local do modelo


 Resultados
MétricaValorPrecision (Fraude)0.88Recall (Fraude)0.85F1-Score (Fraude)0.86AUC-ROC0.9691
O modelo identificou corretamente 83 de 98 fraudes no conjunto de teste, com apenas 11 falsos positivos em 56.864 transações legítimas.

 Principais Insights

A feature V14 é a mais relevante para a decisão do modelo — valores baixos dessa feature são o principal indicador de fraude
Fraudes apresentam valor médio de transação maior que transações legítimas
O dataset é extremamente desbalanceado, tornando métricas como F1-Score e AUC-ROC mais relevantes que a acurácia


Como Executar
O projeto foi desenvolvido no Google Colab. Para reproduzir:

Acesse o notebook pelo link abaixo
Configure suas credenciais do Kaggle na primeira célula
Execute todas as células em ordem (Ambiente de execução → Executar tudo)
