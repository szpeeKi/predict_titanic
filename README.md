# Projeto de Análise e Modelagem de Dados do Titanic

## Descrição do Projeto

Este projeto foi desenvolvido para analisar e modelar os dados do famoso conjunto de dados do Titanic, com o objetivo de prever a sobrevivência dos passageiros com base em características disponíveis. Utilizamos técnicas de aprendizado de máquina e análise estatística para construir um modelo preditivo robusto.

---

## Etapas do Projeto

### 1. **Carregamento e Preparação dos Dados**
- O dataset foi carregado a partir de um arquivo pré-processado (`titanic_tratado.csv`), contendo dados tratados previamente para remover valores ausentes e normalizar variáveis.
- A variável `Name` foi descartada, pois não contribui diretamente para a predição da sobrevivência.
- Para mais detalhes sobre o tratamento de dados, consulte o projeto de tratamento de dados do Titanic [aqui](https://github.com/szpeeKi/TratamentoDeDadosTitanic).

### 2. **Divisão dos Dados**
- Os dados foram divididos em variáveis independentes (`X`) e dependente (`y`), sendo esta última a variável `Survived`, que indica se o passageiro sobreviveu ou não.
- Foi utilizada a técnica de divisão em conjunto de treino (70%), validação (15%) e teste (15%) para garantir a avaliação adequada do modelo.

### 3. **Modelagem**
- O modelo utilizado foi o **Random Forest Classifier**, escolhido pela sua robustez e capacidade de capturar relações não lineares nos dados.
- Um **Grid Search com validação cruzada** foi aplicado para otimizar os hiperparâmetros do modelo, utilizando a métrica de **precisão** como critério principal.

### 4. **Avaliação do Modelo**
- Após a busca pelos melhores hiperparâmetros, o modelo otimizado foi ajustado ao conjunto de treino.
- As predições foram realizadas nos conjuntos de validação e teste, e as matrizes de confusão foram geradas para avaliar o desempenho do modelo em termos de classificação correta.

### 5. **Análise de Importância das Features**
- As importâncias das variáveis foram extraídas do modelo treinado e ordenadas para identificar quais atributos têm maior impacto na predição da sobrevivência.

---

## Resultados Obtidos

- **Melhores Hiperparâmetros**: Os valores ideais para os parâmetros do Random Forest foram identificados por meio do Grid Search.
- **Matrizes de Confusão**: O desempenho do modelo foi avaliado em termos de verdadeiros positivos, falsos positivos, verdadeiros negativos e falsos negativos, tanto no conjunto de validação quanto no de teste.
- **Importância das Variáveis**: A análise revelou as variáveis mais relevantes para a sobrevivência, sendo que a coluna `sex` teve uma grande importância na classificação, o que sugere que o modelo pode ter aprendido um padrão predominante associado a esse atributo.
  
### Observações Importantes
- **Overfitting**: A quantidade limitada de dados pode ter causado overfitting no modelo, resultando em uma alta performance nos dados de treino, mas com um possível desempenho inferior em dados reais.
- **Dependência da Coluna 'Sex'**: O modelo apresentou uma forte dependência da coluna `sex` para classificar a sobrevivência, o que pode indicar um viés no modelo, já que essa característica é um dos fatores mais predominantes na previsão da sobrevivência no Titanic.

---

## Conclusão

Este projeto demonstra uma abordagem completa para análise e modelagem de dados, desde a preparação até a avaliação do modelo. A utilização do Random Forest Classifier, junto com a otimização dos hiperparâmetros, resultou em um modelo preditivo eficiente, mas com limitações devido ao overfitting e à predominância de uma variável específica.

---

## Ferramentas Utilizadas

- **Linguagem de Programação**: Python
- **Bibliotecas**: Pandas, Scikit-learn
- **Técnicas Aplicadas**: Grid Search, Validação Cruzada, Random Forest, Análise de Importância de Features
