# Live-action character skills

Duas skills de agente para criar personagens virais no estilo cartoon/caricatura traduzidos para pessoas reais, com realismo fotográfico, e gerar a prancha de continuidade deles.

**Compatível com:** Claude Code · Higgsfield · Nano Banana · GPT Image · Midjourney · Flux

## Skills

| Skill | O que faz |
|---|---|
| `/live-action-character` | Cria o personagem e entrega um único prompt de geração de imagem. |
| `/live-action-character-sheet` | Gera o prompt do character sheet: vistas de frente, 3/4, perfil e costas, mais closes de rosto, olhos, mãos, prop e figurino. |

## Instalação

Como plugin do Claude Code:

```bash
/plugin marketplace add gustamdev/live-action-character-skills
/plugin install live-action-character-skills@live-action-character-skills
```

Ou copiando as pastas para `~/.claude/skills/`:

```bash
cp -R skills/* ~/.claude/skills/
```

## Uso

1. Peça um personagem com `/live-action-character` e gere a imagem com o prompt.
2. Rode `/live-action-character-sheet` para gerar o character sheet e manter a consistência.
