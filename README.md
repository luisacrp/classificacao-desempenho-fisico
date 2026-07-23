# Classificação de Desempenho Físico: Abordagem Linear Bidimensional

## Objetivo
Desenvolver um classificador binário de aprendizado de máquina para prever se um indivíduo possui desempenho físico acima ou abaixo da média. O projeto foca na utilização de duas variáveis biológicas (percentual de gordura e contagem de abdominais) para criar uma fronteira de decisão linear bidimensional, garantindo total interpretabilidade geométrica.

## Integrantes
* Josan Silva dos Santos Junior
* Luísa Costa Rodrigues Pereira
* Sarah Beatriz Barbosa dos Santos

## Fonte dos Dados
* **Dataset:** Body Performance Dataset
* **Origem:** Korea Sports Promotion Foundation (disponível no Kaggle)
* **Volumetria:** 13.392 registros únicos e 12 atributos originais.
* **Link:** [https://www.kaggle.com/datasets/kukuroo3/body-performance-dataset](https://www.kaggle.com/datasets/kukuroo3/body-performance-dataset)

## Tipo da Tarefa
* **Aprendizado Supervisionado:** Classificação Binária.
* **Alvo (Target):** 1 (Alto Desempenho - Classes originais A e B) | 0 (Baixo Desempenho - Classes originais C e D). Balanceamento perfeito de 50/50.

## Modelos Utilizados
1. **DummyClassifier (Baseline):** Ponto de partida aleatório utilizando estratégia estratificada.
2. **SGDClassifier:** Classificador linear que otimiza os pesos da fronteira de decisão através da função de perda *hinge* (Modelo Final Escolhido).
3. **RandomForestClassifier:** Modelo ensemble baseado em 100 árvores de decisão.

## Principais Resultados
* **Melhor Modelo:** SGDClassifier (Acurácia de **63.76%** no conjunto de teste).
* O modelo linear superou o Random Forest, indicando que a relação entre as variáveis escolhidas possui natureza majoritariamente linear.
* O modelo escolhido apresentou um Recall de 72% para a classe de alto desempenho.
* Foi possível extrair os pesos sinápticos e o viés do SGD para desenhar a reta de separação geométrica, garantindo um modelo totalmente explicável e transparente, optando pela interpretabilidade visual em detrimento da acurácia de um modelo multidimensional (caixa preta).

## Organização dos Arquivos
├── data/

│   └── bodyPerformance.csv

├── notebooks/

│   └── projeto_final.ipynb

└── README.md

## Como Abrir e Executar no Google Colab
1. Faça o download do arquivo `projeto_final.ipynb` localizado na pasta `notebooks/` deste repositório.
2. Acesse o [Google Colab](https://colab.research.google.com/).
3. Vá em `Arquivo > Fazer upload de notebook` e selecione o arquivo baixado.
4. Faça o download do arquivo `bodyPerformance.csv` na pasta `data/` deste repositório e faça o upload dele na aba de arquivos (ícone de pasta na lateral esquerda) dentro do próprio Google Colab.
5. Execute as células em ordem, de cima para baixo.

## Divisão das Contribuições
* **Luísa Costa:** Compreensão dos dados, estruturação inicial da base (remoção de duplicatas, binarização) e formulação da defesa metodológica (trade-off entre acurácia e interpretabilidade geométrica).
* **Josan Silva:** Análise exploratória, geração das visualizações (histogramas, gráfico de dispersão, matriz de correlação) e montagem do pipeline de pré-processamento (estratificação e StandardScaler).
* **Sarah Beatriz:** Treinamento dos algoritmos, avaliação das métricas (Matriz de Confusão, Relatório de Classificação) e plotagem da avaliação geométrica final da fronteira de decisão.

## Vídeo de Apresentação
[]

## Declaração de Uso de Inteligência Artificial
Declaramos o uso de ferramentas de Inteligência Artificial neste trabalho:
* **Ferramenta utilizada:** ChatGPT (OpenAI) e Gemini (Google).
* **Finalidade:** Geração de snippets para visualização de dados (Matplotlib/Seaborn), auxílio na formulação matemática da fronteira de decisão e revisão dos textos interpretativos.
* **Verificação:** Todo o código gerado foi revisado, testado exaustivamente e ajustado manualmente no Google Colab. As interpretações teóricas, as justificativas metodológicas e a análise dos gráficos foram elaboradas, validadas e compreendidas por todos os integrantes do grupo.
