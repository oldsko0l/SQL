# 📊 Funções de Agregação no SQL

**Funções de agregação** processam um **conjunto de valores** para retornar um **único valor resumido**. Elas são essenciais para transformar dados brutos em informações estratégicas.

## 🧰 Principais Funções

| Função | Finalidade | Tipos de Dados Compatíveis |
| :--- | :--- | :--- |
| **COUNT** | Conta o número de registros (linhas). | Qualquer tipo |
| **SUM** | Soma os valores de uma coluna. | Apenas Numéricos |
| **AVG** | Calcula a média aritmética dos valores. | Apenas Numéricos |
| **MAX** | Identifica o valor máximo (maior). | Numéricos, Datas e Texto |
| **MIN** | Identifica o valor mínimo (menor). | Numéricos, Datas e Texto |

---

## 🗂️ Cláusula GROUP BY (Agrupamento)

O `GROUP BY` organiza linhas com valores idênticos em grupos e é quase sempre utilizado em conjunto com funções de agregação.

**O que ele faz na prática:**

* **Condensação de Registros:** Reduz múltiplos registros em uma única linha de resumo por grupo.
* **Cálculos em Nível de Grupo:** Permite calcular métricas por segmento — por exemplo, o faturamento total **por categoria de produto**, em vez do faturamento total da loja inteira.

## 🧩 Exemplo Prático

Imagine uma tabela de vendas com registros de diferentes regiões. Ao usar `GROUP BY regiao`, o SQL agrupa todas as vendas de "Sul", "Norte" e "Leste" e entrega **uma única linha por região** com os totais somados:

```sql
SELECT
    regiao,
    SUM(valor) AS total_vendas,
    COUNT(*) AS numero_pedidos
FROM
    vendas
GROUP BY
    regiao;
```

| regiao | total_vendas | numero_pedidos |
| :--- | :--- | :--- |
| Sul | 45.000 | 120 |
| Norte | 30.500 | 87 |
| Leste | 22.800 | 64 |

> **💡 Dica:** Toda coluna que aparece no `SELECT` e **não** é uma função de agregação **deve** estar listada no `GROUP BY`.

---

[⬅️ Página Anterior](aula_6_funcoes_linha_unica.md) | [🏠 Voltar ao Início](01-introducao-e-conceitos.md)
