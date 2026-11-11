# local

Pasta **pessoal**, com a mesma estrutura de `ai/`. Tudo aqui é ignorado pelo git,
exceto este README.

Use para o que é seu e não deve subir online: suas regras, seu contexto, seus
agentes, comandos, skills e ferramentas.

```
local/
  rules.md        suas regras pessoais
  context.md      seu nome, preferências, forma de trabalhar
  agents/         seus agentes
  commands/       seus comandos
  skills/         suas skills
  tools/          suas ferramentas e integrações
```

Os segredos (senhas, tokens) não ficam necessariamente aqui: o `.env` pode estar em
qualquer pasta da máquina, e o caminho dele fica em `config.json`, na raiz.

## Como a IA usa esta pasta

- **Ordem de leitura:** a IA lê `ai/` e depois `local/`.
- **Itens só em `local/`:** são somados ao projeto (ex.: uma skill pessoal).
- **Mesmo nome nas duas pastas:** vale o de `local/`, só para você. Ex.:
  `local/agents/dev.md` substitui `ai/agents/dev.md` na sua máquina.
- **Regras:** as de `local/rules.md` se somam às de `ai/rules.md`.

As subpastas são criadas pela IA na configuração inicial (`start.md`), porque o git
não guarda pastas vazias.
