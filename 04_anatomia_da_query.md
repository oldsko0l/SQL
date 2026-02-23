# 🔍 Como Criar uma Consulta (SELECT)

Uma consulta SQL não é apenas texto, ela tem uma anatomia:

* **Palavras-chave:** Comandos reservados como `SELECT` e `FROM`.
* **Identificadores:** Os nomes das suas tabelas e colunas.
* **Comentários (`--`):** Notas para você mesmo que o computador ignora.

## 🏗️ Estrutura de uma Busca

```sql
SELECT nome_da_coluna      -- O que eu quero ver?
FROM nome_da_tabela        -- De onde vem?
WHERE condicao             -- Filtro (ex: preco > 100)
ORDER BY coluna;           -- Organização (A-Z ou Z-A)
```

# 🚀 Ferramentas para Turbinar a Busca

| Comando | Função |
| :--- | :--- |
| **DISTINCT** | Remove resultados repetidos da sua consulta. |
| **TOP / LIMIT** | Mostra apenas os primeiros "X" resultados da lista. |
| **Aliases (AS)** | Dá um "apelido" para a coluna, deixando o resultado mais legível. |

---

## 🧠 A Lógica Secreta do SQL

> **Atenção!** Você escreve em uma ordem, mas o computador processa os dados em outra. Entender isso evita muitos erros de lógica:

1.  **FROM**: Primeiro, o computador identifica de onde vêm os dados (a tabela).
2.  **WHERE**: Depois, ele filtra as linhas que não interessam.
3.  **SELECT**: Só agora ele escolhe quais colunas devem ser exibidas.
4.  **ORDER BY**: Por fim, ele organiza a lista final na ordem que você pediu.

---

[⬅️ Página Anterior](link-da-pagina) | [🏠 Voltar ao Início](link-do-inicio)

