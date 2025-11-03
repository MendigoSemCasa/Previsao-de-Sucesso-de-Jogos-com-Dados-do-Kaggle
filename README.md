# Previsão de Sucesso de Jogos – Machine Learning I

## Autor
**Giordano Bruno Guedes Viana**  
Turma 1486 - Adatech

---

## Descrição do Problema
O objetivo deste projeto é prever se um jogo de videogame será bem-sucedido com base em:
- Ano de lançamento  
- Plataforma  
- Gênero  
- Publicadora (Publisher)

O sucesso foi definido como **vendas globais acima da mediana** do dataset.  
Trata-se de um problema de **classificação supervisionada binária**.

---

## Fonte de Dados
**Dataset:** [Kaggle - Video Game Sales](https://www.kaggle.com/datasets/gregorut/videogamesales)

**Total:** 16.598 registros  
**Após limpeza:** ~8.000 registros

Colunas utilizadas:
- `Year`
- `Platform`
- `Genre`
- `Publisher`
- `Global_Sales` (para definir a variável alvo `Success`)

---

## Metodologia
1. **Pré-processamento:**
   - Remoção de colunas irrelevantes (`Name`, `Rank`)
   - Exclusão de valores ausentes
   - Normalização (`StandardScaler`)
   - Codificação (`OneHotEncoder`)

2. **Divisão dos dados:**
   - 80% treino / 20% teste (estratificado)

3. **Modelos testados:**
   - Logistic Regression
   - Random Forest

4. **Avaliação:**
   - Métrica principal: *Accuracy*
   - *GridSearchCV* para ajuste de hiperparâmetros

---

## Resultados

| Modelo | Acurácia |
|--------|-----------|
| Logistic Regression | 0.718 |
| Random Forest | **0.724** |

**Melhor modelo:** Random Forest  
**Acurácia final:** 72,4%

---

## Análise Crítica
As variáveis utilizadas (Ano, Plataforma, Gênero, Publicadora) fazem sentido para prever tendências históricas de sucesso,  
mas não representam fatores causais diretos — faltam variáveis como qualidade do jogo, marketing ou franquia.

Portanto, o modelo serve como **apoio a decisão estratégica**, e não como previsão determinística.
