### Mapa Mental: IAs Generativas

#### O que são IAs Generativas

1. **Introdução às Redes Generativas**
    - Redes Generativas
        - Machine Learning
        - O Mundo da IA
            - IA Geral
            - IA Restrita
            - Machine Learning
        - O que é Visão Computacional?
            - Sensoriamento: Imagens
            - Processamento de Imagens
            - Análise: Machine Learning
        - O que são Redes Neurais?
            - Baseada em nossas redes neurais
            - ![Imagem](https://prod-files-secure.s3.us-west-2.amazonaws.com/ef3cbb28-8b53-4bfc-b01a-c8c6302bcb17/f86bd477-85b0-4b88-931f-db4903b1640d/image.png)

2. **Modelos Autoregressivos**
    - Análise de Características
    - Diferença entre as Redes Deep
        - Machine Learning
            - Input
            - Feature Extraction
            - Classification
            - Output
        - Deep Learning
            - Input
            - Feature Extraction + Classification
            - Output
    - Dados a serem Interpretados
        - Entrada - Feature Map
            - Campo Receptivo Local
        - Convolução Espacial com n Filtros
            - Filtros i com Pesos w
            - n Feature Maps
            - f(i,x,y) Pixel de Saída
    - Análise de Característica (Features)
        - Imagem Entrada 64x64x3
        - 4 Filtros 5x5x3
        - 4 Feature Maps 64x64 (Tensor 64x64x4)
        - 5 Filtros 3x3x4
        - 5 Feature Maps 64x64 (Tensor 64x64x5)
    - Como são as Features?

3. **Algoritmos de Treinamento para Redes Generativas**
    - Mas o que gera um Treinamento?
        - Dados de Aprendizado
            - Pesos gerados no treinamento
                - Camada de Entrada
                    - Pesos de Conexão da Camada de Entrada
                - k Camadas Escondidas
                    - Pesos de Conexão das Camadas Escondidas
                    - Sentido da Propagação
                - Camada de Saída
            - Algoritmo Neural
                - Modelo de Treinamento
                    - Relação dos Pesos
                - Algoritmo
                    - Início
                    - Gera Pesos Aleatórios
                    - Recebe Sinais de Entrada
                    - Cálculo de Resposta da Rede
                    - Comparador dos Valores Calculados e Valores Desejados
                    - Erro Aceitável
                        - Sim: Fim
                        - Não: Ajuste dos Pesos Proporcionais ao Erro
                            - Recebe Sinais de Entrada
            - Framework Keras
                - Importando Modelos de RNA
                    - Classify ImageNet Classes with ResNet50
            - Colab
                - Exemplo de RNA no Colab
                    - Input Layer
                    - Hidden Layer
                    - Output Layer

4. **Redes Adversárias e Generativas**
    - Redes Adversárias
        - O Sistema de Imitação aplica os conhecimentos que tem para produzir milhares de novas imagens no estilo de Picasso, usando características de obras de arte existentes, enquanto outros sistemas de IA avaliam a semelhança entre as criações e o estilo e gera uma classificação. Os resultados não convincentes são retornados ao sistema de imitação para serem aprimorados.
        - As GANs vão além da simples memorização do que já foi feito: elas criam conteúdo novo. Por isso, elas são consideradas um marco importante pela comunidade de pesquisa de IA. Designers e arquitetos já exploram o potencial desses sistemas para gerar modelos 3D de carros e edifícios com base no estudo de fotos em 2D.
