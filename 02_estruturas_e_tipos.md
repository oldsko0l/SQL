# 🏗️ Como o Banco de Dados se Organiza

Os bancos de dados não são todos iguais. Eles podem ser de vários tipos:

- **Relacional:** O mais comum, usa tabelas (ex: MySQL, SQL Server).
- **Não-Relacional:** Usa documentos ou grafos (ex: MongoDB, Redis).

## A Hierarquia do Banco Relacional
1. **Servidor:** É a "casa" principal.
2. **Banco de Dados:** É o "armário" (ex: Banco de Vendas).
3. **Esquema:** São as "gavetas" organizadas.
4. **Tabela:** É onde a informação está de verdade.

## Anatomia de uma Tabela
- **Colunas:** Definem o que é o dado (Nome, Preço, Data).
- **Linhas:** É o registro de cada item individual.
- **Célula:** O encontro de uma linha com uma coluna.
- **Chave Primária:** O "CPF" único de cada linha para não confundir os dados.

## Tipos de Dados (O que cabe na célula?)
- **Números:** `INT` (inteiros) e `DECIMAL` (preços/notas).
- **Texto:** `VARCHAR` (textos que variam de tamanho).
- **Data/Hora:** `DATE` (ano-mês-dia) e `TIME` (hora-minuto-segundo).

---
[Página Anterior](01_conceitos_basicos.md) | [Próxima Aula: Comandos](03_comandos_sql.md)
