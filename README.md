Cursor AI Coding Playbook

Lightweight rules to help AI copilots write better code, reduce compute cost, and keep teams moving fast.

This repo contains the Cursor Rules I use across projects to ensure high-quality output, predictable model behavior, and efficient use of compute. These rules guide architecture, planning, code style, and model-choice discipline when working with AI copilots.

They are intentionally small, opinionated, and built for speed.

⸻

📘 What’s Inside

Each rule lives as a modular .mdc file inside rules/. Cursor automatically loads and applies them in projects using this repo via worktrees.

1. Architecture Principles

High-leverage architectural constraints for small and mid-sized AI-driven products. Helps copilots generate stable, scalable solutions without over-engineering.

2. Clean, Simple, DRY

Forces copilots to favor clarity, simplicity, and reuse. Reduces surface area, makes diffs smaller, and keeps projects maintainable.

3. Full-Stack Programming

Guidance for end-to-end implementation—React, backend, DB—so AI agents produce coherent, integrated features rather than isolated fragments.

4. Effective Planning

Planning templates and conventions that keep tasks atomic, scoped, and easy to execute. Prevents runaway context, multi-feature merges, and diff bloat.

5. Model Economy

Rules for using Sonnet, Codex, and Cursor efficiently—minimizing token burn while maintaining speed. Includes:
	•	model-check header
	•	CHEAP / STANDARD / PREMIUM task classification
	•	guardrails against slow or expensive actions

6. Models Rule (Meta-Rule)

Lightweight behavioral constraints for Cursor’s model itself (e.g., output format, cost-aware classification). Ensures consistent model behavior across tasks.

⸻

🎯 Why This Exists

AI copilots are powerful, but without guardrails they can:
	•	escalate models unnecessarily
	•	rewrite full files
	•	load huge contexts
	•	thrash between tasks
	•	burn compute without improving results

These rules solve that by giving the models a shared language, shared constraints, and consistent execution framework.

⸻

🛠 How to Use

You can consume these rules in three ways:

1. Add as a Git worktree (recommended)

   git worktree add .cursor cursor-worktree

   Then use Cursor’s “Project Rules” interface to enable them.

2. Clone the repo and copy the rules folder

Simple, direct, portable.

3. Import specific rules selectively

Each .mdc file is standalone and safe to use independently.

⸻

📄 Repo Structure

/rules
  architecture-principles.mdc
  clean-simple-dry.mdc
  full-stack.mdc
  implement-plan.mdc
  model-economy.mdc
  models.mdc

  🤝 Contributing

This playbook will evolve as Cursor, Sonnet, and Codex evolve.
PRs and discussions are welcome—especially around:
	•	improved model-economy heuristics
	•	React/Next.js patterns
	•	better planning formats
	•	safety or correctness guardrails
