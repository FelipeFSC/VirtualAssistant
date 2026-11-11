# VirtualAssistant

Estrutura base de um assistente virtual que funciona em qualquer IA (Claude Code,
Cursor, GitHub Copilot ou outra). Regras, agentes, comandos e skills ficam num
lugar só, a pasta `ai/`, e servem para todas as IAs.

## Como começar

1. Abra o projeto na sua IA.
2. Diga:

   ```
   Leia o start.md
   ```

3. A IA pergunta qual IA você está usando e cria o arquivo de entrada dela
   (`.claude/`, `.cursor/` etc.). Daí em diante, ela lê o projeto sozinha em toda sessão.
4. Preencha `ai/context.md` com os dados do time e do projeto.

Repita o passo 2 em cada IA nova que você usar no projeto.

## Estrutura

```
start.md            arquivo inicial: mapa do projeto e configuração da IA
ai/
  rules.md          todas as regras (lista única)
  context.md        assistente, time, projeto, stack e convenções
  agents/           um arquivo por papel (dev, qa, tech-lead, po, sre)
  commands/         um arquivo por comando (commit-message, criar-pr, revisar-codigo)
  skills/           conhecimento sob demanda (git-workflow)
  tools/            integrações (vazio nesta versão)
  plans/            conhecimento dos sistemas: <sistema>/<issue>/<arquivos de plano>
local/              mesma estrutura de ai/, só que pessoal e fora do git
config.example.json modelo da configuração da máquina
config.json         sua configuração (fora do git): "envFile" = caminho do seu .env
.env.example        modelo de segredos (Azure DevOps, banco de dados...)
```

Seu `.env` com senhas e tokens pode ficar em qualquer pasta da sua máquina:
basta colocar o caminho em `config.json`, no campo `envFile`, usando barras normais
(`C:/Users/voce/segredos/.env`).

A `local/` serve para o que você não quer subir online: suas regras, contexto,
agentes, comandos, skills, ferramentas e segredos. Quando o nome é o mesmo nas
duas pastas, vale o de `local/`. Veja [local/README.md](local/README.md).

Cada pasta de `ai/` tem um `_template.md` para criar itens novos.

## Usando no dia a dia

- **Agente:** "aja como dev", "@qa, gere cenários para..."
- **Comando:** "/commit-message ABC-123", "rode o comando criar-pr"
- **Nova regra:** peça à IA; ela adiciona um item em `ai/rules.md`

## Para IAs

Leia `start.md`.
