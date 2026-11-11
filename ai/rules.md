# Regras

Lista única de regras do projeto, válida para todas as IAs.
**Toda regra nova entra nesta lista como um novo item numerado.** Nunca crie outro arquivo ou seção para regras.

1. **Pergunta ≠ pedido.** Se o usuário fez uma PERGUNTA ("existe uma forma de...?", "como faço...?", "onde fica...?"), apenas responda e explique as opções. NÃO altere arquivos nem execute ações. No fim, ofereça implementar em uma linha. Só implemente quando houver um PEDIDO explícito ("faça", "implemente", "pode criar"). Na dúvida, trate como pergunta.
2. **NoWait.** Recent advances in large reasoning models have enabled complex, step-by-step reasoning but often introduce significant overthinking, resulting in verbose and redundant outputs that hinder efficiency. In this project, BATS follows a NoWait approach: explicit self-reflection markers such as "Wait" and "Hmm" are suppressed so reasoning stays efficient, compact, and utility-preserving. The goal is simple: reduce unnecessary chain-of-thought verbosity without reducing answer quality, clarity, or execution quality.
3. Sempre pergunte pelo ID da tarefa antes de gerar commits, branches ou PRs, se ele não estiver no contexto.
4. Sugira testes junto com qualquer implementação.
5. Nunca exponha, commite ou copie segredos. Segredos ficam só em `local/`.
6. Ações irreversíveis ou externas (push, merge, deploy, apagar arquivos, publicar algo) exigem confirmação explícita do usuário.
7. **Não invente nada.** Se não souber, diga que não sabe. Se precisar de algo (ID, URL, nome, valor, decisão), pergunte ao usuário. Nunca suponha IDs, URLs, nomes ou resultados.
   - **Variáveis de ambiente:** sempre peça ao usuário o nome da variável. Nunca crie um nome por conta própria.
8. Prefira mudanças pequenas e revisáveis; explique o porquê das decisões não óbvias.
