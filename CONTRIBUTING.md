# Contributing to ELIS

Thanks for your interest in contributing to ELIS. This guide covers how to get started, add new agents, modify contracts, and submit your changes.

## Getting Started

### Install and test the skill

```bash
git clone https://github.com/xiapeli/elis.git
cd elis

# Copy the skill file to your Claude Code commands directory
mkdir -p ~/.claude/commands
cp -n elis.md ~/.claude/commands/

# Test it works
# Open Claude Code and run:
/elis design "A minimal portfolio site"
```

### Project structure

```
elis.md               # The main skill file (all agent definitions)
docs/
  agents.md           # Full agent reference
  contracts.md        # Contract system specification
  customization.md    # How to customize ELIS defaults
examples/             # Walkthrough examples (SaaS, portfolio, startup)
prd-loop/             # Autonomous PRD-driven development loop
```

## How to Add a New Agent

1. **Pick the right layer.** ELIS has 6 layers: Discovery, Design, Build, Backend, Deploy, Business. Your agent should fit one of them.

2. **Define the contract (partitura).** Every agent needs a structured contract with:
   - `model` — which Claude model it uses (haiku, sonnet, opus)
   - `input_contract` — required and optional inputs
   - `output_contract` — expected output format and schema
   - `quality_gates` — pass/fail criteria
   - `timeout_ms` and `max_retries`

3. **Write the agent prompt.** Add your agent definition inside `elis.md` under the appropriate layer section. Follow the existing pattern: role description, capabilities, input/output format, and quality gates.

4. **Update the README.** Add your agent to the layer table in `README.md` and to `docs/agents.md`.

5. **Add an example.** If possible, add a usage example in the `examples/` directory showing the agent in action.

## How to Modify Contracts

Contracts live inside `elis.md` as structured definitions for each agent. To modify one:

1. Read the existing contract in `elis.md` for the agent you want to change.
2. Update the relevant fields (input/output schemas, quality gates, timeout, etc.).
3. Update `docs/contracts.md` if your change affects the contract specification.
4. Test the agent with the modified contract by running the relevant `/elis` command.

**Important:** Changing a contract's output schema may break downstream agents that consume its output. Grep for the agent name across `elis.md` to find all dependencies before modifying.

## PR Process

1. **Fork** the repository.
2. **Create a feature branch** from `main`:
   ```bash
   git checkout -b feat/add-copywriter-agent
   ```
3. **Make your changes** following the patterns described above.
4. **Use conventional commits:**
   - `feat:` — new feature (new agent, new command, new preset)
   - `fix:` — bug fix
   - `docs:` — documentation only
   - `refactor:` — code restructuring without behavior change
   - `test:` — adding or updating tests
5. **Open a Pull Request** against `main` with a clear description of what you changed and why.

## Ideas for Contributions

These are good starting points. See also the [issues labeled `good first issue`](https://github.com/xiapeli/elis/labels/good%20first%20issue).

- **New agents:** Analytics, Copywriter, SEO specialist
- **Design presets:** brutalist, corporate, playful themes
- **Example PRDs:** common project types for the PRD loop
- **Translations:** translate agent prompts to other languages
- **Integration tests:** tests for the contract system
- **Documentation:** improve existing docs, add tutorials

## Code of Conduct

Be respectful and constructive. We follow standard open-source etiquette. No tolerance for harassment, trolling, or bad-faith contributions.
