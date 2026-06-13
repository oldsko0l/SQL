# 🔐 TCL e DCL no SQL

Além de manipular e consultar dados, o SQL oferece linguagens específicas para controlar **transações** e **permissões de acesso**.

---

# 🔄 TCL — Transaction Control Language

A **TCL** é a linguagem responsável pelo controle de transações, garantindo **segurança**, **consistência** e **integridade** dos dados.

## O que é uma Transação?

Uma transação é um **conjunto de operações executadas como uma única unidade lógica**. Ou tudo acontece, ou nada acontece:

```sql
UPDATE conta SET saldo = saldo - 100 WHERE id = 1;
UPDATE conta SET saldo = saldo + 100 WHERE id = 2;
```

> Se qualquer uma dessas duas operações falhar, nenhuma das duas deve ser confirmada.

---

## 🧰 Principais Comandos TCL

| Comando | Função |
| :--- | :--- |
| **BEGIN / START TRANSACTION** | Inicia uma transação. |
| **COMMIT** | Confirma e salva permanentemente todas as alterações. |
| **ROLLBACK** | Desfaz todas as alterações desde o último `BEGIN`. |
| **SAVEPOINT** | Cria um ponto de restauração parcial dentro da transação. |

---

## 🧱 Propriedades ACID

Todo banco de dados robusto garante as quatro propriedades ACID para suas transações:

| Letra | Propriedade | O que garante |
| :--- | :--- | :--- |
| **A** | **Atomicidade** | Tudo ou nada — uma transação não pode ser parcialmente confirmada. |
| **C** | **Consistência** | Os dados permanecem válidos e íntegros após a transação. |
| **I** | **Isolamento** | Transações simultâneas não interferem umas nas outras. |
| **D** | **Durabilidade** | Após o `COMMIT`, os dados permanecem salvos mesmo em caso de falha. |

---

---

# 🛡️ DCL — Data Control Language

A **DCL** é a linguagem responsável pelo controle de **permissões e segurança**, definindo quem pode acessar, alterar ou excluir dados.

## 🧰 Principais Comandos DCL

| Comando | Função |
| :--- | :--- |
| **GRANT** | Concede permissões a um usuário. |
| **REVOKE** | Remove permissões de um usuário. |

---

## ➕ GRANT — Concedendo Permissões

```sql
GRANT SELECT, INSERT
ON clientes
TO usuario1;
```

O `usuario1` passa a poder **consultar** e **inserir** dados na tabela `clientes`.

## ➖ REVOKE — Removendo Permissões

```sql
REVOKE INSERT
ON clientes
FROM usuario1;
```

O `usuario1` perde a permissão de inserção, mas mantém as demais que possuía.

---

## 🧩 Exemplo Real de Perfis de Acesso

| Usuário | Permissões |
| :--- | :--- |
| **Admin** | Total (todas as operações). |
| **Vendedor** | `SELECT`, `INSERT` |
| **Cliente** | Apenas `SELECT` |

> **⚠️ Boa prática:** Sempre aplique o princípio do **menor privilégio** — conceda apenas as permissões estritamente necessárias para cada perfil.

---

[⬅️ Página Anterior](aula_9_triggers.md) | [🏠 Voltar ao Início](01-introducao-e-conceitos.md)
