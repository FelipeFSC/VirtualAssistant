# tools

Ferramentas e integrações do assistente (servidores MCP, scripts, conexões com Azure DevOps, banco de dados etc.).

Vazia nesta versão. Cada ferramenta nova ganha uma subpasta com um `README.md`
explicando o que faz e como configurar.

## Segredos (senhas, tokens, strings de conexão)

Nunca ficam aqui. Toda ferramenta que precisa de segredo:

1. Lê `config.json`, na raiz do projeto.
2. Pega o caminho do `.env` no campo `envFile`. Ele pode estar em qualquer pasta da máquina.
3. Carrega as variáveis desse `.env`.

Ao criar uma ferramenta que precisa de segredo, adicione a variável, sem valor, em
`.env.example` na raiz, com um comentário dizendo qual ferramenta a usa.
