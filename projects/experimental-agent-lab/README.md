# Experimental Game and Agent Engineering

Artifact Type: RESEARCH DOMAIN / SIMULATION LAB CANDIDATE

Project Status: CONCEPT

Maturity Status: CONCEPT / HYPOTHESIS

Public Repository Status: RESEARCH DIRECTION SUMMARY

## System Role

This research direction explores bounded game and simulation environments as repeatable laboratories for observing and comparing agent behaviour.

The manifesto identifies research around Ultima, Elite, assembly-language heritage, local AI agents, and a competitive evaluation arena. It describes an exploratory research direction, not a completed game, a verified agent framework, or a commercial product.

## Research Questions

- How can agents be compared under identical rules, observations, and resource constraints?
- How can planning, navigation, resource management, and adaptation be measured?
- How can an evaluation distinguish general capability from prompt-specific exploitation?
- How should tool calls, decisions, failures, and outcomes be recorded?
- How can simulation outcomes be related to real-world engineering without treating simulation as physical validation?

## Candidate Architecture

| Layer | Responsibility | Current state |
|---|---|---|
| Environment adapter | Provide a bounded game/simulation interface | CONCEPT |
| Observation model | Convert environment state into structured agent observations | HYPOTHESIS |
| Agent interface | Expose a common decision/action contract | CONCEPT |
| Scenario runner | Execute repeatable tasks and seeds | CONCEPT |
| Evaluation harness | Score outcomes and detect invalid/exploited runs | CONCEPT |
| Evidence recorder | Preserve prompts, tool calls, actions, decisions, and outcomes | DESIGN DIRECTION |
| Comparative analysis | Compare agent classes under equal conditions | CONCEPT |

## Relationship to ERICA OS

ERICA OS may provide project, evidence, and model-routing services if a future implementation justifies integration. The simulation environment must retain its own bounded rules and authoritative state. An agent's recommendation is not a valid action until the environment validates it.

## Maturity Boundary

No current executable game environment, game-engine integration, agent competition, or benchmark result is claimed in this repository. The named game and historical research themes are context for a research direction, not proof that those environments have been implemented.

## Next Verification Gates

1. Recover and inventory any historical game/assembly-language source trees before defining implementation scope.
2. Identify which game assets, engines, emulators, and interfaces can legally and technically be used.
3. Define an environment API and deterministic scenario model.
4. Build a baseline scripted agent before introducing LLM-based agents.
5. Create repeatable evaluation tasks, seeds, and scoring rules.
6. Capture every run as evidence and test for reward hacking and environment leakage.
