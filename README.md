# agent-skills

Repositório público de **skills** para uso em conjunto com agentes de desenvolvimento baseados em IA (GitHub Copilot, Claude, etc.).

## O que são Skills?

Skills são pacotes de conhecimento especializado que ensinam agentes a executar tarefas complexas e repetíveis. Cada skill é composta por um arquivo `SKILL.md` com instruções detalhadas e, opcionalmente, templates, scripts e outros ativos necessários para a execução da tarefa.

## Estrutura do Repositório

```
agent-skills/
├── README.md
├── AGENTS.md                    # Instruções gerais para agentes neste repositório
└── .github/
    └── skills/
        └── <nome-da-skill>/
            ├── SKILL.md         # Instruções da skill
            └── ...              # Ativos opcionais (templates, scripts, etc.)
```

## Como Usar

As skills deste repositório podem ser referenciadas por agentes de desenvolvimento que suportam o formato de skills do VS Code Copilot Chat. Ao identificar uma tarefa que se enquadra no domínio de uma skill, o agente carrega automaticamente as instruções do `SKILL.md` correspondente.

Para invocar uma skill manualmente em um chat com o Copilot, use `/nome-da-skill` ou descreva a tarefa de forma que o agente identifique a skill adequada.

## Contribuindo

1. Crie uma pasta em `.github/skills/<nome-da-skill>/`
2. Adicione um `SKILL.md` com as instruções no formato adequado (frontmatter YAML + corpo em Markdown)
3. Inclua ativos auxiliares se necessário
4. Atualize este README com a descrição da nova skill

## Skills Disponíveis

| Skill | Descrição |
|-------|-----------|
| [`open-pr`](.github/skills/open-pr/SKILL.md) | Abre Pull Requests seguindo convenções semânticas (Conventional Commits) e preenchendo um template padronizado com descrição, tipo de mudança, issues relacionadas, instruções de teste e checklist. |
| [`language-standard`](.github/skills/language-standard/SKILL.md) | Padroniza a linguagem de skills e documentação: PT-BR para texto corrido, termos técnicos em inglês mantidos como estão. Inclui guia de termos, boas práticas de escrita e procedimento de revisão. |

