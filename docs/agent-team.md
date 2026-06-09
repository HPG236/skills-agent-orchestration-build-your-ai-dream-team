# Agent team

This repository uses a small custom agent team to build Mona's Project Pulse dashboard. Each agent's definition lives under .github/agents/*.agent.md and is invoked via the GitHub Copilot CLI running in a Codespace.

Agents:

- Planner — model: Claude Opus 4.7 (copilot)
  - Responsibility: Research the codebase, docs, dependencies and produce practical implementation plans with file-level assignments, dependencies, edge cases, and validation criteria.
  - Definition: .github/agents/planner.agent.md

- Orchestrator — model: Claude Opus 4.7 (copilot)
  - Responsibility: Coordinate Planner, Coder, and Designer; break plans into phases, assign explicit file scopes, run parallel or sequential tasks, and verify integration.
  - Definition: .github/agents/orchestrator.agent.md

- Coder — model: GPT-5.5 (copilot)
  - Responsibility: Implement code and runnable app changes within assigned file scopes, validate behavior, and create support launch/config files when explicitly assigned (Project Pulse: .vscode/launch.json with cwd set to app).
  - Definition: .github/agents/coder.agent.md

- Designer — model: Gemini 3.1 Pro (copilot)
  - Responsibility: Handle UI/UX, accessibility, visual design, and provide styling guidance for a polished Project Pulse dashboard (CSS hooks like .dashboard and .project-card).
  - Definition: .github/agents/designer.agent.md

Note: All agents follow repository patterns and do not stage, commit, or push changes — git operations are controlled via the Copilot CLI prompts in this Codespace.