# ⚙️ Funções de Linha Única no SQL

**Funções SQL** são conjuntos de instruções que recebem um ou mais valores de entrada e retornam um valor de saída — uma transformação por linha.

```
Entrada (Valor)  →  FUNÇÃO  →  Saída (Novo Valor)
```

* **Limpeza:** Remover espaços extras ou caracteres indesejados.
* **Transformação:** Alterar formatos de data ou converter textos.
* **Análise:** Realizar cálculos rápidos por linha.

> **💡 Uso:** Funções de linha única podem ser usadas no `SELECT` (exibir), no `WHERE` (filtrar) e no `ORDER BY` (ordenar).

---

## 🔤 Funções de Texto (String Functions)

**Manipulação:**

| Função | O que faz |
| :--- | :--- |
| **CONCAT** | Une duas ou mais strings (ex: Nome + Sobrenome). |
| **UPPER / LOWER** | Converte o texto para `MAIÚSCULO` ou `minúsculo`. |
| **TRIM** | Remove espaços em branco no início e no fim. |
| **REPLACE** | Substitui um caractere ou trecho de texto por outro. |

**Extração e Medida:**

| Função | O que faz |
| :--- | :--- |
| **LEN** | Retorna a quantidade de caracteres. |
| **LEFT / RIGHT** | Extrai caracteres a partir da esquerda ou direita. |
| **SUBSTRING** | Extrai uma parte específica do texto de qualquer posição. |

---

## 📅 Funções de Data e Hora (Date & Time)

**Cálculos:**

| Função | O que faz |
| :--- | :--- |
| **DATEADD** | Adiciona um intervalo (dias, meses, anos) a uma data. |
| **DATEDIFF** | Calcula a diferença entre duas datas. |

**Extração de Partes:**

| Função | O que faz |
| :--- | :--- |
| **YEAR / MONTH / DAY** | Extraem o ano, mês ou dia numérico. |
| **DATENAME** | Retorna o nome da parte da data (ex: "Janeiro", "Segunda-feira"). |

**Conversão:**

| Função | O que faz |
| :--- | :--- |
| **CAST / CONVERT** | Alteram o tipo de dado (ex: de Texto para Data). |
| **FORMAT** | Define como a data será exibida (ex: `'dd/MM/yyyy'`). |

---

## ❓ Tratamento de Valores Nulos (NULL Functions)

> **⚠️ Por que tratar nulos?** Valores nulos em cálculos geram erros e relatórios imprecisos — sempre trate-os antes de operar.

| Função | O que faz |
| :--- | :--- |
| **ISNULL(valor, substituto)** | Se o valor for nulo, substitui por outro. |
| **COALESCE(v1, v2, ...)** | Retorna o primeiro valor não nulo de uma lista. |
| **NULLIF(v1, v2)** | Retorna nulo se os dois valores forem iguais. |
| **IS NULL** | Operador para filtrar registros sem dados. |

---

## 🔀 Lógica Condicional (CASE)

Funciona como um **"SE… ENTÃO"** (`IF... THEN`) dentro do SQL.

```sql
CASE
    WHEN Condição THEN Resultado
    ELSE Resultado_Padrão
END
```

**Aplicações comuns:**
* **Categorização:** Se `Venda > 1000` então `'Premium'`.
* **Padronização:** Converter `'Alemanha'` para `'DE'`, `'Brasil'` para `'BR'`.

---

## 🪆 Funções Aninhadas (Nested Functions)

É possível usar uma função como **entrada de outra função**, encadeando transformações:

```sql
LEN(LOWER(LEFT('Maria', 2)))
```

| Passo | Função | Resultado |
| :--- | :--- | :--- |
| 1 | `LEFT('Maria', 2)` | `'Ma'` |
| 2 | `LOWER('Ma')` | `'ma'` |
| 3 | `LEN('ma')` | `2` |

---

[⬅️ Página Anterior](aula_5_joins_e_set.md) | [🏠 Voltar ao Início](01-introducao-e-conceitos.md)
