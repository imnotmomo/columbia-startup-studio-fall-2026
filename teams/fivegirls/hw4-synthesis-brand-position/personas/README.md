# Persona Agents

Maya, Chloe, and Alex are fictional customer composites. Their names and ages belong to the personas; the linked source accounts ground their needs. Each includes two real Reddit excerpts, specific objections, calibration, and a structured verdict. They follow the [course persona template](https://github.com/kenxle/columbia-startup-studio-fall-2026/blob/main/resources/template_persona-agent.md).

## Installed definitions

| Persona | Submission file | Codex role | Claude-compatible copy |
| --- | --- | --- | --- |
| Maya, 22 | [judge-maya.md](judge-maya.md) | [judge_maya](../../../../.codex/agents/judge-maya.toml) | [judge-maya](../../../../.claude/agents/judge-maya.md) |
| Chloe, 21 | [judge-chloe.md](judge-chloe.md) | [judge_chloe](../../../../.codex/agents/judge-chloe.toml) | [judge-chloe](../../../../.claude/agents/judge-chloe.md) |
| Alex, 24 | [judge-alex.md](judge-alex.md) | [judge_alex](../../../../.codex/agents/judge-alex.toml) | [judge-alex](../../../../.claude/agents/judge-alex.md) |

The project Codex definitions live in `.codex/agents/`, using the [documented standalone TOML format](https://learn.chatgpt.com/docs/agent-configuration/subagents). They inherit the chosen model and use read-only instructions. Claude-format files live in `.claude/agents/`; Claude was not installed in the shell used for this task, so recorded tests used Codex sessions.

## Reuse

Start a fresh Codex session from this repository. Ask: “Have judge_maya, judge_chloe, and judge_alex separately review `teams/fivegirls/hw4-synthesis-brand-position/brand_position.md`. Return each verdict, then compare their dealbreakers.” The code tool must support custom agents and load this trusted project configuration. With another model that has file access, load each persona definition in a separate session and show it the same artifact.

Keep each review tied to its exact input version. [Review notes](persona_review.md), [short test notes](persona_test_notes.md), raw JSON outputs in `review_runs/`, and frozen inputs in `review_history/` record what was actually evaluated. The imported assistant-role review is archived separately; its missing earlier v1 was not reconstructed.

## Source boundaries

Maya uses C02 and Reddit R1–R2. Chloe uses Reddit R2–R3; her earlier simulated C03 biography and quotes have been removed. Alex uses A02 and Reddit R4–R5. He tests luggage-related choices, not the full range of wheelchair access requirements. Numeric profile values are persona design choices. No review establishes demand or willingness to pay.
