# Changelog

Todas as mudancas notaveis neste projeto serao documentadas neste arquivo.

O formato e baseado em [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
e este projeto adere ao [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [4.0.0] - 2026-01-22

### Adicionado
- Arquitetura completa de orquestracao com contratos JSON
- 10+ agentes especializados (Scout, Designer, UXer, Builder, Animator, Tester, Supabase, Stripe, Deployer, Launcher)
- Sistema de 6 layers (Discovery, Design, Build, Backend, Deploy, Business)
- Swarm orchestration para execucao paralela de agentes
- Quality gates em todas as fases do pipeline
- Integracao com Supabase (database, auth, storage, edge functions)
- Integracao com Stripe (checkout, subscriptions, webhooks)
- Integracao com Vercel (deploy, CI/CD, preview)
- State machine para tracking de progresso (.elis/state.json)
- Protocolos de delegacao com validacao de input/output
- Error handling robusto com retry e fallback
- Design Standards 2026 (gradient orbs, bento grids, glass morphism)
- Animation Standards com acessibilidade (reduced-motion)

### Skills Integrados
- web-artifacts-builder (Anthropic) - 43,959 stars
- stripe-integration (wshobson) - 25,611 stars
- e2e-testing-patterns (wshobson) - 24,887 stars
- swarm-orchestration (ruvnet) - 12,047 stars
- supabase-automation
- vercel-deploy
- github-actions-writer

### Comandos
- `/elis` - Help
- `/elis analyze <url>` - Analise de referencia
- `/elis design <desc>` - Design system
- `/elis build <spec>` - Implementacao
- `/elis full <desc>` - Pipeline completo
- `/elis deploy` - Deploy
- `/elis monetize` - Pagamentos

### Opcoes do Full Pipeline
- `--reference <url>` - Site de referencia
- `--stack <html|next|astro>` - Tech stack
- `--output <path>` - Diretorio de saida
- `--with-backend` - Adiciona Supabase
- `--with-payments` - Adiciona Stripe

## [3.0.0] - 2026-01-15

### Adicionado
- Multi-agent orchestration baseado em Google's 2026 patterns
- Parallel processing (Designer + UXer)
- Quality gates entre fases
- Design approval antes de build
- Suporte a 2026 design trends

## [2.0.0] - 2025-12-01

### Adicionado
- Separacao de agentes (Designer, UXer, Builder)
- Pipeline sequencial
- Suporte a Next.js e Astro

## [1.0.0] - 2025-10-15

### Adicionado
- Versao inicial
- Analise de sites de referencia
- Geracao de HTML/CSS
