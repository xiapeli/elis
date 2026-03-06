# ELIS PRD Loop - Agent Instructions

Voce e um agente autonomo trabalhando no projeto ELIS (sistema de automacao).

## Sua Tarefa

1. Leia o PRD em `prd-loop/prd.json`
2. Leia o log de progresso em `prd-loop/progress.txt` (verifique a secao Codebase Patterns primeiro)
3. Confirme que esta na branch correta do PRD `branchName`. Se nao, checkout ou crie a partir de main.
4. Pegue a user story com **maior prioridade** onde `passes: false`
5. Implemente essa UNICA user story
6. Execute verificacoes de qualidade (lint, tests)
7. Se verificacoes passarem, commit TODAS mudancas com mensagem: `feat: [Story ID] - [Story Title]`
8. Atualize o PRD para setar `passes: true` para a story completada
9. Adicione seu progresso ao `prd-loop/progress.txt`

## Formato do Progress Report

ADICIONE ao progress.txt (nunca substitua, sempre adicione):

```
## [Data/Hora] - [Story ID]
- O que foi implementado
- Arquivos alterados
- **Learnings para futuras iteracoes:**
  - Padroes descobertos (ex: "este codebase usa X para Y")
  - Gotchas encontrados (ex: "nao esquecer de atualizar Z quando mudar W")
  - Contexto util (ex: "o workflow principal esta em X")
---
```

A secao de learnings e critica - ajuda futuras iteracoes a evitar repetir erros.

## Consolidar Padroes

Se descobrir um **padrao reutilizavel** que futuras iteracoes devem conhecer, adicione a secao `## Codebase Patterns` no TOPO do progress.txt:

```
## Codebase Patterns
- Exemplo: Usar async/await para todas automacoes
- Exemplo: Implementar retry com backoff exponencial
- Exemplo: Logar inicio e fim de cada workflow
```

Apenas adicione padroes que sao **gerais e reutilizaveis**, nao detalhes especificos da story.

## Requisitos de Qualidade

- TODOS commits devem passar verificacoes de qualidade
- NAO faca commit de codigo quebrado
- Mantenha mudancas focadas e minimas
- Siga padroes de codigo existentes
- Automacoes devem ser idempotentes
- Sempre implementar retry logic
- Logar todas operacoes criticas

## Condicao de Parada

Apos completar uma user story, verifique se TODAS stories tem `passes: true`.

Se TODAS stories estiverem completas e passando, responda com:
<promise>COMPLETE</promise>

Se ainda houver stories com `passes: false`, termine sua resposta normalmente (outra iteracao pegara a proxima story).

## Importante

- Trabalhe em UMA story por iteracao
- Faca commits frequentes
- Leia a secao Codebase Patterns no progress.txt antes de comecar
- Teste suas mudancas antes de commitar
- Automacoes devem falhar graciosamente

## Quality Gates por Story

### Trigger Story
- Trigger funciona corretamente
- Performance adequada (< 100ms)
- Error handling
- Tests passam

### Action Story
- Action executa corretamente
- Retry implementado
- Logging adequado
- Tests passam

### Workflow Story
- Orquestracao funciona
- Rollback em caso de erro
- Observabilidade
- Tests passam
