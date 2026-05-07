# Guia de Contribuição

Obrigado pelo interesse em contribuir com o **agent-skills**! Este guia explica como participar do projeto de forma organizada.

## Código de Conduta

Ao contribuir, você concorda em seguir nosso [Código de Conduta](CODE_OF_CONDUCT.md). Trate todos com respeito.

## Como Contribuir

### Reportar Problemas

Abra uma [issue](https://github.com/mpr-org/agent-skills/issues/new/choose) usando o template adequado:

- **Bug report** — algo em uma skill existente não funciona como esperado
- **Feature request** — sugestão de nova skill ou melhoria em uma existente

### Propor ou Criar uma Skill

1. **Verifique se já existe** uma skill similar no repositório antes de criar uma nova.
2. **Abra uma issue** descrevendo a skill proposta (escopo, casos de uso, o que não cobre).
3. Aguarde feedback antes de começar a implementar — evita trabalho redobrado.

### Fluxo de Trabalho

```bash
# 1. Faça fork do repositório e clone localmente
git clone https://github.com/<seu-usuario>/agent-skills.git
cd agent-skills

# 2. Crie uma branch a partir de main
git checkout -b feat/nome-da-skill

# 3. Faça suas alterações seguindo as convenções do projeto

# 4. Commit usando Conventional Commits
git commit -m "feat(nome-da-skill): add skill description"

# 5. Publique a branch
git push origin feat/nome-da-skill

# 6. Abra um Pull Request pelo GitHub
```

### Padrões de Commit

Use [Conventional Commits](https://www.conventionalcommits.org/):

```
<tipo>(<escopo>): <descrição curta no imperativo>
```

Tipos: `feat`, `fix`, `docs`, `style`, `refactor`, `chore`

Exemplos:
- `feat(open-pr): add draft PR support`
- `fix(language-standard): correct PT-BR rule for technical terms`
- `docs: update contributing guide`

### Estrutura de uma Skill

Cada skill deve seguir a estrutura definida no [AGENTS.md](AGENTS.md):

```
.github/skills/<nome-da-skill>/
├── SKILL.md          # Obrigatório — frontmatter YAML + instruções
└── templates/        # Opcional — templates e ativos auxiliares
```

### Checklist antes de abrir o PR

- [ ] Frontmatter YAML válido (sem tabs, aspas em valores com `:`)
- [ ] `name` no frontmatter corresponde ao nome da pasta
- [ ] `description` contém gatilhos de invocação claros (`Use when: ...`)
- [ ] A skill foi adicionada à seção "Skills Disponíveis" do `README.md`
- [ ] Nenhum dado sensível incluído (tokens, senhas, chaves)
- [ ] Título do PR segue Conventional Commits

## Dúvidas

Abra uma [discussão](https://github.com/mpr-org/agent-skills/discussions) ou uma issue com a label `question`.
