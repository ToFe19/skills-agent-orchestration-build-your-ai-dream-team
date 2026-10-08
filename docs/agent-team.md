# Agent team

For Mona's Project Pulse dashboard, I will use a four-agent team defined under the repository's agent folder: `.github/agents/`.

## Team overview

- Orchestrator — model: Claude Opus 4.7 (copilot)
  - Responsibility: coordinates the overall workflow, breaks the dashboard work into phases, delegates tasks to the specialist agents, and verifies that the final result fits together.
  - Definition: `.github/agents/orchestrator.agent.md`

- Planner — model: Claude Opus 4.7 (copilot)
  - Responsibility: researches the project, identifies dependencies and edge cases, and produces the implementation plan for the dashboard with clear file ownership and sequencing.
  - Definition: `.github/agents/planner.agent.md`

- Designer — model: Gemini 3.1 Pro (copilot)
  - Responsibility: focuses on the dashboard's UI/UX, accessibility, information hierarchy, and polished visual design so the app feels like a professional Project Pulse frontend.
  - Definition: `.github/agents/designer.agent.md`

- Coder — model: GPT-5.5 (copilot)
  - Responsibility: implements the dashboard code, data model, and supporting config in the app files, including creating the launch setup needed to run the static dashboard.
  - Definition: `.github/agents/coder.agent.md`

## How the team will work

The Orchestrator will drive the work by asking the Planner for a plan, then delegating implementation tasks to the Designer and Coder in the right sequence. The Designer will shape the dashboard experience, while the Coder will build the actual UI, styling, and static data files. I am using GitHub Copilot CLI in a Codespace to orchestrate this multi-agent workflow and keep each specialist focused on its assigned scope.
