# Scalable Runtime Governance for Agentic AI in Financial Services

## Introduction

### From periodic review to runtime governance

1. Historical Model Risk Management programmes rely on pre-deployment validation and scheduled reviews using aggregate indicators, but **this paradigm becomes increasingly strained** for modern AI systems whose risks materialise as sequences of actions over time.
2. Human oversight is not eliminated, but its function must **shift** from serving as a runtime safety net for every decision toward policy and workflow design, verification and approval structures, threshold setting, and review of monitoring evidence.
3. **Runtime governance** is the real-time monitoring and enforcement of policy over an agentic system's execution trajectory, including governance-semantic telemetry, continuous authorisation, temporal and path conformance checking, trajectory-level drift monitoring, and tiered containment.

### Reusable capabilities as the basis for scalable governance

1. **Capability is the appropriate governance abstraction for bank Model Risk Management** because it defines a bounded class of actions together with authority, constraints, and evidence requirements, allowing risk to be governed at the level of what the system is authorised to do.
2. Capability-centric governance **makes interaction between the first and second lines of defence more structured** because 1LoD can specify which approved capabilities are invoked and in what context, while 2LoD can provide evidence packs, playbooks, limitations, and current performance or incident signals.
3. Capabilities **support failure-mode localisation and learning** because failures can be attributed to specific capability failure modes and trajectories, enabling targeted changes to tests, thresholds, controls, or orchestration that benefit all use cases relying on that capability.

## MRM playbook: capability catalogue, telemetry, and runtime governance

1. The minimal governed objects required for implementation are the capability catalogue, use-case specification, execution trajectory, and governance-semantic telemetry, which together connect reusable evidence to runtime controls and auditable records.
    - The **capability catalogue** defines reusable governance units with stable identifiers, authority scopes, constraints, evidence requirements, and telemetry schema requirements.
    - The **use-case specification** records how a particular workflow composes capabilities, authority scopes, approvals, escalation paths, and deployment-specific monitoring plans.
    - The **execution trajectory** is the run-level sequence of governed states, capability invocations, tool calls, approval events, authorisation decisions, and state transitions over which runtime compliance is assessed.
    - **Governance-semantic telemetry** provides the runtime evidence needed for control enforcement, effective challenge, monitoring, and incident reconstruction.
2. The layered view clarifies how human policy becomes operational governance for agentic systems by translating governance intent into capability specifications, governed execution, telemetry, monitoring, escalation, and change control.
    - Layer 1 consists of **human policy** expressed as regulatory obligations, internal standards, approval requirements, operational procedures, role-based restrictions, and constraints on data access, communication, and external side effects.
    - Layer 2 **operationalises policy** through capability specifications and orchestration specifications that define permitted tools, authority, constraints, evidence requirements, admissible transitions, retries, interrupts, escalation paths, and approval dependencies.
    - Layer 3 is **governed execution**, where a use case runs as an orchestration of capabilities under the constraints defined by capability and orchestration specifications.
    - Layer 4 consists of **telemetry, monitoring, and runtime governance**, where governance-semantic telemetry supports policy enforcement, run reconstruction, population-level monitoring, and recalibration of thresholds, controls, and approvals.
3. **Telemetry sufficiency** means telemetry must be adequate for automated control enforcement, effective challenge by 2LoD, and incident reconstruction, with each trajectory represented as a trace and capability invocations, tool calls, guard evaluations, authorisation decisions, approval events, and containment actions captured as spans, events, or attributes.
4. Practical considerations require monitoring reliability across consistency, robustness, uncertainty awareness, and safety, grouping capabilities into coherent subsystems for reuse and root-cause localisation, detecting orchestration drift, and ensuring binding governance decisions are deterministic functions over governed state and measurable signals rather than advisory LLM judgement.

### Formal Definitions

1. **A capability is an AI component executing a clearly specified bounded set of actions, defined by permitted tools and resource scope, enforceable constraints such as authorisation or approvals, and evidence required to validate and monitor it.**
2. A Governance Decision is **a deterministic function** mapping the current governed state and predefined parameters to a binary outcome, so that no action can occur unless explicitly authorised by computable guards derived from the governed state.

### Risk tiering, control assignment, and incremental governance

1. Risk tiering is determined by capability composition and authority across agency, authority, impact, exposure, and recoverability, with authority and impact as primary drivers and agency, exposure, and recoverability as amplifiers.
2. Risk tiering defines four operational tiers that map agentic-system risk profiles to progressively stronger governance intensity and controls.
    - Tier 1 covers **assistive systems** with low agency and no side effects, where outputs support recommendations or drafts while humans retain full control and access remains read-only with logging and review.
    - Tier 2 covers **bounded workflows** with moderate agency and constrained authority, where limited tool use and reversible actions require allowlists, least-privilege access, approval gates for side effects, dedicated testing, structured telemetry, and adversarial testing.
    - Tier 3 covers **high-impact governed execution** with high authority or consequence, where formal risk assessment, policy-as-code trajectory constraints, continuous authorisation, capability- and trajectory-level monitoring, drift detection, and trace-level auditability are required.
    - Tier 4 covers **critical autonomous systems** with high autonomy and irreversible impact, where authority must be default-deny, critical actions require separation of approval and execution, execution must fail closed, environments must be isolated, rollback and containment are mandatory, and monitoring and governance review must be high frequency.
3. **Incremental residual risk** is the change relative to the approved tiering profile of previously approved deployments, and it exists only when the new use case increases agency, authority, impact, or exposure, or decreases recoverability.
4. Onboarding and sign-off should answer whether the use case fits the validated capability catalogue and orchestration patterns, what tier and controls are required, what incremental control uplift is needed, and whether telemetry is sufficient for runtime governance in production.

### Step-by-step programme with explicit 1LoD/2LoD responsibilities

1. Step 1 **establishes the capability catalogue**, with 2LoD leading taxonomy, specification fields, evidence standards, and approval tiers, Security/Ops co-owning tool authority and telemetry requirements, and 1LoD proposing business-relevant capabilities and contexts.
2. Step 2 **creates capability evidence packs and control playbooks**, where 1LoD builds test harnesses, evaluations, thresholds, and controls, while 2LoD challenges methods, coverage, operating points, and residual risk.
3. Step 3 **onboards use cases as capability compositions**, with 1LoD specifying capabilities, authority scopes, control tiers, approvals, dependencies, monitoring, and escalation plans, and 2LoD reviewing composition, tiering, approval logic, and evidence applicability.
4. Step 4 **performs integration and trajectory conformance testing**, where 1LoD encodes and tests policy monitors, 2LoD challenges coverage of high-severity failure modes, and Security/Ops validates enforcement points, side-effect mediation, fail-closed behaviour, and telemetry integrity.
5. Step 5 **deploys workflows under runtime governance**, enforcing continuous authorisation, tool-intent gating, real-time policy monitors, trace-level evidence, and tiered containment mechanisms such as safe modes, tool restrictions, or human takeover.
6. Step 6 **manages monitoring and reliability**, with 1LoD operating remediation within approved limits, 2LoD reviewing aggregate evidence and threshold adequacy, and Security/Ops ensuring enforcement points, telemetry, and logging remain intact and cannot be bypassed.
7. Step 7 **closes the MRM loop** through change control and continuous improvement, where model, tool, prompt, memory, authority, drift, or incident triggers require 1LoD to rerun tests and update monitoring while 2LoD approves evidence packs and operating thresholds.

## Illustrating runtime governance and capability reuse

1. The U3 credit memo drafting illustration contrasts a naive prompt-guarded workflow vulnerable to stale data, prompt injection, silent numeric error, approval-gate reasoning-around, and orchestration drift with a governed transition system in which retrieval, computation, drafting, approval, and release are mediated by explicit guards.
2. The shared capability cluster shows that KYC review, model validation report review, and credit memo drafting can be implemented as different compositions of long-context extraction, retrieval with attribution, deterministic numeric computation, and policy-constrained drafting and release, with validation, controls, and monitoring reused at the capability level and tightened by use-case context.

## Literature review

1. MRM baselines establish expectations for inventory, intended use and limitations, validation evidence, monitoring plans, documentation, change control, and effective challenge, and these requirements remain binding as AI systems become more agentic.
2. Agentic governance and capability-centric views argue that the key risk surface is not only the base model but the system's capabilities and orchestration, and the paper operationalises this view through pooled capability validation and trajectory-level enforceability.
3. Runtime governance and integrated oversight emphasise that agentic risks manifest as sequences of actions at runtime and therefore require governance-semantic telemetry, authorisation monitoring, conformance checking, drift detection, and containment.
4. Evaluation practice and reliability measurement emphasise failure-mode-driven evaluation, regression tests as lifecycle assets, and explicit monitoring of consistency, robustness, predictability, uncertainty awareness, and safety rather than relying on average task success.
5. Agent security and state-dependent vulnerabilities show that tool-using agents can be vulnerable at specific execution states and that backbone vulnerabilities can be amplified through tool use and memory, motivating adversarial threat-snapshot testing and state-aware runtime monitoring.
6. Observability standards such as OpenTelemetry provide implementation primitives for representing one execution trajectory as a trace, capability invocations and tool calls as spans, and governance semantics such as capability IDs, tool intents, guard scores, authorisation decisions, approvals, and containment actions as attributes or events.
