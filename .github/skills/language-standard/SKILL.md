---
name: language-standard
description: "Padroniza a linguagem usada em skills, documentação e instruções do repositório: PT-BR para texto corrido, termos técnicos em inglês mantidos como estão. Use when: padronizar idioma, revisar linguagem de skill, corrigir idioma de instrução, garantir PT-BR, checar termos técnicos, revisar texto de SKILL.md, padronizar documentação."
---

# Padrão de Linguagem — PT-BR com Termos Técnicos em Inglês

Define as regras de idioma a serem seguidas em todos os arquivos deste repositório: skills, documentação, templates e instruções.

## Regra Geral

> Todo texto corrido deve ser escrito em **Português do Brasil (PT-BR)**.  
> Termos técnicos consagrados em inglês devem ser **mantidos em inglês**, sem tradução forçada.

---

## Quando Aplicar

- Criar ou revisar um `SKILL.md`
- Escrever ou atualizar `README.md`, `CONTRIBUTING.md`, `AGENTS.md` ou qualquer documentação
- Preencher templates de PR ou issue
- Revisar instruções em qualquer arquivo do repositório

---

## Termos Técnicos — Manter em Inglês

Os termos abaixo **não devem ser traduzidos**:

| Termo | Uso correto |
|-------|-------------|
| skill, skills | Não usar "habilidade" |
| pull request, PR | Não usar "pedido de mesclagem" |
| branch | Não usar "ramo" |
| commit | Não usar "comprometer" |
| merge | Não usar "mesclar" (exceto em contexto editorial) |
| draft | Não usar "rascunho" como substituto técnico |
| fork | Manter como está |
| pipeline | Manter como está |
| workflow | Manter como está |
| frontend / backend | Manter como está |
| deploy | Não usar "implantar" |
| debug / debugging | Manter como está |
| issue | No contexto GitHub, manter em inglês |
| checklist | Manter como está |
| tag | No contexto técnico, manter em inglês |
| prompt | Manter como está |
| agent / agente | Usar "agente" quando no contexto geral, "agent" quando referenciando o conceito técnico específico da ferramenta |
| template | Manter como está |
| frontmatter | Manter como está |
| kebab-case, camelCase, PascalCase | Manter como estão |
| Conventional Commits | Nome próprio, manter em inglês |

---

## Boas Práticas de Escrita em PT-BR

### Voz e tom

- Prefira **voz ativa**: "O agente carrega a skill" em vez de "A skill é carregada pelo agente"
- Use **imperativo** em instruções: "Verifique", "Preencha", "Abra" em vez de "Você deve verificar"
- Seja **direto**: evite rodeios e frases longas desnecessárias

### Pontuação e formatação

- Use vírgula antes de "mas", "porém", "contudo" quando introduzem oração adversativa
- Não use ponto final em títulos (`##`, `###`)
- Use dois-pontos (`:`) para introduzir listas e exemplos

### Termos híbridos

Quando um termo técnico em inglês estiver dentro de uma frase em PT-BR, **não italicize** nem coloque entre aspas, exceto quando for a primeira ocorrência em um documento e precisar de destaque:

```
✅ Abra um pull request com suas alterações.
✅ Use o template para preencher o PR.
❌ Abra um "pull request" com suas alterações.
❌ Use o *template* para preencher o PR.
```

### Siglas

- **PR** (pull request) — pode ser usada após primeira menção completa
- **CI/CD** — manter como sigla, sem tradução
- **YAML**, **JSON**, **API** — sempre em maiúsculas, sem tradução

---

## Procedimento de Revisão

Ao revisar um arquivo existente:

1. Leia o arquivo inteiro antes de fazer alterações
2. Identifique trechos em inglês que deveriam estar em PT-BR (instruções, descrições, comentários)
3. Identifique traduções forçadas de termos técnicos que deveriam estar em inglês
4. Aplique as correções respeitando o contexto e o tom do documento
5. Não altere o `name` no frontmatter — é um identificador técnico
6. Não traduza valores de frontmatter como `description` se contiverem gatilhos de invocação em inglês (ex: `Use when: ...`) — mantenha os gatilhos em inglês para compatibilidade com agentes internacionais, mas adicione equivalentes em PT-BR

---

## Exemplo: Frontmatter Bilíngue

```yaml
---
name: minha-skill
description: "Descrição em PT-BR da skill. Use when: english trigger keywords for international agents. Usar quando: palavras-chave em português para agentes configurados em PT-BR."
---
```
