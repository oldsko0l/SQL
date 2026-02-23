# 🏗️ Como o Banco de Dados se Organiza

Os bancos de dados não são todos iguais. [cite_start]Eles podem ser de vários tipos[cite: 19]:
- [cite_start]**Relacional:** O mais comum, usa tabelas (ex: MySQL, SQL Server)[cite: 22, 23].
- [cite_start]**Não-Relacional:** Usa documentos ou grafos (ex: MongoDB, Redis)[cite: 24, 25, 26, 27, 28, 29].

## [cite_start]A Hierarquia do Banco Relacional [cite: 32, 33]
1. [cite_start]**Servidor:** É a "casa" principal[cite: 34].
2. [cite_start]**Banco de Dados:** É o "armário" (ex: Banco de Vendas)[cite: 35].
3. [cite_start]**Esquema:** São as "gavetas" organizadas[cite: 36].
4. [cite_start]**Tabela:** É onde a informação está de verdade[cite: 37].

## [cite_start]Anatomia de uma Tabela [cite: 38]
- [cite_start]**Colunas:** Definem o que é o dado (Nome, Preço, Data)[cite: 39].
- [cite_start]**Linhas:** É o registro de cada item individual[cite: 40].
- [cite_start]**Célula:** O encontro de uma linha com uma coluna[cite: 41].
- [cite_start]**Chave Primária:** O "CPF" único de cada linha para não confundir os dados[cite: 42].

## [cite_start]Tipos de Dados (O que cabe na célula?) [cite: 44, 45]
- [cite_start]**Números:** `INT` (inteiros) e `DECIMAL` (preços/notas)[cite: 46, 47, 48].
- [cite_start]**Texto:** `VARCHAR` (textos que variam de tamanho)[cite: 49, 51].
- [cite_start]**Data/Hora:** `DATE` (ano-mês-dia) e `TIME` (hora-minuto-segundo)[cite: 52, 53, 54].

---
[Página Anterior](01_conceitos_basicos.md) | [Próxima Aula: Comandos](03_comandos_sql.md)
