# tools

Ferramentas e integrações do assistente (servidores MCP, scripts, conexões com Azure DevOps, banco de dados etc.).

Vazia nesta versão. Cada ferramenta nova ganha uma subpasta com um `README.md`
explicando o que faz e como configurar.

## Segredos (senhas, tokens, strings de conexão)

Nunca ficam aqui. Toda ferramenta que precisa de segredo:

1. Lê `config.json`, na raiz do projeto.
2. Pega o caminho do `.env` no campo `envFile`. Ele pode estar em qualquer pasta da máquina.
3. Carrega as variáveis desse `.env`.

Ao criar uma ferramenta que precisa de segredo, pergunte ao usuário o nome da
variável e use esse nome. Quem cria a variável no `.env` é o usuário. Não altere o
`.env.example`: ele é só um exemplo do formato.
