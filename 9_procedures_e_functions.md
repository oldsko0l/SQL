# 🧩 Procedures e Functions no SQL

O SQL é uma linguagem **padronizada** (ANSI/ISO) — comandos como `SELECT`, `INSERT`, `UPDATE` e `DELETE` funcionam de forma quase idêntica em qualquer banco de dados. Pense nele como o **"inglês formal"**: todos se entendem, mas cada banco tem suas próprias extensões e expressões regionais.

---

## 📋 Stored Procedures (Procedimentos Armazenados)

Pense nelas como **scripts de ação** — servem para executar processos com várias etapas.

* **Focadas em ações:** podem inserir, atualizar e deletar dados.
* **Retorno flexível:** podem retornar múltiplos valores ou nenhum.
* **Chamada via:** `EXEC` (T-SQL) ou `CALL` (PL/SQL e MySQL).

| T-SQL (SQL Server) | PL/SQL (Oracle) / MySQL |
| :--- | :--- |
| `CREATE PROCEDURE NovoPreco @id INT` | `CREATE PROCEDURE NovoPreco (id INT)` |
| `AS BEGIN` | `BEGIN` |
| `UPDATE Produtos SET Preco = 10 WHERE ID = @id;` | `UPDATE Produtos SET Preco = 10 WHERE ID = id;` |
| `GO` | `END;` |

---

## 🧮 User-Defined Functions (Funções)

Pense nelas como **calculadoras** — servem para transformar dados ou realizar cálculos específicos.

* **Focadas em cálculos:** obrigatoriamente retornam um valor (ou uma tabela).
* **Ideais para:** lógica matemática ou formatação de strings.
* **Podem ser usadas** diretamente dentro de um `SELECT`.

---

## ⚔️ T-SQL vs. PL/SQL

Ambos seguem o padrão SQL, mas são extensões proprietárias que adicionam lógica de programação (loops, variáveis, tratamento de erros).

| Característica | T-SQL (Transact-SQL) | PL/SQL (Procedural Language/SQL) |
| :--- | :--- | :--- |
| **Principal Mantenedora** | Microsoft | Oracle |
| **Outros Bancos** | MS SQL Server, Sybase (SAP ASE), AWS (Babelfish) | IBM (DB2), MySQL, EnterpriseDB (Postgres) |
| **Foco de Uso** | Integração com Windows, .NET e ferramentas de BI (Power BI). | Aplicações críticas empresariais, ERPs e sistemas bancários complexos. |

---

## 🏗️ Database First vs. Code First

Ao iniciar um projeto, existe uma escolha estratégica sobre **de onde o banco de dados nasce**:

**Code First (O Código Primeiro)**

* Você escreve as classes em sua linguagem (C#, Java, Python) e o framework **gera o banco automaticamente**.
* **Vantagem:** foco total na lógica do negócio; controle de versão via Migrations.
* **Ideal para:** projetos novos (Greenfield) onde o desenvolvedor tem controle total.

**Database First (O Banco Primeiro)**

* O banco já existe ou é criado via SQL. O framework **mapeia as tabelas** e gera as classes.
* **Vantagem:** usa toda a potência do DBA (índices complexos, triggers) sem depender do framework.
* **Ideal para:** sistemas legados ou equipes com modelagem de dados dedicada.

---

[⬅️ Página Anterior](aula_7_funcoes_agregacao.md) | [🏠 Voltar ao Início](01-introducao-e-conceitos.md)
