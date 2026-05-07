# Instruções para Agentes — agent-skills

Este arquivo define o comportamento esperado de agentes de IA ao trabalhar neste repositório.

## Propósito do Repositório

Este repositório contém **skills** para agentes de desenvolvimento. Uma skill é um pacote de instruções especializadas que guia um agente na execução de tarefas complexas e bem definidas.

## Convenções

### Estrutura de uma Skill

Cada skill deve seguir esta estrutura:

```
.github/skills/<nome-da-skill>/
├── SKILL.md          # Arquivo principal com frontmatter YAML e instruções
└── references/       # (opcional) Documentação de referência adicional
    └── *.md
```

### Formato do `SKILL.md`

Todo `SKILL.md` deve conter um frontmatter YAML válido seguido do corpo em Markdown:

```markdown
---
name: nome-da-skill
description: "Descrição clara do propósito. Use when: <cenários de uso>. DO NOT USE FOR: <cenários fora do escopo>."
---

# Título da Skill

## Instruções
...
```

**Regras do frontmatter:**
- `name` deve corresponder exatamente ao nome da pasta
- `description` deve conter gatilhos de invocação explícitos ("Use when: ...")
- Valores com `:` devem estar entre aspas duplas
- Usar espaços (não tabs) para indentação YAML

### Nomenclatura

- Nomes de pastas de skills: `kebab-case` (ex: `code-review`, `create-pr`)
- Nomes de arquivos: `kebab-case.md`
- Títulos no `SKILL.md`: Português ou Inglês, conforme o público-alvo da skill

## Diretrizes para Criação de Skills

Ao criar ou atualizar uma skill neste repositório:

1. **Verifique se já existe** uma skill similar antes de criar uma nova
2. **Scope correto**: skills são para tarefas específicas e repetíveis; instruções gerais vão em `.instructions.md`
3. **Description é crítica**: o campo `description` é o principal mecanismo de descoberta — inclua palavras-chave de invocação
4. **Não inclua segredos**: nunca adicione tokens, senhas ou credenciais em nenhum arquivo
5. **Mantenha o README atualizado**: adicione a nova skill na seção "Skills Disponíveis" do `README.md`

## O que NÃO fazer

- Não crie skills genéricas que se sobreponham às instruções base do agente
- Não use `applyTo: "**"` em instructions — isso consome contexto desnecessariamente
- Não adicione lógica condicional complexa no frontmatter
- Não duplique conteúdo entre skills — use referências cruzadas quando necessário

## Validação

Antes de fazer commit de uma nova skill, verifique:

- [ ] Frontmatter YAML é válido (sem tabs, aspas em valores com `:`)
- [ ] `name` no frontmatter corresponde ao nome da pasta
- [ ] `description` contém gatilhos de invocação claros
- [ ] A skill foi adicionada ao `README.md`
- [ ] Nenhum dado sensível foi incluído
