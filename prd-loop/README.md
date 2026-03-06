# ELIS PRD Loop System

> Integrado com Ralph Pattern para execucao autonoma de PRDs

## Visao Geral

O sistema de PRD Loop permite que a ELIS trabalhe de forma autonoma em user stories, executando iteracoes ate completar todas as tarefas definidas em um PRD.

## Como Funciona

```
+-------------------------------------------------------------+
|                      ELIS PRD LOOP                           |
+-------------------------------------------------------------+
|                                                              |
|  1. Criar prd.json com user stories                         |
|     -> Define automacoes/features estruturadas              |
|                                                              |
|  2. ./elis-loop.sh                                          |
|     -> Executa loop autonomo:                               |
|         +-------------------------------------------+        |
|         |  Para cada iteracao:                      |        |
|         |  1. Le prd-loop/prd.json                  |        |
|         |  2. Le prd-loop/progress.txt              |        |
|         |  3. Pega story com maior prioridade       |        |
|         |     onde passes: false                    |        |
|         |  4. Implementa a automacao                |        |
|         |  5. Valida (lint, tests)                  |        |
|         |  6. Se passou: commit + update prd.json   |        |
|         |  7. Append progress.txt                   |        |
|         |  8. Se todas passes: true -> COMPLETE     |        |
|         +-------------------------------------------+        |
|                                                              |
|  3. ./elis-loop.sh 5                                        |
|     -> Limita a 5 iteracoes                                 |
|                                                              |
+-------------------------------------------------------------+
```

## Estrutura de Arquivos

```
prd-loop/
+-- README.md           # Este arquivo
+-- prompt.md           # Instrucoes para cada iteracao
+-- elis-loop.sh        # Script bash para execucao autonoma
+-- prd.json.example    # Exemplo de formato PRD
+-- prd.json            # PRD ativo (criado pelo usuario)
+-- progress.txt        # Log de progresso (append-only)
+-- archive/            # PRDs anteriores arquivados
    +-- YYYY-MM-DD-feature-name/
        +-- prd.json
        +-- progress.txt
```

## Formato do PRD (prd.json)

```json
{
  "project": "ELIS",
  "branchName": "elis/feature-name",
  "description": "Descricao da automacao",
  "userStories": [
    {
      "id": "US-001",
      "title": "Titulo da story",
      "description": "As a [user], I want [feature] so that [benefit]",
      "acceptanceCriteria": [
        "Criterio verificavel 1",
        "Criterio verificavel 2",
        "Tests passam"
      ],
      "priority": 1,
      "passes": false,
      "notes": ""
    }
  ]
}
```

## Regras de Tamanho de Stories

**Cada story deve ser completavel em UMA iteracao (um context window).**

### Stories corretas (pequenas):
- Adicionar novo trigger de automacao
- Implementar action especifica
- Adicionar validacao de workflow
- Criar handler de evento

### Stories muito grandes (dividir):
- "Criar sistema de automacao completo" -> dividir em 5-6 stories
- "Integrar com 10 servicos" -> dividir por servico
- "Reescrever engine" -> dividir por componente

## Ordem de Dependencias

Stories devem ser ordenadas por dependencia:

1. Infraestrutura/Config
2. Triggers/Events
3. Actions/Handlers
4. Workflows/Orchestration
5. Monitoring/Logging

## Criterios de Aceitacao

Cada story DEVE incluir criterios verificaveis:

**Bons criterios:**
- "Trigger dispara em menos de 100ms"
- "Action executa com retry em caso de falha"
- "Tests passam"

**Criterios ruins (evitar):**
- "Funciona rapido"
- "Boa automacao"
- "Confiavel"

## Progress Log

O `progress.txt` acumula conhecimento entre iteracoes:

```markdown
## Codebase Patterns
- Usar async para todas automacoes
- Implementar retry com backoff exponencial
- Logar inicio e fim de cada workflow

## [Data/Hora] - US-001
- O que foi implementado
- Arquivos alterados
- Learnings para futuras iteracoes:
  - Padroes descobertos
  - Gotchas encontrados
---
```

## Stop Conditions

O loop para quando:
1. Todas stories tem `passes: true`
2. Atingiu maximo de iteracoes
3. Erro critico detectado

## Filosofia

> "Each iteration: fresh context, one story, quality checks."
> - Ralph Pattern
