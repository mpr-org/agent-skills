# AGENTS.md

## Contexto do repositório

Este é o repositório **agent-skills** — um repositório público de _skills_ (habilidades) para uso com agentes de desenvolvimento de software baseados em IA.

## O que são skills?

Skills são conjuntos de instruções e contexto que podem ser carregados por um agente para executar tarefas específicas de forma padronizada. Cada skill vive em seu próprio diretório dentro de `skills/` e contém um arquivo `SKILL.md` descrevendo:

- O objetivo da skill
- Pré-requisitos
- Passos detalhados que o agente deve seguir

## Estrutura do repositório

```
agent-skills/
├── README.md        # Visão geral do projeto
├── AGENTS.md        # Este arquivo — contexto para agentes
└── skills/
    └── <nome-da-skill>/
        └── SKILL.md
```

## Diretrizes para agentes

- Ao trabalhar neste repositório, sempre verifique o `SKILL.md` da skill relevante para obter instruções detalhadas.
- Novas skills devem ser adicionadas em `skills/<nome-da-skill>/SKILL.md`.
- Mantenha as instruções claras, objetivas e reproduzíveis.
- Não altere skills existentes sem contexto explícito da tarefa.
