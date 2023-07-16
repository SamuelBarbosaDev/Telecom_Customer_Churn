# Telecom_Customer_Churn
Uma empresa de telecom que fornece serviços está preocupada em reduzir a taxa de retenção de seus clientes.
Portanto, o gerente de CRM te contratou para que você **desenvolva um modelo de predição de clientes que provavelmente irão parar de utilizar os serviços da empresa**. A ideia é alcançar o máximo de clientes que possivelmente irão entrar em churn pois a empresa quer manter o máximo de clientes com seus serviços ativos. Para executar esse projeto, a empresa te forneceu uma base de dados histórica de 7043 clientes com 21 colunas que estão listadas abaixo.

### Índice

- [Telecom\_Customer\_Churn](#telecom_customer_churn)
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
  - [Preparação dos Dados:](#preparação-dos-dados)
    - [Criando Uma Copia do DataFrame:](#criando-uma-copia-do-dataframe)
    - [Substituindo Valores:](#substituindo-valores)
    - [Substituindo Valores:](#substituindo-valores-1)
    - [Removendo nulos:](#removendo-nulos)
    - [Label Endcode:](#label-endcode)
    - [Convertendo Colunas:](#convertendo-colunas)
    - [Dummy:](#dummy)
    - [Removendo Colunas:](#removendo-colunas)
  - [Modelagem:](#modelagem)
    - [Variáveis:](#variáveis-1)
    - [Regressão Logística:](#regressão-logística)
    - [Regressão Logística - Desempenho:](#regressão-logística---desempenho)
    - [Regressão Logística - GridSearchCV:](#regressão-logística---gridsearchcv)
    - [Regressão Logística Tunning:](#regressão-logística-tunning)
    - [Regressão Logística Tunning - Desempenho:](#regressão-logística-tunning---desempenho)
    - [Random Forest:](#random-forest)
    - [Random Forest - Desempenho:](#random-forest---desempenho)
    - [Random Forest - GridSearchCV:](#random-forest---gridsearchcv)
    - [Random Forest Tunning:](#random-forest-tunning)
    - [Random Forest Tunning - Desempenho:](#random-forest-tunning---desempenho)
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
Utilize um modelo de classificação para mapear qual o perfil de usuários tem mais chance de deixar sua plataforma de streaming.
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

## Preparação dos Dados:
### Criando Uma Copia do DataFrame:
![Data Frame](/core/img/copy.png)

### Substituindo Valores:
![Data Frame](/core/img/substituindo_valores.png)

### Substituindo Valores:
![Data Frame](/core/img/substituindo_valores.png)

### Removendo nulos:
![Data Frame](/core/img/removendo_nulos.png)

### Label Endcode:
![Data Frame](/core/img/label_endcode.png)

### Convertendo Colunas:
![Data Frame](/core/img/convertendo_colunas.png)

### Dummy:
![Data Frame](/core/img/dummy.png)

### Removendo Colunas:
![Data Frame](/core/img/removendo_colunas.png)


## Modelagem:
### Variáveis:
![Data Frame](/core/img/x_e_y.png)

### Regressão Logística:
![Data Frame](/core/img/regressão_logística.png)

### Regressão Logística - Desempenho:
![Data Frame](/core/img/regressão_logística_desempenho.png)

### Regressão Logística - GridSearchCV:
![Data Frame](/core/img/regressão_logística_gridsearchcv.png)

### Regressão Logística Tunning:
![Data Frame](/core/img/regressão_logística_tunning.png)

### Regressão Logística Tunning - Desempenho:
![Data Frame](/core/img/regressão_logística_tunning_desempenho.png)

### Random Forest:
![Data Frame](/core/img/random_forest.png)

### Random Forest - Desempenho:
![Data Frame](/core/img/random_forest_desempenho.png)

### Random Forest - GridSearchCV:
![Data Frame](/core/img/random_forest_gridsearchcv.png)

### Random Forest Tunning:
![Data Frame](/core/img/random_forest_tunning.png)

### Random Forest Tunning - Desempenho:
![Data Frame](/core/img/random_forest_tunning_desempenho.png)

## Avaliação:
Com o objetivo de criar este estudo, buscamos identificar o perfil dos usuários que têm maior probabilidade de deixar a plataforma de streaming. Para isso, realizamos uma análise detalhada em busca de padrões entre os diferentes perfis de usuários que abandonam a plataforma, a fim de identificar possíveis casos de churn antes que ocorram. Dessa forma, buscamos reter esses clientes por mais tempo em nossa plataforma.

Utilizamos dois modelos de machine learning para identificar os perfis dos clientes: Regressão Logística e Random Forest. Durante a comparação entre os dois modelos, constatamos que o Random Forest obteve um desempenho superior, além de se adequar melhor à resolução do nosso problema.

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
conda install --file core/requirements.txt
```

---
Linkedin: <https://www.linkedin.com/in/samuel-barbosa-dev/> 

E-mail: <samueloficial@protonmail.com>