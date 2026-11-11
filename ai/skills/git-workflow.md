# Skill: git-workflow

**Quando usar:** ao criar branches, escrever commits, abrir PRs ou revisar o histórico git.

## Branches

- Padrão definido em `ai/context.md` (ex.: `feature/ABC-123-login-sso`).
- Correções urgentes: `hotfix/{ID}-{descricao}`.
- Descrição em minúsculas, com hífens e sem acentos.

## Commits

```
<tipo>(<escopo opcional>): <descrição no imperativo> [<ID>]

<corpo opcional: o porquê, não o como>
```

| Tipo | Quando |
|---|---|
| `feat` | nova funcionalidade |
| `fix` | correção de bug |
| `refactor` | mudança sem alterar comportamento |
| `test` | testes |
| `docs` | documentação |
| `chore` | build, dependências, configuração |

## Pull Requests

- Título: mesmo formato do commit principal.
- Corpo: **Contexto** (link da tarefa), **O que mudou**, **Como testar**, **Riscos**.
- PR pequeno e focado.

## Regras

- Nunca use `push --force` em branches compartilhadas.
- Commit, push e merge só com pedido explícito do usuário.
