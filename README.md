# ASP — Agent Sharing Protocol

ASP is a minimal, open protocol that allows AI agents to share completed work results so other agents can verify and reuse them instead of recomputing the same work.

ASP enables agents to share what has already been done, not how to do it.

---

## Why ASP Exists

Human requests to AI systems are often diverse and personalized.

However, beneath these differences, AI agents repeatedly perform highly similar internal computation:
- Parsing the same structures
- Analyzing the same code or data
- Evaluating the same conditions
- Producing similar intermediate conclusions

Today, this work is almost always recomputed from scratch.

ASP exists to reduce redundant machine computation by enabling agents to describe, publish, discover, verify, and reuse completed work results produced by other agents.

ASP focuses on machine-level efficiency, not human-level content reuse.

---

## Core Idea

ASP does NOT enable agents to share:
- Skills
- Prompts
- Workflows
- Behaviors
- Execution logic

ASP enables agents to share **artifacts**.

An artifact is a completed work result produced by an agent after performing a specific task or subtask.

Artifacts represent outputs of computation, not capabilities of agents.

---

## What Kind of Work Is Shared

ASP is designed primarily for sharing neutral, reusable, and verifiable work results, such as:

- Structural analysis outputs (for example: abstract syntax trees, dependency graphs)
- Deterministic transformations
- Logical or mathematical conclusions
- Intermediate analysis results
- Subtask-level reasoning outputs
- Structured data extraction
- Safety, validity, or consistency assessments

Artifacts do not need to be complete, user-facing deliverables.

Partial and intermediate results are valid and encouraged.

ASP is not focused on sharing preference-driven or personalized final outputs.

---

## How ASP Is Used

A typical agent workflow with ASP looks like this:

1. Before performing a task, an agent computes a canonical hash of its task input or subtask input.
2. The agent searches for existing ASP artifacts that match or relate to that input.
3. If a relevant artifact is found, the agent may retrieve and verify it.
4. Verified artifacts may be reused fully or partially to reduce recomputation.
5. If no suitable artifact exists, the agent performs the computation and publishes a new artifact for future agents.

ASP replaces repeated computation with verification and reuse.

---

## Verification, Not Trust

ASP does not assume trust between agents.

Artifacts may be verified through:
- Full or partial recomputation
- Cryptographic signatures
- Formal or probabilistic proofs

Verification is optional but strongly recommended.

ASP does not define which verification method must be used.

---

## Decentralization by Design

ASP does not require:
- A central server
- A global registry
- An approval process
- An identity system
- A hosting platform

Artifacts may be stored anywhere that is publicly accessible, including:
- Public repositories
- Content-addressed networks
- Cloud storage
- Local or private servers

ASP standardizes artifact description, not storage or discovery.

---

## What ASP Is Not

ASP is NOT:
- A skill-sharing network
- An agent marketplace
- A workflow orchestration framework
- A centralized registry
- A blockchain protocol
- A monetization system
- A content trading platform

ASP does not coordinate agents.
ASP does not execute tasks.
ASP does not enforce policies.

---

## Example Scenario

Agent A analyzes a smart contract and produces several artifacts:
- A control flow graph
- A vulnerability assessment
- Intermediate reasoning results

Agent B later receives a related task.

Instead of recomputing all analysis steps, Agent B:
- Discovers relevant artifacts
- Verifies them
- Reuses verified components
- Performs only task-specific computation

Computation is reduced.
Verification replaces repetition.

---

## Specification

The formal protocol definition is available in:

SPEC.md

The specification defines:
- Artifact structure
- Reuse model
- Verification concepts
- Protocol boundaries

---

## Vision

ASP enables a future where AI agents build on top of each other's completed work, forming a decentralized layer of reusable machine intelligence.

By reducing redundant computation, ASP improves efficiency, scalability, and sustainability across the AI ecosystem—without introducing centralized control or trust dependencies.

---

## Status

ASP is an early-stage, open protocol.

The current version is a draft.
Feedback, discussion, and experimentation are welcome.

---

## License

ASP is released under the MIT License.

Any individual or organization may implement, extend, or adopt the protocol freely.
