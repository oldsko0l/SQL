# 🛠️ As Famílias de Comandos SQL

Os comandos são divididos em "famílias" dependendo do que você quer fazer:

## 1. DDL (Criação e Estrutura)
Mexe no "esqueleto" do banco.
- `CREATE`: Cria o banco ou a tabela do zero.
- `ALTER`: Muda algo que já existe (ex: adiciona uma coluna).
- `DROP`: Apaga a tabela ou banco para sempre (Cuidado!).

## 2. DML (Mexer nos Dados)
Mexe no conteúdo que está dentro das tabelas.
- `INSERT`: Coloca dados novos lá dentro.
- `UPDATE`: Altera um dado que já está lá (ex: mudar o preço).
- `DELETE`: Apaga uma linha ou registro.
- **⚠️ Regra de Ouro:** Nunca use `UPDATE` ou `DELETE` sem a cláusula `WHERE`, ou você apagará/alterará o banco inteiro!

## 3. DQL (Consulta)
O comando mais usado de todos.
- `SELECT`: Serve para visualizar e filtrar os dados.

---
[Página Anterior](02_estruturas_e_tipos.md) | [Próxima Aula: Consultas](04_anatomia_da_query.md)
