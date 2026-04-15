# 🔀 Métodos de Combinação no SQL

O SQL oferece duas formas de combinar dados de múltiplas consultas: **JOINs** (horizontal) e **Operadores SET** (vertical).

---

# ↔️ JOINs — Adição de Colunas (Horizontal)

Conectamos tabelas **lateralmente** através de uma coluna comum (Chave).

| Tipo | O que retorna |
| :--- | :--- |
| **INNER JOIN** | Apenas os registros que existem em **ambas** as tabelas. |
| **LEFT JOIN** | Tudo da tabela à **esquerda** + o que houver correspondência à direita. |
| **RIGHT JOIN** | Tudo da tabela à **direita** + o que houver correspondência à esquerda. |
| **FULL JOIN** | Tudo de **ambos os lados**, independentemente de haver correspondência. |

## 🏗️ Como Usar JOINs

Ao escrever um JOIN, devemos especificar a relação entre as tabelas com `ON`:

```sql
SELECT
    TabelaA.Nome,
    TabelaB.Pais
FROM
    TabelaA INNER JOIN TabelaB ON TabelaA.id = TabelaB.id;
```

---

# ↕️ Operadores SET — Adição de Linhas (Vertical)

Empilhamos resultados de consultas diferentes, desde que tenham a **mesma estrutura de colunas**.

| Operador | O que retorna |
| :--- | :--- |
| **UNION** | Combina os resultados e **remove duplicados**. |
| **UNION ALL** | Combina tudo, **incluindo duplicados** (mais rápido). |
| **EXCEPT / MINUS** | O que existe no **primeiro** conjunto mas **não** no segundo. |
| **INTERSECT** | Apenas o que é **comum** a ambos os conjuntos. |

## 🏗️ Como Usar Operadores SET

```sql
SELECT
    Nome
FROM
    Clientes
UNION
SELECT
    Nome
FROM
    Funcionarios;
```

> **💡 Dica:** Prefira `UNION ALL` quando não houver risco de duplicatas — ele é mais eficiente pois não executa a etapa de remoção de repetidos.

---

[⬅️ Página Anterior](aula_4_fk_e_normalizacao.md) | [🏠 Voltar ao Início](01-introducao-e-conceitos.md)
