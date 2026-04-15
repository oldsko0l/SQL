# 🔗 Chave Estrangeira (Foreign Key)

A **chave estrangeira** é um campo de uma tabela que aponta para a chave primária de outra tabela. Ela é o que "liga" uma tabela à outra em um banco de dados relacional.

## 🤔 Por que precisamos dela?

| Sem Chave Estrangeira | Com Chave Estrangeira |
| :--- | :--- |
| As tabelas ficam isoladas. | O banco garante a integridade dos dados. |
| Não há garantia de que os dados combinam. | Evita erros e inconsistências. |
| Podem existir registros "órfãos" (sem relação real). | Representa relações do mundo real. |

---

## 🧩 Exemplo Prático

**Tabela: Clientes**

| Id (PK) | Nome |
| :--- | :--- |
| 1 | Ana Silva |
| 2 | João Souza |

**Tabela: Pedidos**

| Id (PK) | clienteId (FK) | Total |
| :--- | :--- | :--- |
| 1001 | 1 | 3500 |
| 1002 | 2 | 200 |
| 1003 | 1 | 1200 |

> O campo `clienteId` na tabela de Pedidos é uma **chave estrangeira** — ele aponta para o `Id` da tabela de Clientes, garantindo que nenhum pedido fique sem um cliente válido.

---

---

# 🗂️ Normalização

**Normalizar** um banco de dados é organizar as informações para que cada dado exista apenas uma vez, evitando repetição, erros e inconsistências nas tabelas.

## 🚫 Forma Não Normalizada (UNF)

Todos os dados estão misturados em uma única tabela, com grupos repetidos:

| OrderID | CustomerName | CustomerPhone | Products | Total |
| :--- | :--- | :--- | :--- | :--- |
| 1001 | Ana Silva | 9999-1111 | Notebook, Mouse | 3500 |
| 1002 | João Souza | 9888-2222 | Teclado | 200 |
| 1003 | Ana Silva | 9999-1111 | Monitor, Cabo HDMI, Mouse | 1200 |

> **⚠️ Problemas:** Dados do cliente repetidos, múltiplos valores em uma célula e difícil de consultar e manter.

---

## 1️⃣ Primeira Forma Normal (1FN)

**Regra:** Os campos devem ser **atômicos** — um único valor por célula.

| OrderID | CustomerName | CustomerPhone | Product | Total |
| :--- | :--- | :--- | :--- | :--- |
| 1001 | Ana Silva | 9999-1111 | Notebook | 3500 |
| 1001 | Ana Silva | 9999-1111 | Mouse | 3500 |
| 1002 | João Souza | 9888-2222 | Teclado | 200 |
| 1003 | Ana Silva | 9999-1111 | Monitor | 1200 |
| 1003 | Ana Silva | 9999-1111 | Cabo HDMI | 1200 |
| 1003 | Ana Silva | 9999-1111 | Mouse | 1200 |

> **⚠️ Problema restante:** Os dados do cliente continuam duplicados e o `Total` pertence apenas ao pedido — ainda existem dependências misturadas na mesma tabela.

---

## 2️⃣ Segunda Forma Normal (2FN)

**Regras:**
* Deve estar na 1FN.
* Remover **dependências parciais**.
* Cada entidade passa a ter sua própria tabela e sua própria chave primária.

**Tabela: Clientes**

| CustomerID | Nome | Telefone |
| :--- | :--- | :--- |
| 1 | Ana Silva | 9999-1111 |
| 2 | João Souza | 9888-2222 |

**Tabela: Pedidos**

| OrderID | CustomerID | Total |
| :--- | :--- | :--- |
| 1001 | 1 | 3500 |
| 1002 | 2 | 200 |
| 1003 | 1 | 1200 |

**Tabela: Itens do Pedido**

| OrderID | Produto |
| :--- | :--- |
| 1001 | Notebook |
| 1001 | Mouse |
| 1002 | Teclado |
| 1003 | Monitor |
| 1003 | Cabo HDMI |
| 1003 | Mouse |

> **⚠️ Problema restante:** O campo `Produto` ainda é um texto livre — está "solto", sem uma tabela própria.

---

## 3️⃣ Terceira Forma Normal (3FN)

**Regras:**
* Deve estar na 2FN.
* Remover **dependências transitivas**.
* Campos não-chave devem depender **apenas** da chave primária.

**Tabela: Clientes**

| CustomerID | Nome | Telefone |
| :--- | :--- | :--- |
| 1 | Ana Silva | 9999-1111 |
| 2 | João Souza | 9888-2222 |

**Tabela: Produtos**

| ProductID | NomeProduto |
| :--- | :--- |
| 10 | Notebook |
| 11 | Mouse |
| 12 | Teclado |
| 13 | Monitor |
| 14 | Cabo HDMI |

**Tabela: Pedidos**

| OrderID | CustomerID | Total |
| :--- | :--- | :--- |
| 1001 | 1 | 3500 |
| 1002 | 2 | 200 |
| 1003 | 1 | 1200 |

**Tabela: Itens do Pedido**

| OrderID | ProductID |
| :--- | :--- |
| 1001 | 10 |
| 1001 | 11 |
| 1002 | 12 |
| 1003 | 13 |
| 1003 | 14 |
| 1003 | 11 |

---

## ✅ Resultado Final

Após a normalização, o banco de dados possui:

* **Ausência de redundância** — cada dado existe em apenas um lugar.
* **Relacionamentos claros** — expressos por Chaves Estrangeiras.
* **Estrutura relacional correta** — cada tabela representa uma única entidade.
* **Melhor desempenho, manutenção facilitada e fácil escalabilidade.**

---

[⬅️ Página Anterior](aula_3_dml_e_anatomia_sql.md) | [🏠 Voltar ao Início](01-introducao-e-conceitos.md)
