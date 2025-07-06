
# MVP de Previsão de Preços de Imóveis no Rio de Janeiro

**Nome**: Felipe Cavalcante Araujo  
**Matrícula**: 4052025000736  
**Dataset**: Base_Imoveis_RJ_tratada.csv (GitHub)  
**Referências**: Este MVP (Produto Mínimo Viável) tomou como base, *insights* do https://drivendata.github.io/cookiecutter-data-science/
e do template disponibilizado pelos professores.

Este projeto apresenta um MVP para a previsão de preços de imóveis na cidade do Rio de Janeiro, utilizando técnicas básicas de análise de dados, pré-processamento e um modelo simples de regressão linear. O objetivo é demonstrar um fluxo inicial para construir um preditor de preços com base em características dos imóveis como área, número de quartos, banheiros, vagas de garagem, IPTU e condomínio.

## Descrição do Problema

Desvendando o Valor de Venda de Imóveis Cariocas. Nosso objetivo com este MVP (Produto Mínimo Viável) é construir um modelo preditivo que nos ajude a estimar o preço de venda de imóveis, utilizando suas características. Ao final, esperamos ter um "mapa" que nos mostre quais fatores realmente fazem a diferença no preço de venda.

## Hipóteses do Problema

*   **Previsibilidade do Valor de Venda**: Podemos realmente prever o valor de venda de um imóvel no Rio de Janeiro usando suas características físicas e localização (mesmo que indiretamente pela distância do centro)?
*   **Correlação entre Área e Valor**: Existe uma correlação positiva entre a área do imóvel e seu valor de venda?
*   **Quartos e Banheiros Influenciam o Valor**: O número de quartos e banheiros tem um impacto significativo no valor de venda?
*   **Custos Adicionais Correlacionados**: Custos como condomínio e IPTU estão correlacionados com o valor de venda?

## Tipo de Problema

Uma Aventura de Regressão Supervisionada. O trabalho é ensinar um algoritmo a aprender a relação entre essas evidências e o resultado, para que ele possa prever o valor de venda para novos imóveis, onde o "resultado" ainda é desconhecido. Embora o dataset contenha informações categóricas como "bairro", neste MVP inicial, focaremos nas pistas numéricas, mantendo a simplicidade sem perder o foco na previsão.

## Seleção de Dados

Nossa fonte de "pistas" é o dataset Base_Imoveis_RJ_tratada.csv disponível no GitHub. Este dataset passou por uma análise inicial, o que nos poupa o trabalho de uma coleta e limpeza extensiva, permitindo-nos focar diretamente na análise e modelagem.

**Limpeza da Base:**

*   Evitado o uso de colunas com informações ambíguas ou sem variabilidade (`Descrição`, `Novidade`, `Acabamento`).
*   Removidas linhas com valores ausentes (NaNs) nas colunas numéricas utilizadas.
*   Foco em colunas mais estruturadas e diretas ("valor", "bairro", "quartos" e "área").

## Atributos do Dataset

*   **area**: A metragem quadrada do imóvel.
*   **quartos**: O número de quartos.
*   **suites**: O número de suítes.
*   **vagas**: O número de vagas de garagem.
*   **banheiros**: O número de banheiros.
*   **distancia_centro**: A distância aproximada do centro da cidade (Não utilizada diretamente neste MVP).
*   **valor ou preco**: O valor de venda do imóvel (Variável alvo).
*   **valor_condominio**: O custo mensal do condomínio.
*   **valor_iptu**: O valor anual do IPTU.
*   **bairro**: O bairro do imóvel (Categórica - Não utilizada diretamente neste MVP).
*   **tipo_imovel**: O tipo do imóvel (Categórica - Não utilizada diretamente neste MVP).

## Fluxo do Projeto

O projeto segue as seguintes etapas:

1.  **Carregamento e Preparação dos Dados**: Carregar o dataset e realizar limpeza inicial, renomeando a coluna alvo e removendo colunas não utilizadas neste MVP.
2.  **Análise de Dados Exploratória (EDA)**: Explorar as características das variáveis numéricas, visualizar distribuições, estatísticas descritivas e a matriz de correlação.
3.  **Pré-Processamento de Dados**: Separar features e target, dividir em conjuntos de treino e teste, e aplicar Padronização (StandardScaler) nas features.
4.  **Modelagem e Avaliação**: Treinar um modelo de Regressão Linear e avaliar seu desempenho utilizando métricas como Erro Quadrático Médio (MSE) e R² no conjunto de teste.
5.  **Realizar Previsões (Exemplo)**: Demonstrar como usar o modelo treinado para fazer uma previsão para um novo imóvel de exemplo.
6.  **Visualização de Resultados**: Comparar graficamente os preços reais e previstos para entender a performance geral do modelo.

## Tecnologias Utilizadas

*   Python
*   Pandas
*   NumPy
*   Matplotlib
*   Seaborn
*   Scikit-learn

## Como Executar

1.  Clone este repositório do GitHub.
2.  Abra o notebook `[Nome_do_Seu_Notebook].ipynb` (ou o nome que você deu ao arquivo `.ipynb`) no Google Colab ou em um ambiente Jupyter.
3.  Execute as células sequencialmente.

Certifique-se de que o arquivo `Base_Imoveis_RJ_tratada.csv` está acessível através do URL especificado no notebook.

## Conclusão

Este MVP valida as hipóteses iniciais e demonstra a viabilidade de prever preços de imóveis no Rio de Janeiro utilizando características numéricas. As análises exploratórias e a matriz de correlação confirmaram a importância de features como área, quartos, banheiros e custos adicionais. O modelo de Regressão Linear, embora básico, serve como um ponto de partida.

Para futuras iterações, a inclusão de variáveis categóricas (como bairro) através de One-Hot Encoding, Feature Engineering mais avançada e a exploração de modelos de regressão mais complexos (como Random Forest, Gradient Boosting, etc.) seriam passos importantes para melhorar a precisão e robustez do preditor.

Este projeto é um primeiro passo na complexa tarefa de prever valores de imóveis, oferecendo insights valiosos e uma base para desenvolvimentos futuros.
"""

