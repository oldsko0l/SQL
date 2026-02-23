# 🔍 Como Criar uma Consulta (SELECT)

[cite_start]Uma consulta SQL não é apenas texto, ela tem uma anatomia[cite: 153]:
- [cite_start]**Palavras-chave:** Comandos reservados como SELECT e FROM[cite: 156, 157].
- [cite_start]**Identificadores:** Os nomes das suas tabelas e colunas[cite: 159].
- [cite_start]**Comentários (`--`):** Notas para você mesmo que o computador ignora[cite: 155].

## [cite_start]Estrutura de uma Busca [cite: 162]
```sql
SELECT nome_da_coluna      -- O que eu quero ver?
FROM nome_da_tabela       -- De onde vem?
WHERE condicao            -- Filtro (ex: preco > 100)
ORDER BY coluna;          -- Organização (A-Z ou Z-A)
