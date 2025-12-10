# World Happiness Report - Análise e Modelagem Preditiva

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![License](https://img.shields.io/badge/License-MIT-green)
![Status](https://img.shields.io/badge/Status-Complete-success)

## 📋 Descrição do Projeto

Este projeto aplica técnicas de **Machine Learning** e **Análise Estatística** para investigar os fatores que influenciam a felicidade dos países ao redor do mundo, utilizando dados do **World Happiness Report** (2015-2022).

### 🎯 Objetivos

1. Realizar análise exploratória completa (EDA) com testes estatísticos
2. Implementar modelos de regressão (Linear Simples, Múltipla, Polinomial)
3. Implementar modelos de classificação (Naive Bayes, Regressão Logística)
4. Avaliar desempenho com métricas apropriadas
5. Otimizar modelos com validação cruzada e tuning de hiperparâmetros
6. Comparar resultados com visualizações customizadas

---

## 📊 Dataset

**Fonte:** [Kaggle - World Happiness Report](https://www.kaggle.com/datasets/unsdsn/world-happiness)  
**Licença:** CC0: Public Domain  
**Período:** 2015-2022  
**Registros:** 1.367 países-ano (1.366 após limpeza)  
**Features:** 9 variáveis (5 features preditoras + variável alvo)

### Variáveis Principais:
- **Happiness Score** (0-10): Variável alvo para regressão
- **Economy (GDP per Capita)**: Contribuição do PIB - FEATURE
- **Family**: Suporte social/familiar - FEATURE
- **Health (Life Expectancy)**: Expectativa de vida - FEATURE
- **Freedom**: Liberdade de escolha - FEATURE
- **Generosity**: Generosidade - FEATURE
- **Country**: Nome do país
- **Region**: Região geográfica
- **year**: Ano da coleta

**Nota:** Dataset atual utiliza metodologia consistente. Colunas Trust (Government Corruption) e Dystopia Residual foram removidas devido a mudanças metodológicas pós-2016 no relatório original.

---

## 🛠️ Tecnologias Utilizadas

### Linguagem
- Python 3.8+

### Bibliotecas Obrigatórias
- **pandas**: Manipulação de dados
- **seaborn**: Visualização
- **statsmodels**: Modelagem estatística e testes
- **scikit-learn**: Machine Learning (validação cruzada, Grid/Random Search)

### Bibliotecas Adicionais
- numpy, matplotlib, scipy, jupyter

---

## 📁 Estrutura do Repositório

```
global-happiness-regression-model/
│
├── world_happiness_report 2.csv        # Dataset principal (usado no projeto)
├── world_happiness_report.csv          # Dataset alternativo
├── world_happiness_analysis.ipynb      # Notebook principal com análises completas
├── requirements.txt                    # Dependências
├── README.md                           # Este arquivo
├── GUIA_INTEGRANTE_1_RAFAEL.md         # Guia de apresentação - Parte 1
├── GUIA_INTEGRANTE_2.md                # Guia de apresentação - Parte 2
├── GUIA_APRESENTACAO.md                # Guia geral de apresentação
├── APRESENTACAO_COMPLETA.md            # Slides completos
```

---

## 🚀 Como Executar

### 1. Clone o repositório
```bash
git clone https://github.com/RafaelFerreira18/global-happiness-regression-model.git
cd global-happiness-regression-model
```

### 2. Crie um ambiente virtual com Python menor ou igual ao 3.11 (recomendado)
```bash
python -m venv venv
source venv/bin/activate  # Linux/Mac
# ou
venv\Scripts\activate     # Windows
```

### 3. Instale as dependências
```bash
pip install -r requirements.txt
```

### 4. Execute o Jupyter Notebook
```bash
jupyter notebook world_happiness_analysis.ipynb
```

### 5. Execute as células sequencialmente
⚠️ **Importante:** Execute todas as células na ordem para garantir reprodutibilidade.

---

## 📈 Principais Resultados

### Análise Exploratória
- ✅ Correlações fortes identificadas: Economy (0.78), Family (0.74), Health (0.72)
- ✅ **Testes estatísticos rigorosos aplicados:**
  - Shapiro-Wilk: teste de normalidade (p = 0.0023)
  - ANOVA: diferenças significativas entre regiões (F = 189.47, p < 0.001)
  - Teste t: gap Europa Ocidental vs África Subsaariana (p < 0.001)
  - Qui-Quadrado: associação Região × Categoria de Felicidade (p < 0.001)
- ✅ Distribuição aproximadamente normal da variável alvo

### Modelos de Regressão
| Modelo | MAE | RMSE | R² |
|--------|-----|------|----|---|
| Baseline (Mean) | 0.891 | 1.126 | 0.000 |
| Linear Simples | 0.551 | 0.702 | 0.605 |
| Linear Múltipla | 0.315 | 0.425 | **0.828** |
| Polinomial (d=2) | 0.298 | 0.401 | 0.842 |
| Ridge (Tuned) | 0.313 | 0.423 | 0.830 |
| **Extra Trees (PyCaret)** | **0.255** | **0.351** | **0.891** |

### Modelos de Classificação
| Modelo | Accuracy | Precision | Recall | F1-Score | AUC-ROC |
|--------|----------|-----------|--------|----------|---------|---|
| Naive Bayes | 0.873 | 0.876 | 0.873 | 0.873 | 0.952 |
| Logistic Regression | 0.925 | 0.928 | 0.925 | 0.925 | 0.982 |
| Logistic (Tuned) | 0.928 | 0.930 | 0.928 | 0.928 | 0.983 |
| **Random Forest (PyCaret)** | **0.974** | **0.974** | **0.974** | **0.974** | **0.997** |

### Otimização
- ✅ Validação cruzada (5-fold) aplicada em todos os modelos
- ✅ Grid Search: Ridge com alpha = 0.1 (R² = 0.830)
- ✅ Random Search: Logistic Regression otimizada (Accuracy = 0.928)
- ✅ **PyCaret AutoML:** Testados 15+ modelos automaticamente
  - Regressão: Extra Trees venceu com **R² = 0.891**
  - Classificação: Random Forest venceu com **Accuracy = 0.974**
- ✅ Comparação completa: 7 modelos de regressão, 6 de classificação


## 🎓 Insights e Conclusões

### Principais Descobertas
1. **PIB é o principal preditor** de felicidade (correlação 0.78, p < 0.001)
2. **Trio crucial:** Economy (0.78), Family (0.74), Health (0.72) explicam ~80% da felicidade
3. **Europa Ocidental lidera** com média 6.89 vs África Subsaariana 4.15 (gap de 2.74 pontos)
4. **89.1% da variância explicada** com Extra Trees (PyCaret)
5. **97.4% de accuracy** em classificação com Random Forest
6. **Todas as 5 hipóteses confirmadas** com alta significância estatística

### Limitações
- Dados baseados em auto-relato (subjetivos)
- Viés cultural no conceito de "felicidade"
- Multicolinearidade entre algumas features
- Generalização limitada a países similares

## 📄 Licença

Este projeto está sob a licença **MIT**. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.


**⭐ Se este projeto foi útil, considere dar uma estrela no repositório!**
