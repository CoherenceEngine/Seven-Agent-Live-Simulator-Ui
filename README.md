# Coherent Agents, Eight-Role Architecture Simulator

Explore how assumed role reliability and feedback routing affect an illustrative architecture model.

[Open the simulator](https://coherenceengine.github.io/Seven-Agent-Live-Simulator-Ui/)

## Name and scope

The repository retains its historical name, `Seven-Agent-Live-Simulator-Ui`, to preserve existing links. The current implementation contains **eight modeled roles**: Router, Planner, Coder, Executor, Critic, Memory, Verifier and Tool. Its display name is Eight-Role Architecture Coherence Simulator.

This is a browser-based JavaScript simulator and reporting interface. Roles are configurable nodes, not independently executing AI agents. No language-model calls, autonomous task execution, production telemetry or Coherence Engine backend integration are implemented here.

## Implemented features

- Adjust role reliability proxies and noise presets.
- Compare a base directed acyclic graph with an optional Critic-to-Executor feedback edge.
- Inspect graph connections and adjacency matrices.
- Save scenarios in browser localStorage and compare saved configurations.
- Import and export JSON configurations.
- Generate a template-based narrative and a printable report with configurable branding. PDF export uses the browser print dialog.

## Run

Open `index.html` in a modern browser, or use the hosted simulator above. No API key, package installation or backend is required.

Adjust the reliability controls, toggle feedback and inspect the Architecture, Matrices and Results tabs. Save two scenarios to compare them. Double-click Load to import a JSON file. Use Export PDF Report, then the browser's print-to-PDF option.

Saved scenarios stay in that browser's localStorage. Export JSON for a portable copy. Import only trusted, compatible files; imported fields are not comprehensively validated or sanitized. Avoid entering sensitive information.

## Model assumptions and limitations

- Reliability values (`d`), edge weights (`rho`), costs and latencies are supplied assumptions, not calibrated measurements.
- Role scores use `exp(-kPerf * (1 - d))`. Architecture scores combine their mean with weighted edge contributions and fixed penalties. They are not calibrated probabilities and may exceed 1.
- The optional feedback edge changes the algebraic score. It does not execute a feedback process or establish actual recovery, stability or causal improvement.
- Error reduction is a heuristic transformation of the absolute score difference. It can show a positive value even when the architecture score declines. It is not measured task-error reduction.
- Loop-risk labels use a fixed algebraic proxy; they are not a stability proof. Bottleneck labels use the weakest assumed reliability, not observed queues or throughput.
- Cost and latency sum configured per-role constants. Routing, retries, concurrency, token usage and provider billing are not measured.
- ROI categories are fixed score thresholds, not financial returns or deployment-readiness evidence.
- Trajectory charts contain 11 seeded synthetic points. The historical “Simulation Runs” control changes the random seed; it does not execute that number of Monte Carlo trials. The interface now labels it “Scenario seed parameter.”
- Each chart series is scaled independently. Visual overlap does not establish equal scores.
- Narrative regeneration selects templates and also changes the trajectory seed. It does not call an AI model.
- “Optimize My Architecture” increases the weakest role's assumed reliability and may disable feedback. It does not train, deploy or repair an agent.

These limitations apply to dashboard values and exported reports. This repository does not establish production savings, commercial readiness, validated agent performance or validation of The Coherence Engine™.

## Licensing and IP boundary

See [LICENSE](LICENSE). This repository uses a proprietary, all-rights-reserved notice, not an open-source license. Commercial reuse, redistribution and derivative-product permissions require a separate written agreement, subject to applicable law and GitHub's platform terms.

These terms cover only the simulator materials in this repository to the extent owned by the rights holder. They do not license The Coherence Engine™ core implementation, proprietary operators, private research assets, patents or patent applications, or trademarks. No permissions for another repository are changed.

Copyright and licensing requests: contact the CoherenceEngine repository owner through GitHub.

## Next implementation gates

Real agent execution would require model/tool adapters, orchestration, task-level evaluations and recorded traces. Performance claims would require measured baselines, repeated trials, error accounting and validation of cost and latency. These are future work, not current features.
