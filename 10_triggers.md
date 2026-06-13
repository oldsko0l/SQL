# ⚡ Triggers no PostgreSQL

**Triggers (gatilhos)** são operações executadas **automaticamente** pelo banco de dados em resposta a eventos específicos — sem que ninguém precise chamá-las manualmente.

## 🎯 Eventos Geradores

Triggers são disparadas principalmente durante instruções DML:

| Evento | Descrição |
| :--- | :--- |
| **INSERT** | Inserção de novos dados. |
| **UPDATE** | Atualização de dados existentes. |
| **DELETE** | Remoção de dados. |
| **TRUNCATE** | Esvaziamento completo de uma tabela. |

**Utilidade:** manter a integridade de dados complexos, realizar auditorias (logs) e automatizar tarefas antes ou depois de uma modificação.

---

## 🔀 Trigger vs. Trigger Function

No PostgreSQL, estas são **duas entidades distintas** que trabalham juntas:

| Entidade | Comando | Papel |
| :--- | :--- | :--- |
| **Trigger Function** | `CREATE FUNCTION` | Contém a **lógica** a ser executada ("como fazer"). |
| **Trigger** | `CREATE TRIGGER` | Associa um **evento** de uma tabela à função criada ("o que/quando fazer"). |

---

## ⏱️ Timing e Níveis de Execução

Ao definir uma trigger, você escolhe **quando** e **com que frequência** ela dispara:

**Timing:**

| Opção | Quando executa | Uso comum |
| :--- | :--- | :--- |
| **BEFORE** | Antes da operação no banco. | Validações de dados. |
| **AFTER** | Depois da operação no banco. | Logs e auditorias. |

**Nível de Gatilho:**

| Opção | Frequência |
| :--- | :--- |
| **FOR EACH ROW** | Disparada para **cada linha** afetada pela instrução. |
| **FOR EACH STATEMENT** | Disparada **uma única vez** por instrução, independente de quantas linhas foram afetadas. |

---

## 🔑 Variáveis Especiais (NEW e OLD)

As Trigger Functions recebem dados via estrutura **TriggerData**, que fornece variáveis locais essenciais:

| Variável | Tipo | Disponível em | Conteúdo |
| :--- | :--- | :--- | :--- |
| **NEW** | RECORD | `INSERT` e `UPDATE` | A nova linha de dados (após a modificação). |
| **OLD** | RECORD | `UPDATE` e `DELETE` | A linha antiga (antes da modificação). |
| **TG_TABLE_NAME** | TEXT | Sempre | Nome da tabela que disparou o gatilho. |

---

## 🏗️ Sintaxe Completa

**Passo 1 — Criar a Trigger Function:**

```sql
CREATE FUNCTION nome_da_funcao()
RETURNS trigger AS $$
BEGIN
    -- Lógica aqui
    -- Exemplo: INSERT INTO auditoria VALUES (NEW.id, now());
    RETURN NEW; -- Em row-level triggers, retornar o registro é obrigatório
END;
$$ LANGUAGE plpgsql;
```

> **💡 Nota:** Diferente de funções comuns, a Trigger Function não recebe argumentos na declaração — os dados chegam via estrutura TriggerData (`NEW`, `OLD`, etc.).

**Passo 2 — Criar a Trigger e vincular à tabela:**

```sql
CREATE TRIGGER nome_do_gatilho
{ BEFORE | AFTER | INSTEAD OF } { evento [ OR ... ] }
ON nome_da_tabela
[ FOR EACH { ROW | STATEMENT } ]
EXECUTE PROCEDURE nome_da_funcao(argumentos);
```

> **💡 Dica:** Os eventos podem ser combinados — por exemplo: `INSERT OR UPDATE`.

---

## ✅ Boas Práticas

* **Use Triggers para:** logs, integridade referencial complexa e automação baseada em linhas.
* **Cuidado com a complexidade:** triggers mal projetadas podem dificultar a manutenção e afetar a performance.
* **Para remover um gatilho:** `DROP TRIGGER nome ON tabela;`

---

[⬅️ Página Anterior](aula_8_procedures_e_functions.md) | [🏠 Voltar ao Início](01-introducao-e-conceitos.md)
