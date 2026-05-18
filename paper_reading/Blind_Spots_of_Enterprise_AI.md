# The Blind Spots of Enterprise AI -- Risks Your Governance Framework Isn’t Looking For

## Blind Spots and Gaps

### Why the Frameworks Aren’t Enough

1. twelve **enterprise-AI blind spots**: definitions, sponsorless pilots, missing control plane, shadow AI, productivity loopholes, cadence mismatch, checker dependence, HITL overreach, consensus gaps, weak AI counsel, reward hacking, and vendor resilience.
2. Established frameworks succeed at classification, documentation, human oversight, prohibitions, and vendor due diligence, but leave **operating gaps** around <u>continuous AI traffic, runtime telemetry, prompt intent, productivity deployments, and vendor concentration</u>.

### Is GenAI a model

1. The MRM-versus-IT debate has the wrong shape because GenAI should be governed **by what it is being used for**, not by whether the underlying technology is labeled a model, IT tool, productivity feature, or vendor service.
2. FHFA AB 2022-03 provides a use-based framing in which AI/ML output **used as a key basis for business decision-making, risk management, or financial reporting** receives MRM expectations, while non-decisional uses follow risk-commensurate governance.
3. Enterprise AI deployments should be mapped by **primary use** — <u>decisional, advisory/co-pilot, assistive, or utility</u> - so that each deployment, rather than the underlying model weights, becomes the governance unit.
4. In practice, enterprises need an **AI-use inventory**, **shared MRM/IT ownership** resolved by the use-based test, and a **defensible GenAI governance regime** because SR 26-2’s GenAI exclusion is not a license to under-govern.

### The Sponsor-less Pilot Trap

1. A productive AI pilot requires **a named executive sponsor, an accountable delivery officer, pre-agreed success and ROI metrics, and in-house research capacity** capable of converting pilot learnings into production assets.

### The Missing AI Control Plane

1. An AI control plane **must provide** prompt-intent inspection, tool-call and agent hand-off tracing, automated response-quality monitoring, cost-aware routing, and vendor concentration mitigation.
2. The **reference architecture** routes all prompts, responses, tool calls, and agent hand-offs through a control plane that emits OpenTelemetry GenAI spans into the enterprise observability backend.
3. A web gateway can block known-bad domains and apply DLP regexes, but an **AI control plane is required** for intent classification, prompt-injection detection, agent trajectory correlation, response-quality scoring, token accounting, multi-vendor routing, and vendor resilience.

### Shadow AI and the Untrained Operator

1. The 25-page-prompt scenario shows how an **untrained operator can unknowingly delegate** a material underwriting decision to an LLM through context-window exhaustion, lost-in-the-middle degradation, and single-shot reasoning over a complex task.
2. **Prompt-engineering training is insufficient** because context limits, mid-context degradation, single-shot complex reasoning, and silent confabulation are structural properties of the technology rather than merely operator skill issues.
3. A **four-tier shadow-AI control model** distinguishes personal productivity, enterprise-data input, externally visible decision support, and regulated or material decisions, with controls escalating from acceptable-use policy to MRM-grade governance and certified operators.

## Close the Gap Between the Framework and the Operating Reality

### The Productivity-Tool Loophole

1. The **three-question test** asks whether AI output materially influences an external-party decision, whether the recommendation would be followed without independent verification, and whether a regulator, plaintiff, or auditor could reasonably ask how the system works and what its error rate is.
2. A defensible AI inventory **must capture every system** that calls a generative model API, the decisions or actions it supports, its assigned governance regime, data sources, model families, and applicable control-plane policies.

### Rethinking Cadence and Controls

1. The **independence problem** arises when the same model family produces and checks an output, because shared training data, RLHF pipelines, architectural biases, and failure modes make the check decorative rather than independent.
2. **Cross-family ensembling** mitigates correlated-failure risk for mission-critical tasks by having independent model families produce candidate responses and aggregating them through voting, ranking, or LLM-as-judge methods, with disagreement becoming an escalation signal.
3. **Human-in-the-loop is not the default control** because it works only when volume is low, reviewers are expert, and reviewers have time and incentive to disagree, otherwise it predictably degrades into a rubber stamp.

### A Multi-Agent Consensus Framework with Human Arbitration

1. A **multi-agent consensus framework** rests on cross-model verification, ensemble diversity with arbitration logic, and **human escalation reserved for edge cases** where cross-family agents disagree or confidence is low.
2. Recommended checker families should **come from different model families** than the primary agent so that cross-family diversity can surface family-specific blind spots, reduce unchanged targeted backdoors, and limit propagation of degenerate patterns.

### Hybrid Escalation, Misalignment, and Reward Hacking

1. Misalignment and reward hacking require **abandoning human-motivation analogies** because AI agents do not seek money, status, or concealment, but optimize explicit or implicit reward signals that may be mis-specified.
2. AI-agent investigations should **focus on** prompt templates, retrieval corpus, reasoning summaries, intermediate artifacts, tool traces, reward signals, and the difference between what the model said and what it actually did.
3. Evaluation debt arises when an enterprise **lacks versioned golden datasets and regression suites**, leaving it unable to detect performance regressions when the model, prompt, or retrieval corpus changes.