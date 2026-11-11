# criar-pr

**O que faz:** gera título e corpo de Pull Request a partir da branch atual.
**Agente:** `dev`
**Argumentos:** branch base (padrão `main`)

## Passos

1. Compare a branch atual com a base usando `git log` e `git diff`.
2. Extraia o ID da tarefa do nome da branch; se não houver, pergunte.
3. Use o formato de PR da skill `git-workflow`.
4. Só crie o PR de fato se o usuário pedir.
