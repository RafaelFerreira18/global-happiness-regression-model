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
**Registros:** 1.231 países-ano  
**Features:** 14 variáveis

### Variáveis Principais:
- **Happiness Score** (0-10): Variável alvo para regressão
- **Economy (GDP per Capita)**: Contribuição do PIB
- **Family**: Suporte social/familiar
- **Health (Life Expectancy)**: Expectativa de vida
- **Freedom**: Liberdade de escolha
- **Trust (Government Corruption)**: Confiança no governo
- **Generosity**: Generosidade

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
├── world_happiness_report.csv          # Dataset
├── world_happiness_analysis.ipynb      # Notebook principal
├── requirements.txt                    # Dependências
├── README.md                           # Este arquivo
└── LICENSE                             # Licença MIT
```

---

## 🚀 Como Executar

### 1. Clone o repositório
```bash
git clone https://github.com/RafaelFerreira18/global-happiness-regression-model.git
cd global-happiness-regression-model
```

### 2. Crie um ambiente virtual (recomendado)
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
- ✅ ANOVA confirmou diferenças significativas entre regiões (p < 0.001)
- ✅ Distribuição aproximadamente normal da variável alvo

### Modelos de Regressão
| Modelo | MAE | RMSE | R² |
|--------|-----|------|----|
| Baseline (Mean) | ~1.13 | ~1.36 | 0.00 |
| Linear Simples | ~0.72 | ~0.89 | 0.60 |
| Linear Múltipla | ~0.32 | ~0.43 | 0.78 |
| Polinomial (d=2) | ~0.30 | ~0.41 | 0.80 |

### Modelos de Classificação
| Modelo | Accuracy | Precision | Recall | F1-Score | AUC-ROC |
|--------|----------|-----------|--------|----------|---------|
| Naive Bayes | ~0.87 | ~0.87 | ~0.87 | ~0.87 | ~0.93 |
| Logistic Regression | ~0.92 | ~0.92 | ~0.92 | ~0.92 | ~0.96 |

### Otimização
- ✅ Validação cruzada (5-fold) aplicada em 6 modelos de regressão
- ✅ Grid Search: Melhor alpha para Ridge = 1.0
- ✅ Random Search: Otimização de Logistic Regression
- ✅ Comparação manual: Visualizações customizadas com scikit-learn

---

## 📚 Metodologia

### 1. EDA (20% da nota)
- Limpeza e tratamento de ausências
- Visualizações (histogramas, boxplots, pairplots, heatmap)
- Testes estatísticos (Pearson, ANOVA, Shapiro-Wilk)
- Análise de outliers

### 2. Modelagem (40% da nota)
- Baseline com média
- Statsmodels para interpretação (coeficientes, p-valores)
- Sklearn para pipelines reprodutíveis
- Diagnóstico de resíduos completo

### 3. Otimização (30% da nota)
- Validação cruzada estratificada (5-fold)
- Grid/Random Search com scikit-learn
- Comparação manual de 6+ modelos
- Análise de trade-offs com visualizações customizadas

### 4. Documentação (10% da nota)
- Notebook estruturado com Markdown
- Código limpo e comentado
- Reprodutibilidade (seed=42)
- Referências adequadas

---

## 🎓 Insights e Conclusões

### Principais Descobertas
1. **PIB é o principal preditor** de felicidade (correlação 0.78)
2. **Europa Ocidental lidera** os rankings de felicidade
3. **Modelos lineares são suficientes** para capturar a maioria da variação
4. **Classificação multiclasse** alcança >90% de acurácia

### Limitações
- Dados baseados em auto-relato (subjetivos)
- Viés cultural no conceito de "felicidade"
- Multicolinearidade entre algumas features
- Generalização limitada a países similares

### Próximos Passos
- Incluir dados mais recentes (2023-2025)
- Testar modelos ensemble (XGBoost, Random Forest)
- Análise de séries temporais
- Deploy com API REST

---

## 📄 Licença

Este projeto está sob a licença **MIT**. Veja o arquivo [LICENSE](LICENSE) para mais detalhes.

---

## 👤 Autor

**Rafael Ferreira**  
- GitHub: [@RafaelFerreira18](https://github.com/RafaelFerreira18)
- Repositório: [global-happiness-regression-model](https://github.com/RafaelFerreira18/global-happiness-regression-model)

---

## 🙏 Agradecimentos

- **Sustainable Development Solutions Network** pelos dados do World Happiness Report
- **Kaggle** pela plataforma de compartilhamento de dados
- Comunidade open-source das bibliotecas utilizadas

---

## 📞 Contato

Para dúvidas, sugestões ou colaborações, abra uma [issue](https://github.com/RafaelFerreira18/global-happiness-regression-model/issues) no repositório.

---

**⭐ Se este projeto foi útil, considere dar uma estrela no repositório!**
