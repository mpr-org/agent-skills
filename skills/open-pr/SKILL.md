# SKILL.md — open-pr

## Descrição

A skill **open-pr** instrui o agente a criar e abrir uma _pull request_ (PR) em um repositório GitHub de forma padronizada, incluindo título, descrição e contexto adequados.

## Pré-requisitos

- Acesso ao repositório alvo com permissão para criar branches e pull requests.
- As alterações desejadas já devem estar implementadas localmente ou o agente deve receber instruções claras sobre quais mudanças fazer.
- A branch base (geralmente `main` ou `master`) deve estar atualizada.

## O que o agente deve fazer

1. **Garantir que as alterações estão prontas**: Verificar que todos os arquivos modificados estão corretos e os testes (se existirem) passam.
2. **Criar uma branch descritiva**: Usar um nome de branch que reflita o objetivo das mudanças (ex.: `feat/minha-feature`, `fix/corrige-bug`).
3. **Fazer commit das alterações**: Escrever mensagens de commit claras e objetivas seguindo as convenções do repositório.
4. **Abrir a pull request**:
   - **Título**: Conciso e descritivo, indicando o que foi feito.
   - **Descrição**: Incluir contexto sobre o problema resolvido, as mudanças realizadas e qualquer informação relevante para o revisor.
   - **Labels/Reviewers**: Adicionar quando aplicável.
5. **Confirmar**: Verificar que a PR foi criada com sucesso e reportar a URL ao usuário.

## Exemplo de fluxo

```bash
# 1. Criar e mudar para nova branch
git checkout -b feat/minha-feature

# 2. Adicionar e commitar alterações
git add .
git commit -m "feat: adiciona minha feature"

# 3. Enviar branch para o remoto
git push origin feat/minha-feature

# 4. Abrir a PR via GitHub CLI
gh pr create \
  --title "feat: adiciona minha feature" \
  --body "## Contexto\nDescrição do que foi feito e por quê." \
  --base main
```

## Notas

- Sempre use o idioma do repositório na descrição da PR.
- Certifique-se de que o CI passa antes de solicitar revisão.
- Prefira PRs pequenas e focadas em um único objetivo.
