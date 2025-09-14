Show, mestre 🚀
Peguei sua estrutura de tabelas e adaptei o `.md` que você tinha pro formato do **Students Performance**, já com os tipos de dados e descrições de cada camada.

Aqui está a versão atualizada:

---

# Data Model: Open Food Facts

Este documento descreve a modelagem de dados em três camadas: **System of Record (SOR)**, **System of Truth (SOT)** e **Specification (SPEC)**.

---

## 1. System of Record (SOR)

**Tabela:** `sor_students`

Representa os dados brutos, exatamente como chegam do arquivo `.csv`. É a primeira camada de armazenamento, garantindo que tenhamos uma cópia fiel dos dados originais.

* **Propósito:** Ingestão e arquivamento dos dados brutos.
* **Estrutura:** Colunas correspondem ao dataset original, sem limpeza ou transformação.

| Coluna                                   | Tipo de Dado (SQL) | Descrição                                                   |
| ---------------------------------------- | ------------------ | ----------------------------------------------------------- |
| id                                       | INT PRIMARY KEY    | Código único do aluno (ID).                                 |
| gender                                   | VARCHAR(20)        | Gênero do aluno.                                            |
| race_ethnicity                           | VARCHAR(50)        | Etnia racial do aluno.                                      |
| parental_level_of_education              | VARCHAR(50)        | Descrição do nível de ecuação parental do estudante.        |
| lunch                                    | VARCHAR(20)        | Nível de alimentação.                                       |
| test_preparation_course                  | VARCHAR(20)        | Cursos prepatatórios para os testes.                        |
| math_score                               | INT                | Nota atingida em matemática.                                | 
| reading_score                            | INT                | Nota atingida em leitura.                                   |
| writing_score                            | INT                | Nota atingida em escrita.                                   |

---

## 2. System of Truth (SOT)

**Tabela:** `sot_math`

Esta camada representa a "versão única da verdade". Os dados da SOR são limpos, padronizados e enriquecidos. É a base confiável para análises e modelagem.

* **Propósito:** Fornecer dados limpos e consistentes.
* **Transformações Aplicadas:**

  * Padronização de colunas com os dados dos alunos.
  * Remoção de colunas não essenciais para análise/modelagem.

| Coluna                                   | Tipo de Dado (SQL) | Descrição                                                   |
| ---------------------------------------- | ------------------ | ----------------------------------------------------------- |
| parental_level_of_education              | VARCHAR(255)       | Descrição do nível de ecuação parental do estudante.        |
| lunch                                    | VARCHAR(255)       | Nível de alimentação.                                       |
| test_preparation_course                  | VARCHAR(255)       | Cursos prepatatórios para os testes.                        |
| math_score                               | INT                | Nota atingida em matemática.                                | 
| reading_score                            | INT                | Nota atingida em leitura.                                   |
| writing_score                            | INT                | Nota atingida em escrita.                                   |

---

## 3. Specification (SPEC)

**Tabela:** `spec_food`

Camada final, pronta para ser consumida em modelos de **machine learning**. Contém as variáveis independentes (features) e a variável alvo.

* **Propósito:** Fornecer dataset já limpo e pronto para modelagem.
* **Estrutura:** Geralmente é uma cópia ou visão da `sot_math`.

| Coluna                                   | Tipo de Dado (SQL) | Descrição                                                   |
| ---------------------------------------- | ------------------ | ----------------------------------------------------------- |
| parental_level_of_education              | VARCHAR(255)       | Descrição do nível de ecuação parental do estudante.        |
| lunch                                    | VARCHAR(255)       | Nível de alimentação.                                       |
| test_preparation_course                  | VARCHAR(255)       | Cursos prepatatórios para os testes.                        |
| math_score                               | INT                | Nota atingida em matemática.                                | 
| reading_score                            | INT                | Nota atingida em leitura.                                   |
| writing_score                            | INT                | Nota atingida em escrita.                                   |

---
