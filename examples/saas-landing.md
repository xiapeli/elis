# Exemplo: Landing Page para SaaS

## Comando

```bash
/elis full "Landing page para TaskFlow, um app de gestao de tarefas com IA para times remotos" \
  --reference https://linear.app \
  --stack next \
  --output ./taskflow-landing \
  --with-backend \
  --with-payments
```

## O que o Elis vai fazer

### Phase 1: Discovery (Scout)
- Pesquisar competidores: Linear, Asana, Monday, Notion
- Analisar tendencias de mercado de produtividade
- Avaliar viabilidade e recomendar stack
- Identificar diferenciais competitivos

### Phase 2: Design (Designer + UXer)
**Designer vai criar:**
- Paleta de cores: tons de azul/roxo para confianca + produtividade
- Tipografia: Inter + serif para headlines
- Componentes: cards, pricing tables, feature grids
- Animacoes: scroll reveals, hover effects

**UXer vai validar:**
- Jornada do usuario (awareness → trial → conversion)
- Heuristicas de Nielsen
- Acessibilidade WCAG AA
- CTAs e pontos de friccao

### Phase 3: Build (Builder + Tester)
**Estrutura gerada:**
```
taskflow-landing/
├── app/
│   ├── page.tsx          # Home
│   ├── pricing/page.tsx  # Pricing
│   └── layout.tsx        # Layout
├── components/
│   ├── hero.tsx
│   ├── features.tsx
│   ├── pricing.tsx
│   ├── testimonials.tsx
│   └── cta.tsx
├── lib/
│   └── utils.ts
└── styles/
    └── globals.css
```

### Phase 4: Backend (Supabase)
- Tabelas: users, subscriptions, waitlist
- Auth: email + Google OAuth
- Edge Functions: webhook handlers
- RLS policies configuradas

### Phase 5: Payments (Stripe)
- 3 tiers: Free, Pro ($15/mo), Team ($49/mo)
- Checkout Sessions
- Customer Portal
- Webhooks: subscription.created, subscription.updated

### Phase 6: Deploy (Deployer + Launcher)
- vercel.json configurado
- Environment variables documentadas
- Meta tags e Open Graph
- Sitemap e robots.txt

## Output Esperado

Um site completo e funcional com:
- Design moderno (bento grids, glass morphism)
- Responsivo em todos os breakpoints
- Backend com auth e database
- Sistema de pagamentos integrado
- Deploy automatico no Vercel
- SEO otimizado
