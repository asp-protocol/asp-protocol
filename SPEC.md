# ASP — Agent Sharing Protocol
Version 0.1 (Draft)

---

## 1. Introduction

AI agents frequently perform large amounts of overlapping computation.

Although human requests appear diverse, the internal work performed by agents—such as parsing inputs, analyzing structures, evaluating conditions, and producing intermediate conclusions—is often highly repetitive across tasks, users, and systems.

Today, these completed work results are rarely reused. Each agent independently recomputes similar analyses, resulting in unnecessary cost, latency, and energy consumption.

ASP (Agent Sharing Protocol) defines a minimal, open standard that allows AI agents to describe, publish, discover, verify, and reuse completed work results produced by other agents—without requiring a central platform, registration, or trusted authority.

ASP focuses on sharing what has already been computed, not how agents perform tasks.

ASP is not a product.
ASP is not a marketplace.
ASP is not a service.
ASP is a protocol.

---

## 2. Core Concept

### 2.1 Artifacts, Not Abilities

In ASP, agents do NOT share:
- Skills
- Prompts
- Workflows
- Behaviors
- Execution logic

Agents share artifacts.

An artifact is a completed work result produced by an agent after performing a specific computational task or subtask.

Artifacts represent outputs of computation, not capabilities of agents.

---

### 2.2 Scope of Shared Work

ASP is designed primarily for sharing neutral, reusable, and verifiable work results, including:

- Structural analysis outputs (for example: abstract syntax trees, dependency graphs)
- Deterministic transformations
- Logical or mathematical conclusions
- Intermediate analysis results
- Subtask-level reasoning outputs
- Structured data extraction
- Safety, validity, or consistency assessments

Artifacts do not need to be complete, user-facing deliverables.
Partial and intermediate results are valid and encouraged.

---

## 3. Design Principles

ASP follows these principles:

1. Result over ability  
   Share completed work results, not agent capabilities.

2. Verification over trust  
   Artifacts must be independently verifiable.

3. Decentralization by default  
   No central registry, server, or authority is required.

4. Minimal structure  
   The protocol defines only what is necessary for reuse.

5. Permissionless adoption  
   Any agent may publish or consume ASP artifacts.

6. Content neutrality  
   ASP does not judge usefulness, quality, or ownership.

---

## 4. Artifact Reuse Model

### 4.1 Levels of Reusability

Artifacts may exist at different levels, including:

- Structural artifacts  
  Deterministic representations derived from input.

- Analytical artifacts  
  Objective conclusions or evaluations.

- Intermediate artifacts  
  Results of subtasks or partial reasoning.

ASP prioritizes machine-level reusable work rather than preference-driven final outputs.

---

### 4.2 Partial Reuse

Artifacts do not need to match future tasks exactly.

Agents may:
- Reuse parts of an artifact
- Combine multiple artifacts
- Use artifacts as verified inputs to new computation

ASP reduces redundant computation rather than replacing task execution entirely.

---

## 5. Artifact Description Format

An ASP artifact is described using the following JSON structure:

    {
      "artifact_id": "sha256(canonical_input_hash + canonical_output_hash)",
      "task_type": "string",
      "input_hash": "sha256(original_input)",
      "output_hash": "sha256(result_output)",
      "created_by": "agent_identifier",
      "created_at": 1735689600,
      "artifact_scope": "structural | analytical | intermediate | other",
      "location": "https://... or ipfs://...",
      "verification": {
        "method": "recompute | signature | proof",
        "details": "optional"
      }
    }

All fields are descriptive.
ASP does not enforce how artifacts are generated, stored, or discovered.

---

## 6. Agent Interaction Flow

### 6.1 Before Computation

An agent may:
1. Compute a canonical hash of its task input or subtask input.
2. Search for existing ASP artifacts with matching or relevant input hashes and task types.

Discovery mechanisms are implementation-specific and outside the scope of this specification.

---

### 6.2 Artifact Reuse

If a relevant artifact is found, the agent may:
- Retrieve the artifact
- Verify its integrity and validity
- Reuse part or all of the result
- Skip or reduce recomputation

Verification is optional but strongly recommended.

---

### 6.3 Artifact Publication

If no suitable artifact exists, the agent may:
- Perform the computation
- Produce a new artifact
- Publish its description for future agents

Publication does not imply ownership, endorsement, or permanence.

---

## 7. Verification

ASP does not assume trust between agents.

Artifacts may be verified through:
- Full or partial recomputation
- Cryptographic signatures
- Formal or probabilistic proofs

Verification methods are optional and extensible.

---

## 8. Storage and Discovery

ASP does not define storage, hosting, or discovery mechanisms.

Artifacts may be stored on:
- Public repositories
- Content-addressed networks
- Cloud storage
- Local or private servers

ASP standardizes description, not distribution.

---

## 9. What ASP Is Not

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

## 10. Example Scenario

Agent A analyzes a smart contract and produces:
- A control flow graph
- A vulnerability assessment
- Several intermediate reasoning artifacts

Agent B later receives a related task.

Instead of recomputing all analysis steps, Agent B:
- Discovers relevant artifacts
- Verifies them
- Reuses verified components
- Performs only task-specific computation

Computation is reduced.
Verification replaces repetition.

---

## 11. Vision

ASP enables a future where AI agents build upon each other's completed work, forming a decentralized layer of reusable machine intelligence.

By reducing redundant computation, ASP improves efficiency, scalability, and sustainability across the AI ecosystem—without introducing centralized control or trust dependencies.

---

## 12. License

ASP is released under the MIT License.

Any individual or organization may implement, extend, or adopt the protocol freely.
