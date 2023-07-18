# Telecom Customer Churn

### Índice

- [Telecom Customer Churn](#telecom-customer-churn)
    - [Índice](#índice)
    - [Contextualização:](#contextualização)
    - [Metodologia Aplicada:](#metodologia-aplicada)
  - [Entendimento do Negócio:](#entendimento-do-negócio)
  - [Entendimento dos Dados:](#entendimento-dos-dados)
    - [Variáveis:](#variáveis)
    - [Verificando as Dimensões do DataFrame:](#verificando-as-dimensões-do-dataframe)
    - [Describe:](#describe)
    - [Verificando Valores Nulos:](#verificando-valores-nulos)
    - [Verificando Tipos:](#verificando-tipos)
    - [Distribuição de Churn:](#distribuição-de-churn)
  - [Preparação dos Dados:](#preparação-dos-dados)
    - [Substituindo Valores Vazios '' Por Nulos:](#substituindo-valores-vazios--por-nulos)
    - [Removendo nulos:](#removendo-nulos)
    - [Convertendo Colunas:](#convertendo-colunas)
    - [Train-test split:](#train-test-split)
    - [Construção do pipeline de pré-processamento:](#construção-do-pipeline-de-pré-processamento)
  - [Modelagem:](#modelagem)
    - [Sem Balanceamento:](#sem-balanceamento)
    - [Random OverSampler:](#random-oversampler)
    - [Smote:](#smote)
    - [Adasyn:](#adasyn)
  - [Avaliação:](#avaliação)
  - [Implantação:](#implantação)
  - [Pré-requisitos para executar o projeto:](#pré-requisitos-para-executar-o-projeto)
    - [Instale o Pacote Anaconda:](#instale-o-pacote-anaconda)
    - [Ambiente virtual e Dependências:](#ambiente-virtual-e-dependências)


### Contextualização:
Uma empresa de telecom que fornece serviços está preocupada em reduzir a taxa de retenção de seus clientes.
Portanto, o gerente de CRM te contratou para que você **desenvolva um modelo de predição de clientes que provavelmente irão parar de utilizar os serviços da empresa**. A ideia é alcançar o máximo de clientes que possivelmente irão entrar em churn pois a empresa quer manter o máximo de clientes com seus serviços ativos. Para executar esse projeto, a empresa te forneceu uma base de dados histórica de 7043 clientes com 21 colunas que estão listadas abaixo.

### Metodologia Aplicada:
A análise foi realizada utilizando o modelo CRISP-DM, o CRISP-DM (Cross Industry Standard Process for Data Mining) é um modelo padrão de processo para projetos de mineração de dados que define um conjunto de fases e tarefas que devem ser executadas para desenvolver soluções de mineração de dados efetivas.

![CRISP-DM](/core/img/CRISP-DM.png)

O modelo CRISP-DM é uma abordagem sistemática e estruturada para a mineração de dados que ajuda as empresas a desenvolver soluções de mineração de dados de maneira eficiente e eficaz, reduzindo o tempo e os custos do projeto.

## Entendimento do Negócio:
Utilize um modelo de classificação para mapear qual o perfil de usuários tem mais chance parar de utilizar os serviços da empresa.
Compreender quem é o perfil que está aumentando o churn do seu negócio é essencial para tomar ações que reduzam essas perdas, seja alterando critérios na venda ou modificando o produto.

## Entendimento dos Dados:
### Variáveis:
| Coluna           | Descrição                                             |
| ---------------- | ----------------------------------------------------- |
| customerID       | Id do cliente                                         |
| gender           | Sexo do cliente                                       |
| SeniorCitizen    | Se o cliente é idoso ou não                           |
| Partner          | Se o cliente faz parte de algum relacionamento ou não |
| Dependents       | Se o cliente possui dependentes ou não                |
| tenure           | Número de meses que o cliente permaneceu c/ a empresa |
| PhoneService     | Se o cliente tem atendimento telefônico ou não        |
| MultipleLines    | Se o cliente tem várias linhas ou não                 |
| InternetService  | Provedor de serviços de internet do cliente           |
| OnlineSecurity   | Se o cliente tem segurança online ou não              |
| OnlineBackup     | Se o cliente tem backup online ou não                 |
| DeviceProtection | Se o cliente tem proteção de dispositivo ou não       |
| TechSupport      | Se o cliente tem suporte técnico ou não               |
| StreamingTV      | Se o cliente tem streaming de TV ou não               |
| StreamingMovies  | Se o cliente tem streaming de filmes ou não           |
| Contract         | O prazo do contrato do cliente                        |
| PaperlessBilling | Se o cliente tem recebe conta em papel ou não         |
| PaymentMethod    | A forma de pagamento do cliente                       |
| MonthlyCharges   | O valor cobrado mensalmente do cliente                |
| TotalCharges     | O valor total cobrado do cliente                      |
| Churn            | Indicador se o cliente deu churn (1) ou não (0)       |

### Verificando as Dimensões do DataFrame:
![Data Frame](/core/img/shape.png)

### Describe:
![Data Frame](/core/img/describe.png)

### Verificando Valores Nulos:
![Data Frame](/core/img/nulos.png)

### Verificando Tipos:
![Data Frame](/core/img/tipos.png)

### Distribuição de Churn:
![Data Frame](/core/img/distribuição.png)

## Preparação dos Dados:

### Substituindo Valores Vazios '' Por Nulos:
![Data Frame](/core/img/substituindo_valores.png)

### Removendo nulos:
![Data Frame](/core/img/removendo_nulos.png)

### Convertendo Colunas:
![Data Frame](/core/img/convertendo_colunas.png)

### Train-test split:
![Data Frame](/core/img/train_test_split.png)

### Construção do pipeline de pré-processamento:
![Data Frame](/core/img/pre_processamento.png)


## Modelagem:
### Sem Balanceamento:
![Data Frame](/core/img/sem_balanceamento.png)

### Random OverSampler:
![Data Frame](/core/img/random_over_sampler.png)

### Smote:
![Data Frame](/core/img/smote.png)

### Adasyn:
![Data Frame](/core/img/adasyn.png)

## Avaliação:
Nosso objetivo é reduzir a taxa de cancelamento (churn), então testamos vários modelos de classificação para prever o perfil dos clientes propensos a cancelar ou não. Também utilizamos técnicas de balanceamento de dados, como Random Oversampling, SMOTE, ADASYN e Random Undersampling.

Criamos um pipeline de pré-processamento e um pipeline para cada modelo e técnica de balanceamento. No final, o pipeline de regressão logística em conjunto com a técnica de oversampling aleatório apresentou o melhor desempenho, com um F1 de 0.64.

No entanto, esta é a versão 0.1.0 do projeto, e há vários pontos que serão atualizados em versões futuras. Com isso em mente, listamos algumas possíveis atualizações que podem ser feitas no futuro.

- **Exploração dos dados:** Analise os dados com mais detalhes para entender melhor as características dos clientes churn e identificar padrões ou insights relevantes. Isso pode ajudar a identificar variáveis-chave que afetam o churn e a orientar a seleção de recursos e técnicas de pré-processamento mais adequadas.

- **Engenharia de recursos:** Considere a possibilidade de criar novas variáveis ou transformar as existentes para capturar melhor a informação relevante para a previsão do churn. Isso pode envolver a criação de variáveis agregadas, rácios ou categorizações mais refinadas.

- **Seleção de recursos:** Utilize técnicas de seleção de recursos para identificar as variáveis mais relevantes para o problema de churn. Isso pode ajudar a simplificar o modelo, reduzir o ruído e melhorar a generalização.

- **Experimentação com diferentes modelos:** Embora a regressão logística tenha apresentado bom desempenho, vale a pena explorar outros algoritmos de classificação, como árvores de decisão, random forest, gradient boosting, SVM, entre outros. Cada algoritmo tem suas próprias características e pode se adaptar melhor ao seu conjunto de dados específico.

- **Ajuste de hiperparâmetros:** Experimente ajustar os hiperparâmetros do seu modelo para otimizar o desempenho. O ajuste correto dos hiperparâmetros pode melhorar significativamente o desempenho do modelo.

- **Validação cruzada:** Utilize técnicas de validação cruzada para avaliar o desempenho do modelo de forma mais robusta. Isso envolve dividir o conjunto de dados em conjuntos de treinamento e teste em várias iterações para obter estimativas mais confiáveis do desempenho do modelo.

- **Outras métricas de avaliação:** Além do F1-score, considere outras métricas de avaliação, como precisão, recall, matriz de confusão, curva ROC e área sob a curva (AUC-ROC). Essas métricas podem fornecer uma visão mais completa do desempenho do modelo em diferentes aspectos.

- **Validação externa:** Se possível, valide o desempenho do seu modelo em um conjunto de dados externo ou em um ambiente de produção. Isso ajuda a verificar se o desempenho observado é generalizável e se o modelo está realmente fornecendo insights úteis para a empresa.

## Implantação:
Iniciando a etapa de implementação do modelo em produção.

## Pré-requisitos para executar o projeto:
Abaixo, listarei os requisitos necessários para que o projeto funcione corretamente.

### Instale o Pacote Anaconda:
Você pode baixá-lo em: <https://www.anaconda.com/download/> 

### Ambiente virtual e Dependências:
Criando ambiente virtual:
```
conda create -n .tcc python=3.10.6
```

Entrando no ambiente virtual:
```
conda activate .tcc
```

Instale as dependências:
```
pip install -r core/requirements.txt
```

---
Linkedin: <https://www.linkedin.com/in/samuel-barbosa-dev/> 

E-mail: <samueloficial@protonmail.com>