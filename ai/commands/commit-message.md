# commit-message

**O que faz:** gera a mensagem de commit para as mudanças atuais.
**Agente:** `dev`
**Argumentos:** ID da tarefa (opcional)

## Passos

1. Veja as mudanças com `git diff --staged`. Se não houver nada staged, use `git diff`.
2. Se o ID da tarefa não foi informado nem está no contexto, pergunte.
3. Siga a skill `git-workflow`.
4. Se as mudanças misturam assuntos diferentes, sugira dividir em mais de um commit.
5. Apenas proponha a mensagem. Só execute `git commit` se o usuário pedir.
