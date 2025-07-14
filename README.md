# **Modelo de Crédito para concessão de cartões**

# **Entendimento do Negócio**
## **Problema de Negócio**

A concessão de cartões de crédito é um desafio crucial para instituições financeiras, que buscam equilibrar a expansão de sua base de clientes com a minimização de riscos associados a inadimplências. O problema reside em determinar, com base em um conjunto de variáveis explicativas como histórico de crédito, renda, idade e outros fatores socioeconômicos, se um solicitante é elegível para receber um cartão de crédito.

A decisão incorreta pode resultar em perdas significativas para o banco em caso de default, ou na perda de um cliente potencialmente valioso se um cartão for indevidamente negado. Portanto, é essencial desenvolver modelos preditivos robustos e precisos que possam auxiliar as instituições na tomada dessas decisões, garantindo sustentabilidade financeira e satisfação do cliente

## **Sobre os Dados**

Os dados utilizados para a análise são uma combinação de fontes internas e externas, proporcionando uma visão abrangente e detalhada do perfil dos solicitantes. Estes dados abrangem um período histórico de 13 meses, começando em janeiro de 2019 e se estendendo até janeiro de 2020. Esse intervalo de tempo foi estrategicamente escolhido para capturar padrões e tendências relevantes, permitindo uma avaliação mais precisa da elegibilidade dos solicitantes para a concessão de cartões de crédito.

A inclusão de informações tanto internas quanto externas enriquece a análise, oferecendo uma perspectiva multidimensional dos riscos e oportunidades associados a cada cliente.

## **Objetivo do Projeto**

O principal objetivo deste projeto é desenvolver um modelo robusto e confiável para a concessão de cartões de crédito, que possa ser facilmente interpretado e implementado. Dada a necessidade de explicabilidade e uma implementação sem complicações, optamos por utilizar a regressão logística como método de modelagem. Esta técnica é reconhecida por sua alta capacidade de oferecer insights claros sobre as variáveis influentes, além de ser facilmente integrada em sistemas de tomada de decisão. Ao longo do desenvolvimento, serão consideradas todas as etapas tradicionais, desde a compreensão e preparação dos dados até a validação e implementação do modelo, garantindo assim uma abordagem sistemática e rigorosa para alcançar os melhores resultados possíveis.

# **Entendimento dos dados**

Os dados estão divididos em 13 safras (tendo a duração de 1 mês cada) entre os períodos de 01/2019 a 01/2020.

As variáveis são censuradas, tendo apenas os nomes "VAR_1", "VAR_2", "VAR_3", etc.

As variáveis não apresentam um alto percentual de nulos, tendo apenas 1 coluna com mais de 1% de nulos.

## **Preparação dos dados**

1- Foi realizada a divisão dos dados em treino e teste utilizando a validação temporal Out-of-time;

2- Foi realizado o tratamento dos valores nulos, substituindo os valores faltantes pela média de cada coluna da base de treino (foi aplicado o mesmo valor de média na base teste);

3- Foram selecionadas as variáveis mais importantes utilizando Feature Importance;

4- As variáveis numéricas foram padronizadas;

5- Foi verificada a correlação de Pearson das variáveis numéricas;

6- Foi verificada a linearidade com o Log Odds;

7- As variáveis que não eram lineares foram transformadas ou categorizadas.

# **Modelagem**

Foi utilizado o modelo de Regressão Logística, por ser altamente explicável e fácil de se obter insights sobre o peso de cada variável na decisão final.

# **Avaliação do modelo**

O modelo foi avaliado utilizando as métricas de AUC, KS e Gini, obtendo os seguintes valores na base de teste:

- AUC: 0.7859;

- Gini: 0.5718;

- KS: 0.4335.

Também foi calculado o Índice de Estabilidade Populacional (PSI), que ficou em torno de 0.0452.

# **Conclusão e Impactos no Negócio**

O modelo de regressão logística desenvolvido apresentou resultados bastante positivos, com destaque para o valor de PSI (Population Stability Index) de 0,0452, indicando uma excelente estabilidade entre a base de desenvolvimento e a base de teste. Isso significa que o perfil dos solicitantes de crédito se manteve consistente ao longo do tempo, o que reforça a confiança na capacidade do modelo de manter sua performance quando for aplicado em produção.

## **Principais impactos no negócio:**

- **Redução de Perdas com Inadimplência:** A maior precisão na identificação de clientes com maior risco permite minimizar a concessão de crédito para perfis com alta probabilidade de default.

- **Expansão Controlada da Base de Clientes:** Com o modelo, a instituição pode ampliar a oferta de crédito para clientes com bom potencial, sem comprometer a qualidade da carteira.

- **Tomada de Decisão mais Rápida e Consistente:** A automatização do processo, aliada à interpretabilidade da regressão logística, traz agilidade e uniformidade nas decisões, reduzindo a dependência de análises subjetivas.

- **Transparência e Compliance:** O modelo atende às exigências de explicabilidade, facilitando auditorias internas e externas, além de garantir conformidade com as políticas de risco e regulamentações vigentes.

- **Governança de Risco:** A estabilidade populacional validada pelo PSI fortalece a governança do modelo, criando uma base sólida para monitoramento contínuo e eventuais recalibrações futuras.


## **Considerações finais**

De forma geral, o projeto entrega uma solução que equilibra crescimento da carteira, controle de risco e eficiência operacional.

A partir deste ponto, o foco passa a ser o acompanhamento periódico do desempenho do modelo, garantindo que ele continue aderente ao perfil dos clientes ao longo do tempo e alinhado às estratégias da instituição.
