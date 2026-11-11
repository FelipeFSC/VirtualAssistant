# start

Arquivo inicial do projeto. **Toda IA que abrir este projeto pela primeira vez lê
este arquivo e segue os passos abaixo.**

O usuário só precisa dizer à IA: `Leia o start.md`.

---

## 1. Mapa do projeto

Existem duas pastas com a **mesma estrutura**:

- `ai/`: o que é do projeto e do time. Versionada.
- `local/`: o que é pessoal do usuário. Não versionada, exceto o `README.md`.

Na raiz ficam também:

- `config.json`: configuração da máquina do usuário, fora do git. O campo `envFile`
  aponta para o `.env`, que pode estar em qualquer pasta. O modelo é `config.example.json`.
- `.env.example`: modelo das variáveis de segredo (sem valores).

| O quê | Projeto | Pessoal | Quando ler |
|---|---|---|---|
| Regras | `ai/rules.md` | `local/rules.md` | sempre, no início de toda sessão |
| Contexto | `ai/context.md` | `local/context.md` | sempre, no início de toda sessão |
| Agentes | `ai/agents/<nome>.md` | `local/agents/<nome>.md` | quando o usuário pedir um papel ("aja como dev", "@qa") |
| Comandos | `ai/commands/<nome>.md` | `local/commands/<nome>.md` | quando o usuário pedir um comando ("/commit-message") |
| Skills | `ai/skills/<nome>.md` | `local/skills/<nome>.md` | quando a tarefa combinar com a skill, ou quando um agente indicar |
| Ferramentas | `ai/tools/` | `local/tools/` | quando precisar de uma integração |
| Segredos | — | o `.env` indicado em `config.json` → `envFile` | **nunca leia nem exiba**: só as ferramentas usam |

**Como combinar as duas pastas:**
- Leia `ai/` primeiro e depois `local/`.
- O que existe só em `local/` soma-se ao projeto.
- Quando houver o mesmo nome nas duas, vale o de `local/`.
- As regras de `local/rules.md` se somam às de `ai/rules.md`.

Os arquivos que começam com `_` (ex.: `_template.md`) são modelos. Não são agentes,
comandos nem skills ativos.

## 2. Configuração inicial

Faça isto **uma única vez por IA**.

1. Pergunte ao usuário: **"Qual IA estamos usando?"**
   - Claude Code
   - Cursor
   - GitHub Copilot
   - Outra (pergunte qual)
2. Crie o arquivo de entrada da IA escolhida. É o arquivo que essa IA lê
   sozinha em toda sessão.

   | IA | Arquivo a criar |
   |---|---|
   | Claude Code | `.claude/CLAUDE.md` |
   | Cursor | `.cursor/rules/projeto.mdc` (com o cabeçalho abaixo) |
   | GitHub Copilot | `.github/copilot-instructions.md` |
   | Outra | o arquivo de instruções nativo dessa IA (se não souber, `AGENTS.md` na raiz) |

   Cabeçalho obrigatório só no Cursor (no início do `.mdc`):

   ```
   ---
   description: Instruções do projeto
   alwaysApply: true
   ---
   ```

3. O conteúdo é **sempre o mesmo**, para qualquer IA:

   ```markdown
   # Instruções do projeto

   Este projeto é configurado pelas pastas `ai/` (projeto) e `local/` (pessoal),
   que têm a mesma estrutura. O mapa completo está em `start.md`.

   No início de toda sessão, antes de responder:
   1. Leia `ai/rules.md` e `local/rules.md` (se existir) e siga todas as regras.
   2. Leia `ai/context.md` e `local/context.md` (se existir).

   Durante a sessão, procure primeiro em `local/` e depois em `ai/`:
   - Agente pedido → `agents/<nome>.md`
   - Comando pedido → `commands/<nome>.md`
   - Skill relevante → `skills/<nome>.md`

   Nunca leia, exiba ou commite o `.env` (caminho em `config.json` → `envFile`).
   Não crie regras, agentes, comandos ou skills fora de `ai/` ou `local/`.
   ```

4. Se o arquivo já existir, **não sobrescreva**: mostre ao usuário o que existe e pergunte.
5. Prepare a pasta `local/`, criando só o que faltar e sem sobrescrever nada:
   - as subpastas `agents/`, `commands/`, `skills/` e `tools/`;
   - `rules.md` com o título `# Regras pessoais` e uma lista vazia;
   - `context.md` com o título `# Contexto pessoal`. Pergunte o nome do usuário e anote.
6. Configure o `.env`:
   - Se `config.json` não existir, copie de `config.example.json`.
   - Pergunte ao usuário o caminho do `.env` dele e grave em `envFile`, com barras
     normais (ex.: `C:/Users/nome/segredos/.env`).
   - Se o arquivo não existir nesse caminho, ofereça criá-lo copiando `.env.example`.
     Quem preenche os valores é o usuário; você não preenche.
7. Confirme ao usuário o que foi criado e leia as regras e o contexto.

## 3. Onde adicionar coisas novas

Quando o usuário pedir algo novo, pergunte se é **do projeto** (`ai/`, vai para o
repositório) ou **pessoal** (`local/`, fica só na máquina dele). Se ele já disser
"pessoal" ou "local", use `local/` direto.

| Pedido | Arquivo (em `ai/` ou `local/`) |
|---|---|
| Nova regra | novo item numerado em `rules.md`. **Nunca** em outro arquivo. |
| Novo agente | `agents/<nome>.md`, copiando `ai/agents/_template.md` |
| Novo comando | `commands/<nome>.md`, copiando `ai/commands/_template.md` |
| Nova skill | `skills/<nome>.md`, copiando `ai/skills/_template.md` |
| Contexto | `context.md` |
| Nova ferramenta | subpasta em `tools/`, com `README.md` |
| Novo segredo (senha, token) | pergunte ao usuário o nome da variável (nunca invente). Adicione-a em `.env.example` na raiz, sem valor e com um comentário dizendo para que serve. O usuário preenche no `.env` dele |

Os arquivos de entrada das IAs (`.claude/`, `.cursor/`, `.github/copilot-instructions.md`)
só apontam para `ai/` e `local/`. Nunca coloque regras neles.
