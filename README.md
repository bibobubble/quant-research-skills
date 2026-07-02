# Quant Research Skills

Reusable AI assistant skills for quantitative research workflows.

## Included skills

- `quantitative-investing`: A systematic investing research workflow inspired by Giuseppe A. Paleologo's *The Elements of Quantitative Investing*. It covers alpha research, backtesting, risk and factor models, portfolio construction, transaction costs, hedging, Kelly sizing, drawdown control, capacity, and performance attribution.

## Install for Codex-style skills

Clone this repository, then copy the skill folder into your local skills directory:

```bash
git clone https://github.com/bibobubble/quant-research-skills.git
mkdir -p ~/.codex/skills
cp -R quant-research-skills/quantitative-investing ~/.codex/skills/
```

Then invoke it with:

```text
Use $quantitative-investing to review this alpha backtest.
```

## Use with Claude

If your Claude setup supports project instructions or custom skills, add the `quantitative-investing/SKILL.md` instructions and keep the `references/` folder available for deeper task-specific context.
