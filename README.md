# Análise de Dados para Previsão de Inadimplência em Cartões de Crédito

Este repositório contém um notebook Jupyter (`metodologia-CRISP.ipynb`) que realiza uma análise de dados para previsão de inadimplência em cartões de crédito, seguindo a metodologia CRISP-DM (Cross-Industry Standard Process for Data Mining). O objetivo principal é construir um modelo preditivo para identificar o risco de inadimplência com base em variáveis observáveis na data da avaliação do crédito.

## Metodologia CRISP-DM

A metodologia CRISP-DM é dividida em seis etapas principais:

1. **Entendimento do Negócio**: Compreensão do problema de negócio e definição dos objetivos.
2. **Entendimento dos Dados**: Exploração e análise dos dados disponíveis.
3. **Preparação dos Dados**: Limpeza, transformação e preparação dos dados para modelagem.
4. **Modelagem**: Construção e avaliação de modelos preditivos.
5. **Avaliação**: Avaliação dos modelos em relação aos objetivos de negócio.
6. **Implantação**: Implementação do modelo em um ambiente de produção.

Este notebook foca nas duas primeiras etapas: **Entendimento do Negócio** e **Entendimento dos Dados**.

## Dicionário de Dados

O conjunto de dados contém 16 variáveis, incluindo a variável resposta `mau`, que indica se o cliente é um mau pagador (`True`) ou não (`False`). Abaixo está o dicionário de dados:

| Variável                | Descrição                                         | Tipo       |
|-------------------------|---------------------------------------------------|------------|
| sexo                    | M = 'Masculino'; F = 'Feminino'                   | M/F        |
| posse_de_veiculo        | Y = 'possui'; N = 'não possui'                    | Y/N        |
| posse_de_imovel         | Y = 'possui'; N = 'não possui'                    | Y/N        |
| qtd_filhos              | Quantidade de filhos                              | inteiro    |
| tipo_renda              | Tipo de renda (ex: assalariado, autônomo etc)     | texto      |
| educacao                | Nível de educação (ex: secundário, superior etc)  | texto      |
| estado_civil            | Estado civil (ex: solteiro, casado etc)           | texto      |
| tipo_residencia         | Tipo de residência (ex: casa/apartamento, com os pais etc) | texto |
| idade                   | Idade em anos                                     | inteiro    |
| tempo_emprego           | Tempo de emprego em anos                          | inteiro    |
| possui_celular          | Indica se possui celular (1 = sim, 0 = não)       | binária    |
| possui_fone_comercial   | Indica se possui telefone comercial (1 = sim, 0 = não) | binária |
| possui_fone             | Indica se possui telefone (1 = sim, 0 = não)      | binária    |
| possui_email            | Indica se possui e-mail (1 = sim, 0 = não)        | binária    |
| qt_pessoas_residencia   | Quantidade de pessoas na residência               | inteiro    |
| **mau**                 | Indicadora de mau pagador (True = mau, False = bom) | binária |

## Análise Exploratória de Dados (EDA)

### Carregamento dos Dados

O conjunto de dados é carregado a partir de um arquivo CSV (`demo01.csv`) e contém 16.650 linhas e 16 colunas.

```python
import pandas as pd

df = pd.read_csv('demo01.csv')
print("Número de linhas e colunas da tabela: {}".format(df.shape))
df.head()
