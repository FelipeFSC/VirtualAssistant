# revisar-codigo

**O que faz:** revisa o código selecionado, um arquivo ou o diff atual.
**Agente:** `dev`
**Argumentos:** arquivo ou escopo (opcional; sem argumento, revisa a seleção ou o `git diff`)

## Passos

Organize a revisão em:

1. **Bugs e riscos:** o que pode quebrar, com o cenário concreto.
2. **Segurança:** entradas não validadas, segredos, permissões.
3. **Padrões do time:** desvios do `ai/context.md` e das skills.
4. **Testes:** o que falta cobrir.
5. **Sugestões:** melhorias opcionais, marcadas como tal.

Cite arquivo e linha em cada ponto. Não aplique mudanças sem o usuário pedir.
