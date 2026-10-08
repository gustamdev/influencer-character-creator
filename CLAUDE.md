# CLAUDE.md

Repositório com duas skills de agente para gerar prompts de imagem de personagens live-action.

## Estrutura

- `skills/live-action-character/SKILL.md`: cria o personagem e entrega o prompt de geração de imagem.
- `skills/live-action-character-sheet/SKILL.md`: gera o prompt do character sheet (prancha de continuidade) do personagem.
- `assets/`: logo do README.
- `.claude-plugin/`: manifesto do plugin e do marketplace.

## Regras

- Cada skill vive em `skills/<nome>/SKILL.md`, e o `name` do frontmatter é igual ao nome da pasta.
- Ao adicionar ou remover uma skill, atualize a tabela do `README.md` e o `AGENTS.md`.
- O README é curto e em inglês. Mantenha assim.
