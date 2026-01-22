# Customizacao do Elis

## Modificando o Skill Principal

O arquivo principal esta em:
```
~/.claude/commands/elis.md
```

### Alterando Design Standards

Encontre a secao `## DESIGN STANDARDS 2026` e modifique:

```yaml
gradient_orbs:
  colors: "sua_cor_primaria at 30% opacity"
  blur: "100px"

expressive_typography:
  headlines: "64-120px"  # headlines maiores
  pairing: "Playfair Display + Inter"  # suas fontes
```

### Adicionando Novos Agentes

1. Crie o contrato JSON:
```json
{
  "agent": "copywriter",
  "model": "sonnet",
  "role": "Expert Copywriter",
  "capabilities": [
    "Headlines que convertem",
    "Copy de vendas",
    "Microcopy de UX"
  ],
  "input_contract": {
    "required": ["product_info", "target_audience"],
    "optional": ["tone", "word_count"]
  },
  "output_contract": {
    "format": "json",
    "schema": {
      "headlines": [],
      "body_copy": {},
      "ctas": []
    }
  }
}
```

2. Adicione o template de invocacao:
```javascript
Task(
  subagent_type: "general-purpose",
  model: "sonnet",
  description: "Copywriter: [task]",
  prompt: `...`
)
```

3. Integre ao pipeline onde necessario

### Modificando Quality Gates

Cada agente tem quality gates que podem ser ajustados:

```json
"quality_gates": {
  "min_competitors": 5,           // mais competidores
  "min_confidence": "high",       // so aceita alta confianca
  "all_sections_implemented": true
}
```

### Alterando Timeouts

Se seus projetos sao maiores, aumente os timeouts:

```json
{
  "agent": "builder",
  "timeout_ms": 300000,  // 5 minutos
  "max_retries": 5
}
```

## Criando Pipelines Customizados

### Pipeline so de Design

```bash
/elis design "Projeto X" --style bold
```

Modifique o pipeline para pular fases:

```markdown
### `/elis design <description>`

**Pipeline Customizado:**
Scout ──► Designer ──► Approval (skip UXer)
```

### Pipeline sem Backend

Remova o `--with-backend` ou crie um comando especifico:

```bash
/elis frontend "Projeto Y" --stack next
```

## Integrando Novos Skills do SkillsMP

1. Encontre o skill no [SkillsMP](https://skillsmp.com)
2. Adicione a referencia no contrato:

```json
{
  "agent": "novo_agente",
  "skill_reference": "autor/skill-name"
}
```

3. Use no template de invocacao:
```javascript
prompt: `
Use skill reference: autor/skill-name
...
`
```

## Configurando Estado Persistente

O Elis salva estado em `.elis/state.json`:

```json
{
  "version": "4.0",
  "project": {
    "name": "MeuProjeto",
    "description": "..."
  },
  "phase": {
    "current": "build",
    "completed": ["discovery", "design"]
  },
  "contracts": {
    "scout": { "output": {...} },
    "designer": { "output": {...} }
  }
}
```

Para retomar um projeto:
```bash
cd meu-projeto
/elis run build  # continua de onde parou
```

## Criando Presets

Crie arquivos `.elis-preset.json` para configuracoes recorrentes:

```json
{
  "preset": "saas",
  "defaults": {
    "stack": "next",
    "with_backend": true,
    "with_payments": true,
    "style": "professional"
  }
}
```

Use com:
```bash
/elis full "Meu SaaS" --preset saas
```

## Troubleshooting

### Agente falha repetidamente
1. Aumente `max_retries`
2. Aumente `timeout_ms`
3. Simplifique o input
4. Use modelo mais capaz (sonnet → opus)

### Output incompleto
1. Verifique quality gates
2. Adicione mais contexto no input
3. Divida a tarefa em partes menores

### Erros de parsing JSON
1. O agente pode estar retornando texto extra
2. Adicione instrucao: "RETORNE APENAS O JSON"
3. Use parsing mais tolerante
