# Exemplo: Portfolio Pessoal

## Comando

```bash
/elis full "Portfolio minimalista para designer UI/UX com foco em case studies" \
  --reference https://www.craftz.dog/ \
  --stack astro \
  --output ./portfolio
```

## O que o Elis vai fazer

### Phase 1: Discovery (Scout)
- Analisar portfolios de referencia (Craftz.dog, Rauno, etc.)
- Identificar patterns de portfolios de sucesso
- Recomendar estrutura de case studies

### Phase 2: Design (Designer + UXer)
**Design System:**
- Cores: preto/branco com accent color unico
- Tipografia: mono ou sans-serif clean
- Layout: muito whitespace, grid minimalista
- Animacoes: sutis, scroll-triggered

**Secoes:**
1. Hero com nome e titulo
2. Sobre (bio curta)
3. Work (grid de projetos)
4. Case study pages
5. Contato

### Phase 3: Build (Builder)
**Stack: Astro**
```
portfolio/
├── src/
│   ├── pages/
│   │   ├── index.astro
│   │   └── work/[slug].astro
│   ├── components/
│   │   ├── Header.astro
│   │   ├── ProjectCard.astro
│   │   └── Footer.astro
│   ├── layouts/
│   │   └── Base.astro
│   └── content/
│       └── projects/
├── public/
└── astro.config.mjs
```

### Phase 6: Deploy
- Deploy no Vercel/Netlify
- Meta tags otimizadas
- Performance A+ no Lighthouse

## Output Esperado

Portfolio minimalista com:
- Design elegante e clean
- Animacoes sutis
- Sistema de case studies
- Performance excelente (Astro = zero JS por padrao)
- SEO otimizado para "UI/UX Designer"
