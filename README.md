# Projeto Final da Trilha de Analista de Dados: Análise de Score de Crédito

## Introdução
Este repositório contém o projeto final da Trilha de Analista de Dados do Bootcamp [RE]Start. O projeto foi desenvolvido para a empresa fictícia Data Girls Finance, uma fintech que busca compreender de forma aprofundada o perfil financeiro, comportamental e cadastral de seus clientes. O objetivo principal é identificar padrões associados às classificações de score de crédito, gerando informações valiosas para apoiar a área de risco na tomada de decisão.

## Perguntas Norteadoras de Negócio

A análise foi estruturada para responder às seguintes questões fundamentais para a empresa:

* Qual perfil apresenta maior risco de inadimplência, refletido em um baixo score de crédito?
* Quais fatores mais influenciam os clientes classificados com o score "Poor"?
* Existe relação entre variáveis relevantes, como renda anual, quantidade de contas bancárias, número de cartões de crédito, empréstimos e a classificação de score?
* Clientes com maior atraso médio de pagamento tendem a apresentar uma pior classificação de crédito?

## Metodologia e Pipeline de Dados

O desenvolvimento do projeto seguiu uma rotina estruturada de processamento de dados. Os dados foram extraídos da base "Credit Score Classification" disponibilizada no Kaggle. O processo foi realizado em linguagem Python, utilizando bibliotecas como Pandas, NumPy, Matplotlib e Seaborn.

A etapa de preparação e limpeza dos dados consistiu nos seguintes passos:

* **Correção de Tipos de Dados:** Caracteres inválidos e ruídos foram removidos de variáveis numéricas. Além disso, inconsistências de preenchimento em variáveis de texto, como números de segurança social (SSN) e ocupação, foram padronizadas.
* **Tratamento de Valores Nulos:** A identificação do cliente foi utilizada como referência para o preenchimento de dados, garantindo a coesão do perfil histórico.
  * Dados estáticos, como informações cadastrais, foram preenchidos com base no histórico do próprio cliente.
  * Variáveis financeiras contínuas foram preenchidas utilizando a mediana do indivíduo, evitando distorções.
  * Variáveis qualitativas foram ajustadas utilizando o valor mais frequente (moda) do histórico do cliente.
  * O histórico de idade de crédito, originalmente em formato de texto não estruturado, teve seus anos e meses extraídos, interpolados matematicamente e convertidos para um formato numérico padronizado.
* **Tratamento de Anomalias:** Valores fora da realidade do negócio em variáveis discretas, como idades negativas ou taxas de juros irreais, foram invalidados. Para variáveis financeiras, aplicou-se a limitação de valores extremos para mitigar distorções. Variáveis com escalas muito grandes passaram por transformação logarítmica para facilitar a visualização.

## Entregáveis
Os resultados deste projeto estão organizados da seguinte forma:
* **Notebook de Análise:** Arquivo contendo os códigos executados para a leitura, limpeza e exploração inicial dos dados.
* **Dashboard Interativo:** Painel de visualização de dados desenvolvido para responder às perguntas de negócio.

## Guia de Uso do Dashboard

O painel foi desenhado para ser intuitivo e direto, auxiliando a equipe da Data Girls Finance a explorar as informações. Para utilizá-lo de forma eficiente:

1. Utilize os menus e filtros para isolar a base de clientes com base em suas classificações de crédito (Good, Standard, Poor).
2. Observe as correlações visuais entre o saldo mensal, o nível de endividamento e a quantidade de produtos financeiros (como cartões e contas) para compreender os fatores que reduzem a pontuação do cliente.
3. Avalie os indicadores de atraso de pagamento para tomar decisões relacionadas a campanhas de educação financeira ou revisão de critérios de aprovação.
