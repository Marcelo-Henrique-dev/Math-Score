# Project Model Canvas — Kaggle Chatbot MVP (Exemplo Titanic)

## Contexto
Diversos fatores influenciam notas escolares.

---

## Problema a ser Respondido
Quais fatores mais influenciam boas notas em matemática e leitura?

---

## Pergunta Norteadora
- Qual a nota em matemática ?
---

## Solução Proposta
Desenvolver um **chatbot educacional em Streamlit** que:  
1. Permita upload do arquivo `.csv` do Students Performance.  
2. Treine modelos de:
   - Regressão logística (classificação).  
   - Regressão linear (predição).  
3. Mostre métricas de avaliação (acurácia, f1-score, RMSE).  
4. Explique a importância das variáveis por meio de coeficientes e odds ratios. 
5. Responda perguntas do usuário via chatbot regrado.  

---

## Desenho de Arquitetura
O sistema será estruturado em camadas:  

- **Interface (app/):** Streamlit como front-end para upload, treino e perguntas.  
- **Core (core/):** módulos para dados, features, modelos, explicabilidade e chatbot.  
- **Dados (data/):** pastas para armazenar arquivos brutos, tratados e modelos treinados.  
- **Documentação (docs/):** PMC, arquitetura, governança e testes.  

---

## Resultados Esperados
- Modelo de classificação com acurácia próxima de **75–80%**.  
- Relatório de métricas e importâncias de variáveis.  
- Deploy em **Streamlit Cloud** com documentação completa no GitHub.  

---
