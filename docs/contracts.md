# Sistema de Contratos

O Elis usa contratos JSON para definir o comportamento de cada agente.

## Estrutura de um Contrato

```json
{
  "agent": "nome_do_agente",
  "model": "haiku|sonnet|opus",
  "skill": "/skill_name",
  "skill_reference": "external-skill-name",
  "role": "Descricao do papel",
  "capabilities": [
    "Lista de capacidades"
  ],
  "input_contract": {
    "required": ["campos_obrigatorios"],
    "optional": ["campos_opcionais"]
  },
  "output_contract": {
    "format": "json|files",
    "schema": { "estrutura_do_output" }
  },
  "quality_gates": {
    "gate_name": true,
    "another_gate": "value"
  },
  "timeout_ms": 60000,
  "retry_on_fail": true,
  "max_retries": 2
}
```

## Campos do Contrato

### Identificacao
- `agent`: Nome unico do agente
- `model`: Modelo Claude a usar (haiku para tasks rapidas, sonnet para complexas)
- `skill`: Skill interno do Claude Code (ex: `/designer`)
- `skill_reference`: Skill externo do SkillsMP

### Capacidades
- `role`: Descricao do papel do agente
- `capabilities`: Lista do que o agente pode fazer

### Contratos de I/O
- `input_contract.required`: Campos que DEVEM ser fornecidos
- `input_contract.optional`: Campos opcionais
- `output_contract.format`: Tipo de saida (json ou files)
- `output_contract.schema`: Estrutura esperada do output

### Quality Gates
Criterios que o output deve passar antes de ser aceito:
- `complete_color_palette`: true = paleta completa
- `min_competitors`: 3 = minimo 3 competidores analisados
- `responsive_at_all_breakpoints`: true = responsivo em 320, 768, 1024, 1440

### Configuracao
- `timeout_ms`: Tempo maximo de execucao
- `retry_on_fail`: Se deve tentar novamente em caso de falha
- `max_retries`: Numero maximo de tentativas

## Exemplo Completo: Designer

```json
{
  "agent": "designer",
  "model": "sonnet",
  "skill": "/designer",
  "role": "Elite UI/Visual Designer",
  "capabilities": [
    "Design system completo",
    "Color theory e paletas",
    "Typography systems",
    "Component specifications",
    "Animation intentions",
    "2026 design trends"
  ],
  "input_contract": {
    "required": ["project_brief"],
    "optional": [
      "reference_url",
      "brand_guidelines",
      "target_emotion",
      "style_direction"
    ]
  },
  "output_contract": {
    "format": "json",
    "schema": {
      "status": "success|partial|failed",
      "confidence": "high|medium|low",
      "design_system": {
        "colors": {
          "primary": "hsl()",
          "secondary": "hsl()",
          "accent": "hsl()",
          "neutrals": ["array"],
          "semantic": {}
        },
        "typography": {
          "font_display": "string",
          "font_body": "string",
          "scale": {},
          "weights": []
        },
        "spacing": {},
        "effects": {},
        "borders": {}
      },
      "visual_hierarchy": {},
      "components": [],
      "animations": {},
      "decorative_elements": {}
    }
  },
  "quality_gates": {
    "complete_color_palette": true,
    "typography_scale_min_sizes": 6,
    "responsive_strategy_defined": true,
    "accessibility_considered": true
  },
  "timeout_ms": 90000,
  "retry_on_fail": true,
  "max_retries": 2
}
```

## Validacao de Contratos

O Elis valida automaticamente:

1. **Pre-execucao:** Input tem todos os campos required?
2. **Pos-execucao:** Output segue o schema?
3. **Quality Gates:** Todos os gates passaram?

Se alguma validacao falhar:
1. Retry com o mesmo agente (se retry_on_fail = true)
2. Apos max_retries, tenta fallback
3. Se nao houver fallback, reporta erro ao usuario

## Customizando Contratos

Voce pode modificar os contratos no arquivo `elis.md`:

1. Abra `~/.claude/commands/elis.md`
2. Encontre o contrato do agente
3. Modifique conforme necessario
4. Salve o arquivo

Exemplo: Aumentar timeout do Builder:
```json
{
  "agent": "builder",
  "timeout_ms": 300000  // 5 minutos em vez de 3
}
```
