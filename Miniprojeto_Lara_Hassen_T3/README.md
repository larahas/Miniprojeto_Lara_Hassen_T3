# Mini-Projeto de Análise Exploratória de Dados — Base Varejo

**Aluna:** Lara Hassen  
**Turma:** T3  
**Disciplina:** Visualização de Dados e Business Intelligence  
**Módulo:** 1 — Semana 07

## Sobre o projeto

Este projeto apresenta uma Análise Exploratória de Dados da base Varejo. O objetivo é transformar os dados brutos em uma base limpa e adequada para análises, aplicando etapas de carregamento, diagnóstico, tratamento, validação, estatística descritiva e agrupamento.

A análise foi desenvolvida em Python no Google Colab, utilizando principalmente a biblioteca pandas.

## Tecnologias utilizadas

- Python
- Google Colab
- pandas
- NumPy
- Matplotlib
- Seaborn
- KaggleHub

## Base de dados

Foi utilizada a base pública Varejo, disponibilizada no Kaggle.

A base contém informações sobre datas das compras, identificadores das compras e clientes, características dos clientes e nomes dos produtos.

A base original possuía 830.000 registros e 14 colunas.

## Tratamento e preparação dos dados

Foram realizadas as seguintes etapas:

1. Leitura estruturada do arquivo CSV utilizando `pandas.read_csv()`.
2. Inspeção da quantidade de registros, nomes das colunas e tipos de dados.
3. Conversão da coluna `DATA` para o tipo `datetime`
4. Identificação de valores nulos e campos de texto vazios.
5. Remoção das colunas totalmente vazias `Unnamed: 10`, `Unnamed: 11`, `Unnamed: 12` e `Unnamed: 13`.
6. Tratamento preventivo de categorias vazias com o valor `Sem Categoria`.
7. Identificação e remoção de 96.553 registros integralmente duplicados.
8. Validação do identificador da compra por cliente e data.
9. Exportação da base tratada para o arquivo `Varejo_limpo.csv`.

## Estatísticas do número de filhos

As estatísticas foram calculadas considerando cada cliente uma única vez, evitando que clientes com mais compras tivessem maior peso nos resultados.

- Contagem de clientes: 1.000
- Média: 1,136
- Mediana: 0 
- Desvio padrão: 1,413
- Moda: 0
- Máximo: 4
- Mínimo: 0

## Principais insights

- A análise contemplou 1.000 clientes e 18.471 compras distintas.
- O número médio de filhos por cliente foi de 1,136, enquanto a mediana e a moda foram iguais a zero.
- Os clientes do gênero feminino realizaram 9.615 compras, enquanto os clientes do gênero masculino realizaram 8.856.
- A categoria Alimentos apresentou o maior volume de itens vendidos, seguida pelas categorias Higiene e Limpeza.
- Não foram identificadas compras associadas a mais de um cliente ou a mais de uma data.
- A análise temporal permitiu identificar os períodos de maior e menor volume de itens vendidos.

## Análise temporal

- O mês com maior volume de vendas foi maio/2019, com 711 itens vendidos.
- O mês com menor volume de vendas foi setembro/2022, com 35 itens vendidos.

## Análise sobre extração, tratamento, qualidade e carregamento dos dados

Considerando que a qualidade dos dados influencia diretamente a confiabilidade das análises, foi realizada a limpeza e validação das informações antes do levantamento dos indicadores.

O processo desenvolvido representa uma aplicação simplificada de ETL. Na etapa de extração, a base foi obtida do Kaggle e carregada com pandas. 
Além disso, foi identificado os tipos de dados, valores nulos, campos vazios, duplicatas e possíveis inconsistências. 
E então, a coluna de data foi convertida de object para DATA. Na etapa de análise dos campos nulos, foram removidas colunas sem informação, e aplicada uma regra preventiva para categorias vazias. 
Enquanto que a verificação de campos duplicados não apresentou erros. 
Já na etapa de carregamento final, a base tratada foi exportada para um novo arquivo CSV.