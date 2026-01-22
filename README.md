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
║   "Nada sera como antes, amanha"                                             ║
║                                                                               ║
║   Multi-Agent Orchestrator for World-Class One-Page Websites                 ║
║                                                                               ║
╚═══════════════════════════════════════════════════════════════════════════════╝
```

> Em homenagem a **Elis Regina** (1945-1982), a maior cantora do Brasil, conhecida como "Pimentinha" e "A Voz do Brasil". Assim como Elis regia palcos com intensidade e perfeicao, este orquestrador rege agentes de IA para criar obras digitais de classe mundial.

## A Filosofia Elis

Elis Regina nao era apenas uma cantora - ela era uma **regente** de emocoes. Cada performance era uma orquestracao perfeita de voz, banda, arranjo e alma. Ela exigia excelencia de si mesma e de todos ao redor.

**Elis** (o orquestrador) carrega esse espirito:

- **Excelencia sem compromisso** - Cada output deve ser digno de awwwards.com
- **Orquestracao perfeita** - Cada agente entra no momento certo, com o contexto certo
- **Alma no trabalho** - Nao e so codigo, e arte digital
- **Intensidade** - Entrega completa, do discovery ao deploy

> *"Eu nao sei viver sem paixao"* - Elis Regina

## O que e o Elis?

**Elis** e um skill para [Claude Code](https://claude.ai/code) que transforma o Claude em um maestro de uma orquestra de agentes especializados. Assim como Elis Regina regia suas performances com precisao e paixao, este orquestrador coordena 10+ agentes para criar websites one-page de classe mundial.

### Arquitetura - A Orquestra

```
                              ┌─────────────────────┐
                              │       ELIS          │
                              │   A Regente (Opus)  │
                              │                     │
                              │  "Como nossa voz    │
                              │   principal, eu     │
                              │   coordeno tudo"    │
                              └──────────┬──────────┘
                                         │
           ┌─────────────────────────────┼─────────────────────────────┐
           │                             │                             │
    ┌──────┴──────┐               ┌──────┴──────┐               ┌──────┴──────┐
    │   NAIPE 1   │               │   NAIPE 2   │               │   NAIPE 3   │
    │  Discovery  │               │   Design    │               │    Build    │
    │   Cordas    │               │   Sopros    │               │  Percussao  │
    └─────────────┘               └─────────────┘               └─────────────┘
           │                             │                             │
    ┌──────┴──────┐               ┌──────┴──────┐               ┌──────┴──────┐
    │   NAIPE 4   │               │   NAIPE 5   │               │   NAIPE 6   │
    │   Backend   │               │    Deploy   │               │  Business   │
    │   Metais    │               │   Teclados  │               │    Vocal    │
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
# Pipeline completo - a performance inteira
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

Elis vai reger:
1. **Scout** (primeiro violino) - pesquisa o mercado
2. **Designer** (flauta) - extrai o design system
3. **Sintese** - harmoniza tudo em um relatorio

#### Criar design do zero

```bash
/elis design "App de meditacao para profissionais ocupados" --style minimal
```

A performance:
1. **Scout**: Abertura - pesquisa competidores
2. **Designer + UXer**: Dueto - design e validacao em paralelo
3. **Aprovacao**: Pausa dramatica - usuario aprova
4. **Finale**: Entrega do design system

#### Pipeline completo

```bash
/elis full "Landing para startup de IA" --reference https://anthropic.com --stack next
```

Sinfonia completa em 6 movimentos:
```
I. Discovery → II. Design → III. Approval → IV. Build → V. Deploy → VI. Launch
```

## Os Musicos - Agentes Especializados

### Naipe 1: Discovery (Cordas)
| Musico | Instrumento | Funcao |
|--------|-------------|--------|
| Scout | Primeiro Violino | Pesquisa, competidores, viabilidade |
| Analyzer | Segundo Violino | Analise tecnica detalhada |

### Naipe 2: Design (Sopros)
| Musico | Instrumento | Funcao |
|--------|-------------|--------|
| Designer | Flauta | Design system, cores, tipografia |
| UXer | Clarinete | Validacao UX, acessibilidade |
| Animator | Obo | Motion design, animacoes |

### Naipe 3: Build (Percussao)
| Musico | Instrumento | Funcao |
|--------|-------------|--------|
| Builder | Timpano | Implementacao frontend |
| Tester | Caixa | QA, E2E tests |

### Naipe 4: Backend (Metais)
| Musico | Instrumento | Funcao |
|--------|-------------|--------|
| Supabase | Trompete | Database, Auth, Storage |

### Naipe 5: Deploy (Teclados)
| Musico | Instrumento | Funcao |
|--------|-------------|--------|
| Deployer | Piano | Vercel, CI/CD |

### Naipe 6: Business (Vocal)
| Musico | Instrumento | Funcao |
|--------|-------------|--------|
| Stripe | Tenor | Pagamentos, subscriptions |
| Launcher | Soprano | SEO, marketing, lancamento |

## A Partitura - Sistema de Contratos

Cada musico segue uma **partitura** (contrato JSON):

```json
{
  "agent": "designer",
  "model": "sonnet",
  "role": "Elite UI/Visual Designer",
  "input_contract": {
    "required": ["project_brief"],
    "optional": ["reference_url"]
  },
  "output_contract": {
    "format": "json",
    "schema": { "design_system": "..." }
  },
  "quality_gates": {
    "complete_color_palette": true
  }
}
```

## Skills Integrados (Repertorio)

| Skill | Stars | Funcao |
|-------|-------|--------|
| Web Artifacts Builder | 43,959 | React + Tailwind + shadcn/ui |
| Stripe Integration | 25,611 | Pagamentos completos |
| E2E Testing Patterns | 24,887 | Playwright/Cypress |
| Swarm Orchestration | 12,047 | Multi-agent paralelo |
| Supabase Automation | - | Backend completo |
| Vercel Deploy | - | Deploy automatizado |

## Design Standards 2026 (O Som Contemporaneo)

Elis sempre foi a frente do seu tempo. Este orquestrador segue as tendencias mais atuais:

- **Gradient Orbs** - Como as luzes de um palco
- **Bento Grids** - Composicao visual harmonica
- **Expressive Typography** - Headlines que cantam
- **Glass Morphism** - Transparencia e profundidade
- **Micro-interactions** - Cada hover e uma nota

## Estrutura do Projeto

```
elis/
├── elis.md              # A partitura principal
├── README.md            # Este arquivo
├── LICENSE              # MIT License
├── CHANGELOG.md         # Historico de versoes
├── examples/            # Repertorio de exemplos
│   ├── saas-landing.md
│   ├── portfolio.md
│   └── startup.md
└── docs/                # Manual do maestro
    ├── contracts.md
    ├── agents.md
    └── customization.md
```

## Contribuindo

Contribuicoes sao bem-vindas! Junte-se a orquestra:

1. Fork o repositorio
2. Crie uma branch (`git checkout -b feature/nova-feature`)
3. Commit suas mudancas (`git commit -m 'Add nova feature'`)
4. Push para a branch (`git push origin feature/nova-feature`)
5. Abra um Pull Request

## Roadmap

- [ ] Mais frameworks (Vue, Svelte, SolidJS)
- [ ] Integracao com Figma
- [ ] Agente de copywriting
- [ ] Agente de analytics
- [ ] Dashboard de projetos
- [ ] Suporte a PWA

## Licenca

MIT License - veja [LICENSE](LICENSE) para detalhes.

## Creditos

Criado por [@pheeliipe91](https://github.com/pheeliipe91)

Em homenagem a **Elis Regina Carvalho Costa** (1945-1982)
- "Aguas de Marco"
- "Como Nossos Pais"
- "O Bebado e a Equilibrista"
- E tantas outras obras-primas

Inspirado por:
- [Anthropic Skills](https://github.com/anthropics/skills)
- [SkillsMP](https://skillsmp.com)

---

> *"Eu sei que a minha voz pode ser pequena diante de tudo que esta acontecendo no mundo. Mas enquanto eu puder cantar, eu vou cantar."* - Elis Regina

**Elis** - Regendo a orquestra de agentes para criar obras digitais de classe mundial.
