# Guia dos Agentes

O Elis coordena 10+ agentes especializados organizados em 6 layers.

## Layer 1: Discovery

### Scout
**Modelo:** Haiku (rapido e economico)
**Skill:** `/scout`

**Capacidades:**
- WebSearch para pesquisa de mercado
- Analise de competidores
- Identificacao de tendencias
- Avaliacao de viabilidade (1-10)
- Recomendacoes de stack tecnica

**Output:**
```json
{
  "status": "success",
  "confidence": "high",
  "report": {
    "summary": "...",
    "competitors": [...],
    "market_trends": [...],
    "tech_recommendations": {...},
    "viability_score": 8,
    "go_no_go": "go",
    "risks": [...],
    "opportunities": [...]
  }
}
```

---

## Layer 2: Design

### Designer
**Modelo:** Sonnet
**Skill:** `/designer`

**Capacidades:**
- Design system completo
- Color theory e paletas (HSL)
- Typography systems
- Component specifications
- Animation intentions
- 2026 design trends

**Output:** Design system JSON com cores, tipografia, spacing, efeitos, componentes.

### UXer
**Modelo:** Sonnet
**Skill:** `/uxer`

**Capacidades:**
- User journey analysis (AIDA)
- Heuristic evaluation (Nielsen, 1-10)
- Friction identification
- Accessibility audit (WCAG)
- Conversion optimization

**Output:** Analise completa com recommendations classificadas (critical, important, nice_to_have).

### Animator
**Modelo:** Sonnet
**Skill Reference:** web-artifacts-builder

**Capacidades:**
- Framer Motion patterns
- CSS animations
- Scroll-triggered effects
- Micro-interactions
- Page transitions
- Stagger animations

---

## Layer 3: Build

### Builder
**Modelo:** Sonnet
**Skill:** `/builder`

**Capacidades:**
- HTML/CSS/JS production code
- React/Next.js/Astro
- Tailwind CSS
- shadcn/ui components
- Framer Motion animations
- Responsive implementation
- Performance optimization

**Stacks suportados:**
- `html` - HTML + CSS + JS vanilla
- `next` - Next.js 14+ App Router
- `astro` - Astro com islands

### Tester
**Modelo:** Sonnet
**Skill:** `/tester`
**Skill Reference:** e2e-testing-patterns

**Capacidades:**
- Playwright tests
- Visual regression
- Accessibility testing (axe-core)
- Performance testing
- Cross-browser testing

---

## Layer 4: Backend

### Supabase
**Modelo:** Sonnet
**Skill Reference:** supabase-automation

**Capacidades:**
- Database schema design
- RLS policies
- Edge Functions
- Auth setup (email, OAuth)
- Realtime subscriptions
- Storage configuration
- TypeScript types generation

---

## Layer 5: Deploy

### Deployer
**Modelo:** Sonnet
**Skill Reference:** vercel-deploy

**Capacidades:**
- Vercel configuration
- GitHub Actions
- Environment variables
- Domain setup
- Edge functions
- Preview deployments

---

## Layer 6: Business

### Stripe
**Modelo:** Sonnet
**Skill Reference:** stripe-integration

**Capacidades:**
- Checkout Sessions
- Payment Intents
- Subscriptions
- Webhooks
- Customer Portal
- Stripe Connect (marketplaces)

### Launcher
**Modelo:** Sonnet
**Skill:** `/launcher`

**Capacidades:**
- SEO optimization
- Meta tags
- Open Graph
- Sitemap generation
- Analytics setup
- Launch checklist

---

## Como os Agentes se Comunicam

O Elis usa um sistema de **contratos** para garantir comunicacao clara:

1. **Input Contract:** Define o que o agente precisa receber
2. **Output Contract:** Define o formato do retorno
3. **Quality Gates:** Criterios que o output deve passar

Exemplo de fluxo:
```
Scout Output → Designer Input
Designer Output → UXer Input (validacao)
Designer + UXer → Builder Input
Builder Output → Tester Input
```

## Execucao Paralela

Alguns agentes podem rodar em paralelo:
- Designer + UXer (fase de design)
- Builder + Tester (em partes diferentes)

O Elis identifica automaticamente quando paralelizar.
