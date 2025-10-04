# 🤖 Question Similarity Analysis with SBERT

Um projeto de análise de similaridade entre questões usando Sentence-BERT (SBERT) para competições de Machine Learning.

## 📊 Visão Geral

Este projeto implementa um modelo de deep learning para avaliar a similaridade semântica entre pares de sentenças, utilizando a arquitetura Sentence-BERT. O modelo é treinado para prever scores de similaridade numa escala de 0 a 5, onde 0 indica sentenças completamente diferentes e 5 indica sentenças semanticamente idênticas.

## 🎯 Objetivo

Desenvolver um sistema capaz de:
- Analisar a similaridade semântica entre pares de questões
- Prever scores de similaridade com alta precisão
- Ser otimizado para execução em ambiente Kaggle

## 📁 Estrutura do Projeto

```
questionSimilarity/
├── sbert.ipynb           # Notebook principal com todo o pipeline
├── README.md            # Este arquivo
└── .gitignore          # Arquivos a serem ignorados pelo Git
```

## 🛠 Tecnologias Utilizadas

### Core Libraries
- **Python 3.8+**
- **PyTorch** - Framework de deep learning
- **Sentence-Transformers** - Biblioteca para embeddings de sentenças
- **Scikit-learn** - Métricas e divisão de dados

### Data Science & Visualization
- **Pandas** - Manipulação de dados
- **NumPy** - Computação numérica
- **Matplotlib** & **Seaborn** - Visualização de dados

### Model Architecture
- **SBERT (all-MiniLM-L6-v2)** - Modelo base pré-treinado
- **CosineSimilarityLoss** - Função de perda
- **EmbeddingSimilarityEvaluator** - Avaliação durante treinamento

## 📈 Metodologia

### 1. **Análise Exploratória de Dados (EDA)**
- Análise da distribuição dos scores de similaridade
- Verificação de valores nulos e balanceamento
- Visualizações estatísticas dos dados

### 2. **Preparação dos Dados**
- Normalização dos scores para o intervalo [0, 1]
- Divisão em conjuntos de treino/validação (80/20)
- Criação de objetos `InputExample` para o SBERT

### 3. **Configuração do Modelo**
- Carregamento do modelo `all-MiniLM-L6-v2` pré-treinado
- Configuração da função de perda `CosineSimilarityLoss`
- Setup do avaliador com similaridade coseno

### 4. **Treinamento**
- **Épocas**: 4
- **Batch Size**: 16
- **Warmup Ratio**: 0.1
- **Otimização**: AdamW com FP16
- **Estratégia de Avaliação**: A cada 100 steps

### 5. **Avaliação**
- Métricas: MSE, MAE, Correlação de Pearson e Spearman
- Avaliação contínua durante o treinamento
- Análise visual dos resultados

## 🚀 Como Executar

### Pré-requisitos
```bash
pip install sentence-transformers datasets accelerate torch pandas matplotlib seaborn scikit-learn
```

### Execução Local
1. Clone o repositório
2. Instale as dependências
3. Execute o notebook `sbert.ipynb` célula por célula

### Execução no Kaggle
1. Faça upload dos arquivos para um dataset do Kaggle
2. Crie um novo notebook no Kaggle
3. Copie o conteúdo de `sbert.ipynb`
4. Execute todas as células

### Visualizações
O projeto inclui análises visuais abrangentes:
- Distribuição dos scores de similaridade
- Scatter plots de predições vs valores reais
- Histogramas comparativos de distribuições

## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

## 👥 Contribuição

Contribuições são bem-vindas! Por favor:
1. Faça um fork do projeto
2. Crie uma branch para sua feature
3. Commit suas mudanças
4. Push para a branch
5. Abra um Pull Request

## 📞 Contato

- **Autor**: João Lucas
- **Projeto**: Question Similarity Analysis
- **Data**: Outubro 2025

---

⭐ Se este projeto foi útil para você, considere dar uma estrela no repositório!