### Resumo dos slides

#### Aula 11: Aprendizagem Baseada em Instâncias - KNN
- **Conceito Geral**: Não há uma descrição explícita da hipótese; apenas os exemplos são armazenados. Quando uma nova instância aparece, a relação com os exemplos armazenados é usada para classificá-la.
- **K-Nearest Neighbor (KNN)**: Método que classifica uma nova instância com base nos k exemplos mais próximos no espaço n-dimensional.
  - **Cálculo da Distância**: Geralmente usa distância Euclidiana.
  - **Valores Discretos**: Classificação baseada no valor mais comum entre os k vizinhos.
  - **Valores Contínuos**: Calcula a média ponderada dos valores.
  - **Ponderação por Distância**: Exemplos mais próximos têm maior peso.
- **Desvantagens**:
  - Sensível à "maldição da dimensionalidade" (muitos atributos irrelevantes podem impactar a performance).
  - Computacionalmente caro.
- **Melhorias**:
  - Indexação com árvores Kd para melhorar desempenho.
  - Seleção de atributos relevantes por validação cruzada.
  - Escolha de k ideal (geralmente entre 5 e 10 para problemas com baixa dimensionalidade).

---

#### Aula 12: Pré-Processamento de Dados
- **Etapas do Pré-Processamento**:
  1. **Integração de Dados**: Combina conjuntos de dados, lidando com inconsistências.
  2. **Amostragem**: Seleção de uma amostra representativa para melhorar eficiência computacional.
     - Técnicas: Amostragem simples, estratificada, progressiva.
  3. **Balanceamento de Dados**: Reduz problemas com classes desbalanceadas (e.g., replicação da classe minoritária).
  4. **Limpeza de Dados**: Tratamento de dados incompletos, inconsistentes, redundantes ou com ruídos.
  5. **Transformação de Dados**:
     - **Normalização**: Escala os valores entre [0, 1].
     - **Discretização**: Cria faixas para variáveis contínuas.
     - **Transformação de variáveis categóricas**: Ex.: one-hot encoding.
  6. **Redução de Dimensionalidade**:
     - **Agregação**: Combinação de atributos.
     - **Seleção de Atributos**: Identifica os mais relevantes para o modelo.
- **Avaliação de Modelos**:
  - Uso de métricas como erro, precisão e matrizes de confusão.
  - Métodos de validação: Holdout, k-fold cross-validation, leave-one-out, bootstrap.

---

### Possíveis perguntas de prova
1. **Aula 11**:
   - Qual a diferença entre classificação por KNN para valores discretos e contínuos?
   - Explique como a ponderação por distância pode melhorar o desempenho do KNN.
   - Quais os desafios do KNN em problemas de alta dimensionalidade?
   - Cite e explique uma técnica para selecionar o valor ideal de k.

2. **Aula 12**:
   - Por que a normalização é importante em alguns algoritmos de aprendizado de máquina?
   - Quais as principais diferenças entre amostragem simples e amostragem estratificada?
   - Como lidar com dados desbalanceados em um conjunto de treinamento?
   - Explique a "maldição da dimensionalidade" e como a redução de dimensionalidade pode mitigar esse problema.
   - Diferencie as abordagens de seleção de atributos: filtros, wrappers e embutidos.
   - Qual a importância da validação cruzada na avaliação de modelos?

### Perguntas e Respostas

#### **Aula 11: Aprendizagem Baseada em Instâncias - KNN**

1. **Qual a diferença entre classificação por KNN para valores discretos e contínuos?**  
   - **Resposta**:  
     - Para valores discretos, o KNN retorna o valor mais comum (moda) entre os k vizinhos mais próximos.  
     - Para valores contínuos, ele calcula a média dos valores dos k vizinhos mais próximos.

2. **Explique como a ponderação por distância pode melhorar o desempenho do KNN.**  
   - **Resposta**:  
     - A ponderação por distância atribui pesos maiores aos vizinhos mais próximos e menores aos mais distantes. Isso reduz a influência de exemplos menos relevantes, melhorando a precisão da classificação.

3. **Quais os desafios do KNN em problemas de alta dimensionalidade?**  
   - **Resposta**:  
     - O KNN sofre com a "maldição da dimensionalidade", onde a distância entre os pontos torna-se menos significativa à medida que o número de dimensões aumenta. Além disso, muitos atributos irrelevantes podem afetar negativamente o desempenho do modelo.

4. **Cite e explique uma técnica para selecionar o valor ideal de k.**  
   - **Resposta**:  
     - Uma técnica comum é a validação cruzada, onde o conjunto de dados é dividido em k partes, e o desempenho do modelo é avaliado iterativamente para diferentes valores de k. O valor de k que apresenta melhor desempenho médio é escolhido.

---

#### **Aula 12: Pré-Processamento de Dados**

1. **Por que a normalização é importante em alguns algoritmos de aprendizado de máquina?**  
   - **Resposta**:  
     - A normalização ajusta os valores das variáveis para uma escala comum (geralmente [0, 1]). Isso é crucial para algoritmos que utilizam medidas de distância, como KNN e redes neurais, pois evita que variáveis com escalas maiores dominem as demais.

2. **Quais as principais diferenças entre amostragem simples e amostragem estratificada?**  
   - **Resposta**:  
     - Na amostragem simples, os exemplos são selecionados aleatoriamente, com ou sem reposição. Na amostragem estratificada, a proporção das classes no conjunto original é mantida na amostra, garantindo representatividade.

3. **Como lidar com dados desbalanceados em um conjunto de treinamento?**  
   - **Resposta**:  
     - Pode-se usar técnicas como:
       - Replicação dos exemplos da classe minoritária.
       - Remoção de exemplos da classe majoritária.
       - Atribuição de diferentes custos às classes no algoritmo de aprendizado.

4. **Explique a "maldição da dimensionalidade" e como a redução de dimensionalidade pode mitigar esse problema.**  
   - **Resposta**:  
     - A "maldição da dimensionalidade" ocorre porque o volume do espaço de dados cresce exponencialmente com o número de atributos, tornando a análise e a classificação menos precisas. A redução de dimensionalidade mitiga isso eliminando atributos irrelevantes ou combinando atributos correlacionados.

5. **Diferencie as abordagens de seleção de atributos: filtros, wrappers e embutidos.**  
   - **Resposta**:  
     - **Filtros**: Selecionam atributos antes do aprendizado, baseando-se em critérios estatísticos (e.g., correlação).  
     - **Wrappers**: Avaliam subconjuntos de atributos em conjunto com o algoritmo de aprendizado, otimizando o desempenho.  
     - **Embutidos**: O algoritmo de aprendizado seleciona os atributos relevantes durante o treinamento (e.g., árvores de decisão).

6. **Qual a importância da validação cruzada na avaliação de modelos?**  
   - **Resposta**:  
     - A validação cruzada distribui os dados em k partes (folds) para treinar e testar o modelo várias vezes, garantindo que o desempenho avaliado seja mais representativo e menos influenciado por divisões específicas do conjunto de dados.
!
