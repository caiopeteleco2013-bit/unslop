# unslop (opencode)

A fork/adaptação do [heydamir/unslop](https://github.com/heydamir/unslop) para o [OpenCode](https://opencode.ai).

unslop é uma skill que transforma interfaces com "cara de IA" (vibecoded UI — gradientes roxos, glows, rótulos com emoji, copy gritante, espaçamento aleatório) em uma interface projetada com caráter próprio. Ela audita a tela, define uma direção a partir do produto e corrige espaçamento, cor, ícones, copy, tipografia, layout, detalhes, visuais e movimento — nessa ordem.

Criado por Damir Sokolovsky ([@heydamir](https://x.com/heydamir)). Licenciado sob [CC BY 4.0](LICENSE).

## Instalação no OpenCode

O OpenCode carrega skills automaticamente de `.opencode/skills/` dentro do projeto ou de `~/.config/opencode/skills/` globalmente.

### Por projeto (recomendado)

Clone este repo dentro do seu projeto (ou copie apenas a pasta da skill):

```bash
# a partir da raiz do seu projeto
git clone https://github.com/SEU_USUARIO/unslop.git
```

Isso coloca a skill em `seu-projeto/.opencode/skills/unslop/SKILL.md`. O OpenCode descobre e anuncia a skill automaticamente.

### Global (disponível em todo projeto)

```bash
mkdir -p ~/.config/opencode/skills
git clone https://github.com/SEU_USUARIO/unslop.git ~/.config/opencode/skills/unslop
```

## Como usar

Quando quiser redesenhar uma tela, peça ao agente:

> "unslop esta tela para ela parar de parecer gerada por IA"

Ou carregue a skill diretamente:

```
skill({ name: "unslop" })
```

Depois passe o que deseja (arquivo, pasta, URL de um site ao vivo ou descrição em palavras próprias). A skill:

1. Audita a tela listando todos os sinais de slop com onde estão.
2. Propõe uma direção (produto, caráter, mundo, momentos, assinatura) antes de editar anything — você pode ajustar.
3. Aplica nove passes, em ordem: espaçamento, cor, ícones, copy, tipografia, layout, detalhes, visuais, movimento.
4. Gera um relatório com o que mudou em cada pass.

## Conteúdo da skill

```
.opencode/skills/unslop/
├── SKILL.md          # instruções (9 passes + direção + checklist + story video)
├── references/       # signs, tokens, visuals, effects, refs + imagens de referência
└── scripts/          # snapshot.mjs e story.mjs (Playwright + ffmpeg para vídeo da história)
```

A pasta `agents/openai.yaml` do original (específica do Codex) foi intencionalmente removida, pois não é usada pelo OpenCode.

## Crédito

Mantenha o crédito a Damir Sokolovsky ([@heydamir](https://x.com/heydamir)) e o link de volta para o repositório original, como exige a licença CC BY 4.0.
