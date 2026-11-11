# plans

Base de conhecimento sobre os sistemas da empresa, organizada por sistema e por issue.
A IA usa esta pasta para entender o contexto de um sistema antes de trabalhar nele.

## Estrutura

```
plans/
  <nome-do-sistema>/
    <numero-da-issue>/
      <arquivos de plano>
```

- **`<nome-do-sistema>`:** um sistema da empresa.
- **`<numero-da-issue>`:** a issue/tarefa trabalhada nesse sistema.
- **Arquivos de plano:** planos, análises, decisões e anotações daquela issue.

A mesma estrutura existe em `local/plans/`, para planos pessoais que não sobem para o git.

## Como a IA usa

- **Ao trabalhar em um sistema:** leia `ai/plans/<sistema>/` e `local/plans/<sistema>/`
  para entender o histórico e as decisões já tomadas.
- **Ao trabalhar em uma issue:** leia também a pasta da issue, se existir.
- **Ao criar um plano:** salve em `plans/<sistema>/<issue>/`. Se não souber o nome
  do sistema ou o número da issue, pergunte ao usuário. Pergunte também se o plano
  é do projeto (`ai/plans/`) ou pessoal (`local/plans/`).
