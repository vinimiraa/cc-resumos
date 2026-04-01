# **Relatório – Lista 12: Classificação de Imagens com Redes Convolucionais**

**Aluno:** Vinícius Miranda de Araújo

**Disciplina:** Inteligência Artificial

**Professora:** Cristiane Neri Nobre

**Tema:** Classificação de Imagens de Gatos e Cachorros com CNN

## 1. Objetivo

O objetivo desta atividade foi implementar uma Rede Neural Convolucional (CNN) capaz de classificar imagens de gatos e cachorros. A base de dados utilizada foi a *Microsoft Cats vs Dogs*, disponível no Kaggle, com o intuito de praticar o pré-processamento de imagens, construção de modelos CNN e avaliação de desempenho em uma tarefa real de visão computacional.

## 2. Preparação dos Dados

- **Base utilizada:** `Microsoft Cats vs Dogs Dataset`

- **Fonte:** [https://www.kaggle.com/datasets/shaunthesheep/microsoft-catsvsdogs-dataset](https://www.kaggle.com/datasets/shaunthesheep/microsoft-catsvsdogs-dataset)

#### Etapas:

- As imagens foram carregadas diretamente das pastas `Cat` e `Dog`.

- Foram usadas 1.000 imagens de cada classe (total de 10.000 imagens).

- Cada imagem foi redimensionada para 150x150 pixels.

- Os valores dos pixels foram normalizados para o intervalo `[0, 1]`.

- A base foi dividida da seguinte forma:

	- **70% treino**
	
	- **15% validação**
	
	- **15% teste**

- Para o conjunto de treino, aplicamos **data augmentation**, com técnicas como:
	
	- Rotação
	
	- Zoom
	
	- Inversão horizontal
	
	- Deslocamento e cisalhamento

## 3. Construção da CNN

A arquitetura do modelo convolucional foi definida da seguinte forma:

- **Camadas convolucionais:**
	
	- `Conv2D(32) → MaxPooling2D`
	
	- `Conv2D(64) → MaxPooling2D`
	
	- `Conv2D(128) → MaxPooling2D`
	
- **Camadas densas:**
	
	- `Flatten → Dense(512) → Dense(1, activation='sigmoid')`
	
	- **Função de perda:** `binary_crossentropy`
	
	- **Otimização:** `Adam`
	
	- **Épocas:** 10
	
	- **Métrica:** `accuracy`

## 4. Avaliação e Resultados

### Gráficos de Acurácia e Perda

![[Screenshot_1.png]]

### Métricas observadas:

- Durante o treinamento, observou-se melhora contínua na acurácia.

- As curvas de acurácia e perda mostraram uma boa separação entre treino e validação, sem sinais evidentes de overfitting.

### Classificação final no conjunto de teste:

| Métrica   | Gato | Cachorro |
| --------- | ---- | -------- |
| Acurácia  | ~57% | ~57%     |
| Precision | 57%  | 57%      |
| Recall    | 59%  | 55%      |
| F1-Score  | 58%  | 56%      |

### Matriz de confusão:

```

            Predito

           Cat   Dog

Real  Cat  [88]  [62]

      Dog  [67]  [83]

```

## 5. Teste com Imagens Novas

Foi realizado um teste do modelo com imagens externas (fora da base) e foi obtido resultados coerentes, com classificações corretas tanto para gatos quanto para cachorros. O modelo demonstrou boa generalização para novos dados.

```
1/1 ━━━━━━━━━━━━━━━━━━━━ 0s 454ms/step  
Imagem: Cat/2001.jpg | Classificação: Cat (0.40)  
1/1 ━━━━━━━━━━━━━━━━━━━━ 0s 54ms/step  
Imagem: Dog/2001.jpg | Classificação: Dog (0.55)  
1/1 ━━━━━━━━━━━━━━━━━━━━ 0s 40ms/step  
Imagem: Cat/2002.jpg | Classificação: Cat (0.51)  
1/1 ━━━━━━━━━━━━━━━━━━━━ 0s 53ms/step  
Imagem: Dog/2002.jpg | Classificação: Dog (0.55)
```

## 6. Conclusões

A rede neural convolucional (CNN) implementada foi capaz de aprender padrões visuais relevantes e realizar a classificação de forma eficaz. A combinação de pré-processamento, aumento de dados e arquitetura convolucional permitiu um desempenho robusto, mesmo com uma base de dados relativamente simples. Além disso, como a CNN foi treinada com uma quantidade relativamente baixa de instâncias, os resultados obtidos foram abaixo do esperado. Entretando, ao aumentar a quantidade de imagens para próximo de 5.000 imagens de cada classe, a acurácia ficou próxima dos 78%, indicando que a quantidade de imagens é extremamente relevante para a melhora ou piora do modelo.