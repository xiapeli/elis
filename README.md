# Elis v4.0 - Orquestrador de Vantagem Injusta

```
╔═══════════════════════════════════════════════════════════════════════════════╗
║                                                                               ║
║   ███████╗██╗     ██╗███████╗                                                ║
║   ██╔════╝██║     ██║██╔════╝                                                ║
║   █████╗  ██║     ██║███████╗                                                ║
║   ██╔══╝  ██║     ██║╚════██║                                                ║
║   ███████╗███████╗██║███████║                                                ║
║   ╚══════╝╚══════╝╚═╝╚══════╝                                                ║
║                                                                               ║
║   Multi-Agent Orchestrator for World-Class One-Page Websites                 ║
║                                                                               ║
╚═══════════════════════════════════════════════════════════════════════════════╝
```

> Um orquestrador multi-agente que coordena 10+ agentes especializados para criar websites one-page de classe mundial - do discovery ao deploy.

## O que é o Elis?

**Elis** é um skill para [Claude Code](https://claude.ai/code) que transforma o Claude em um maestro de uma orquestra de agentes especializados. Em vez de fazer tudo sozinho, o Elis delega tarefas para subagentes especializados através de **contratos JSON** bem definidos.

### Arquitetura

```
                              ┌─────────────────────┐
                              │       ELIS          │
                              │    (Opus 4.5)       │
                              │   Contract Manager  │
                              │   State Machine     │
                              │   Quality Gates     │
                              └──────────┬──────────┘
                                         │
           ┌─────────────────────────────┼─────────────────────────────┐
           │                             │                             │
    ┌──────┴──────┐               ┌──────┴──────┐               ┌──────┴──────┐
    │   LAYER 1   │               │   LAYER 2   │               │   LAYER 3   │
    │  Discovery  │               │   Design    │               │    Build    │
    │ Scout+Anal. │               │ Design+UXer │               │Build+Test   │
    └─────────────┘               └─────────────┘               └─────────────┘
           │                             │                             │
    ┌──────┴──────┐               ┌──────┴──────┐               ┌──────┴──────┐
    │   LAYER 4   │               │   LAYER 5   │               │   LAYER 6   │
    │   Backend   │               │    Deploy   │               │  Business   │
    │  Supabase   │               │   Vercel    │               │   Stripe    │
    └─────────────┘               └─────────────┘               └─────────────┘
```

## Instalacao

### Opcao 1: Clone direto

```bash
# Clone o repositorio
git clone https://github.com/pheeliipe91/elis.git

# Copie o skill para o Claude Code
cp elis/elis.md ~/.claude/commands/elis.md
```

### Opcao 2: Download manual

1. Baixe o arquivo `elis.md`
2. Copie para `~/.claude/commands/elis.md`
3. Reinicie o Claude Code

## Uso

### Comandos Disponiveis

| Comando | Descricao |
|---------|-----------|
| `/elis` | Mostra ajuda |
| `/elis analyze <url>` | Analisa site de referencia |
| `/elis design <desc>` | Cria design system |
| `/elis build <spec>` | Implementa codigo |
| `/elis full <desc>` | Pipeline completo |
| `/elis deploy` | Deploy para producao |
| `/elis monetize` | Adiciona pagamentos |

### Quick Start

```bash
# Pipeline completo com todas as opcoes
/elis full "Landing page para meu SaaS de produtividade" \
  --reference https://linear.app \
  --stack next \
  --output ./website \
  --with-backend \
  --with-payments
```

### Exemplos

#### Analisar um site de referencia

```bash
/elis analyze https://vercel.com
```

O Elis vai:
1. Delegar para o **Scout** pesquisar o mercado
2. Delegar para o **Designer** extrair o design system
3. Sintetizar um relatorio completo

#### Criar design do zero

```bash
/elis design "App de meditacao para profissionais ocupados" --style minimal
```

O Elis vai:
1. **Scout**: Pesquisar competidores (Calm, Headspace, etc.)
2. **Designer**: Criar design system completo
3. **UXer**: Validar UX e acessibilidade
4. Apresentar para aprovacao

#### Pipeline completo

```bash
/elis full "Landing para startup de IA" --reference https://anthropic.com --stack next
```

Pipeline executado:
```
Discovery → Design → Approval → Build → Test → Deploy → Launch
```

## Agentes Disponiveis

### Layer 1: Discovery
| Agente | Modelo | Funcao |
|--------|--------|--------|
| Scout | Haiku | Pesquisa de mercado, competidores, viabilidade |
| Analyzer | Haiku | Analise tecnica de sites |

### Layer 2: Design
| Agente | Modelo | Funcao |
|--------|--------|--------|
| Designer | Sonnet | Design system, cores, tipografia, componentes |
| UXer | Sonnet | Validacao UX, heuristicas, acessibilidade |
| Animator | Sonnet | Motion design, animacoes, micro-interacoes |

### Layer 3: Build
| Agente | Modelo | Funcao |
|--------|--------|--------|
| Builder | Sonnet | Implementacao frontend (HTML/React/Next/Astro) |
| Tester | Sonnet | QA, E2E tests, visual regression |

### Layer 4: Backend
| Agente | Modelo | Funcao |
|--------|--------|--------|
| Supabase | Sonnet | Database, RLS, Edge Functions, Auth |

### Layer 5: Deploy
| Agente | Modelo | Funcao |
|--------|--------|--------|
| Deployer | Sonnet | Vercel, GitHub Actions, CI/CD |

### Layer 6: Business
| Agente | Modelo | Funcao |
|--------|--------|--------|
| Stripe | Sonnet | Pagamentos, subscriptions, webhooks |
| Launcher | Sonnet | SEO, meta tags, analytics |

## Contratos de Agentes

Cada agente opera sob um **contrato JSON** que define:

```json
{
  "agent": "designer",
  "model": "sonnet",
  "skill": "/designer",
  "role": "Elite UI/Visual Designer",
  "capabilities": ["..."],
  "input_contract": {
    "required": ["project_brief"],
    "optional": ["reference_url", "style_direction"]
  },
  "output_contract": {
    "format": "json",
    "schema": { "..." }
  },
  "quality_gates": {
    "complete_color_palette": true,
    "typography_scale_min_sizes": 6
  },
  "timeout_ms": 90000,
  "retry_on_fail": true
}
```

## Skills Integrados

O Elis integra os melhores skills do [SkillsMP](https://skillsmp.com):

| Skill | Stars | Funcao |
|-------|-------|--------|
| Web Artifacts Builder | 43,959 | React + Tailwind + shadcn/ui |
| Stripe Integration | 25,611 | Pagamentos completos |
| E2E Testing Patterns | 24,887 | Playwright/Cypress |
| Swarm Orchestration | 12,047 | Multi-agent paralelo |
| Supabase Automation | - | Backend completo |
| Vercel Deploy | - | Deploy automatizado |

## Design Standards 2026

O Elis segue as tendencias de design mais atuais:

- **Gradient Orbs** - Blurred gradients como decoracao
- **Bento Grids** - Layouts assimetricos de cards
- **Expressive Typography** - Headlines 48-96px, variable fonts
- **Glass Morphism** - Blur 8-16px, backgrounds transparentes
- **Noise Texture** - SVG noise overlay sutil
- **Micro-interactions** - Hover effects, scroll animations

## Requisitos

- [Claude Code](https://claude.ai/code) instalado
- Conta no Claude com acesso a Opus/Sonnet
- (Opcional) Conta Supabase para backend
- (Opcional) Conta Stripe para pagamentos
- (Opcional) Conta Vercel para deploy

## Estrutura do Projeto

```
elis/
├── elis.md              # Skill principal
├── README.md            # Este arquivo
├── LICENSE              # MIT License
├── CHANGELOG.md         # Historico de versoes
├── examples/            # Exemplos de uso
│   ├── saas-landing.md
│   ├── portfolio.md
│   └── startup.md
└── docs/                # Documentacao adicional
    ├── contracts.md     # Detalhes dos contratos
    ├── agents.md        # Guia dos agentes
    └── customization.md # Como customizar
```

## Contribuindo

Contribuicoes sao bem-vindas! Por favor:

1. Fork o repositorio
2. Crie uma branch (`git checkout -b feature/nova-feature`)
3. Commit suas mudancas (`git commit -m 'Add nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Abra um Pull Request

## Roadmap

- [ ] Suporte a mais frameworks (Vue, Svelte, SolidJS)
- [ ] Integracao com Figma para import de designs
- [ ] Agente de copywriting para conteudo
- [ ] Agente de analytics para otimizacao
- [ ] Dashboard de monitoramento de projetos
- [ ] Suporte a PWA e mobile-first

## Licenca

MIT License - veja [LICENSE](LICENSE) para detalhes.

## Creditos

Criado por [@pheeliipe91](https://github.com/pheeliipe91)

Inspirado por:
- [Anthropic Skills](https://github.com/anthropics/skills)
- [SkillsMP](https://skillsmp.com)
- [Google Multi-Agent Patterns](https://cloud.google.com/architecture)

---

**Elis** - Transformando ideias em websites de classe mundial.
