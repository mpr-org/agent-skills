---
name: open-pr
description: "Abre um Pull Request no GitHub seguindo convenções semânticas e preenchendo um template padronizado. Use when: abrir PR, criar pull request, submeter código para revisão, publicar branch, criar draft PR, finalizar feature, abrir PR com template, PR semântico, conventional commits no PR."
argument-hint: "Opcionalmente informe título, branch base, ou se deve ser criado como draft"
---

# Abertura de Pull Request Padronizado

Cria Pull Requests seguindo convenções semânticas (Conventional Commits) e preenchendo obrigatoriamente o template padronizado do repositório.

## Quando Usar

- O usuário quer abrir um PR para a branch atual ou para uma branch específica
- O usuário finalizou uma feature, fix ou refactor e quer submeter para revisão
- O usuário quer criar um draft PR para compartilhar trabalho em progresso
- O usuário pede para "abrir PR", "criar pull request", "submeter para revisão", "abrir PR semântico"

## Convenção de Título (Conventional Commits)

O título do PR **deve** seguir o formato:

```
<tipo>(<escopo opcional>): <descrição curta no imperativo>
```

### Tipos aceitos

| Tipo | Quando usar |
|------|-------------|
| `feat` | Nova funcionalidade |
| `fix` | Correção de bug |
| `docs` | Apenas documentação |
| `style` | Formatação, sem mudança de lógica |
| `refactor` | Refatoração sem nova feature ou fix |
| `perf` | Melhoria de performance |
| `test` | Adição ou correção de testes |
| `chore` | Tarefas de build, CI, configuração |
| `revert` | Reverte um commit anterior |

**Exemplos:**
- `feat(auth): add JWT refresh token support`
- `fix(api): handle null response on user fetch`
- `chore(ci): update Node.js version to 20`
- `docs: add contributing guide`

## Procedimento

### 1. Coletar Informações

Antes de abrir o PR, determine:

- **Branch de origem**: Se não especificada, use o contexto do workspace ou git para obter a branch atual. Passe apenas o nome da branch, sem o formato `owner:branch`.
- **Branch base**: Se não especificada, omita e deixe o repositório usar a branch padrão.
- **Título semântico**: Derive do nome da branch, commits recentes ou da descrição do usuário, seguindo o padrão Conventional Commits acima.
- **Corpo**: Preencha completamente o template em `templates/pull-request-template.md`. Nunca abra o PR com o template vazio ou parcialmente preenchido.
- **Draft**: Verifique se o trabalho está pronto para revisão. Use draft por padrão quando o usuário indicar que ainda está em progresso.

### 2. Verificar Estado do Repositório

1. **Mudanças não commitadas**: Verifique se há alterações staged ou unstaged.
   - Se houver, pergunte ao usuário se deseja commitá-las antes de abrir o PR.
   - Se sim, ajude a escrever a mensagem de commit seguindo Conventional Commits e execute `git add -A && git commit -m "<mensagem>"`.
   - Se não, prossiga apenas se já houver commits à frente da base.

2. **Commits não publicados**: Verifique se a branch local está à frente do remoto.
   - Se sim, execute `git push` ou `git push --set-upstream origin <branch>` se ainda não houver upstream configurado.

3. **Branch no remoto**: A branch de origem deve existir no remoto antes de criar o PR.

### 3. Preencher o Template

Leia o arquivo `templates/pull-request-template.md` e preencha **todas** as seções:

- **Descrição**: Explique o que foi feito e por quê — não apenas o quê.
- **Tipo de mudança**: Marque o(s) tipo(s) aplicável(eis) com `[x]`.
- **Issues relacionadas**: Referencie com `Closes #N` ou `Relates to #N`.
- **Como testar**: Descreva os passos para validar as mudanças.
- **Checklist**: Marque cada item conforme aplicável antes de submeter.

> Nunca submeta o PR com seções em branco ou com o placeholder do template sem preenchimento.

### 4. Abrir o PR

Use a ferramenta `github-pull-request_create_pull_request` com os parâmetros coletados:

```
github-pull-request_create_pull_request({
  title: '<tipo>(<escopo>): <descrição imperativa>',
  head: '<nome-da-branch>',
  body: '<template preenchido>',
  base: '<branch-base>',       // opcional; omitir para usar a padrão do repo
  draft: false,                // true para trabalho em progresso
})
```

### 5. Confirmar Resultado

Após a criação bem-sucedida:

- Informe o número e a URL do PR como link markdown.
- Mencione a branch base para a qual o PR foi direcionado.
- Se for draft, lembre o usuário de marcá-lo como pronto quando apropriado.
