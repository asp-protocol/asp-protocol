# ASP — Agent Sharing Protocol
Version 0.1 (Draft)

---

## 1. Introduction

AI agents frequently repeat work that has already been completed by other agents.

Tasks such as code audits, research analysis, reasoning, data transformation, and structured generation are recomputed independently across agents, resulting in duplicated computation, increased cost, and wasted time.

ASP (Agent Sharing Protocol) defines a minimal, open protocol that allows AI agents to describe, publish, and reuse completed work results, enabling other agents to verify and reuse those results without necessarily recomputing the entire task.

ASP is not a platform, not a marketplace, and not a service.

ASP is a protocol for agent-to-agent sharing of completed work results.

---

## 2. Scope and Non-Goals

### 2.1 In Scope

ASP defines:

- A standard way to describe completed work results
- A minimal metadata format for shared results
- Common semantics for verification and reuse

### 2.2 Explicit Non-Goals

ASP does not define:

- Task execution or scheduling
- Agent coordination or orchestration
- Skill, capability, or tool sharing
- Agent identity, reputation, or trust systems
- Artifact discovery, indexing, or ranking mechanisms
- Storage infrastructure or hosting requirements
- Monetization or access control mechanisms

ASP is a description protocol, not a workflow engine.

---

## 3. Core Concepts

### 3.1 Artifact

An artifact is a completed work result produced by an agent after performing a specific task.

Examples include, but are not limited to:

- Smart contract audit results
- Code analysis reports
- Research summaries
- Data transformation outputs
- Logical reasoning results
- Structured or machine-readable outputs

Artifacts represent outcomes, not abilities, prompts, or execution processes.

### 3.2 Result-Oriented Sharing

In ASP:

- Agents do not share skills, models, prompts, or tools
- Agents share completed outputs
- Reuse is optional and always subject to verification by the consuming agent

---

## 4. Design Principles

ASP follows these principles:

1. Result over ability  
   Share outcomes, not skills or execution logic.

2. Verification over trust  
   Artifacts must be independently verifiable by consuming agents.

3. No central authority  
   No registry, coordinator, or required service exists.

4. Minimal structure  
   Use a simple, extensible JSON-based metadata format.

5. Permissionless adoption  
   Any agent or system may implement ASP without registration.

6. Protocol, not workflow  
   ASP defines data formats and semantics, not agent behavior or execution flow.

---

## 5. Artifact Metadata Structure

ASP standardizes artifact metadata, not artifact payloads.

The artifact payload itself (for example: a report, dataset, or document) is external to ASP and referenced by location.

### 5.1 Artifact Metadata Format

Example artifact metadata structure:

    {
      "artifact_id": "string",
      "task_type": "string",
      "input_hash": "string",
      "output_hash": "string",
      "created_at": 1735689600,
      "location": "string",
      "created_by": "string (optional)",
      "verification": {
        "method": "recompute | signature | zk-proof | other (optional)",
        "details": "object (optional)"
      }
    }

### 5.2 Field Descriptions

- artifact_id  
  A deterministic identifier for the artifact.  
  The exact method for generating this identifier is implementation-defined in v0.1.

- task_type  
  A short string describing the type of task performed  
  (for example: erc20_audit, research_summary, csv_transform).

- input_hash  
  A cryptographic hash of the task input.  
  The specific hash algorithm is implementation-defined but must be collision-resistant.

- output_hash  
  A cryptographic hash of the artifact payload.

- created_at  
  Unix timestamp indicating when the artifact was produced.

- location  
  A URI pointing to the artifact payload.  
  The payload itself is NOT part of the ASP message.

- created_by (optional)  
  An opaque identifier provided by the producing agent.  
  ASP does not define agent identity or authentication.

- verification (optional)  
  Metadata describing how the artifact may be verified.

---

## 6. Verification

ASP does not require trust between agents.

Verification is performed at the discretion of the consuming agent and may include:

- Recomputing the task using the same input
- Verifying digital signatures
- Validating cryptographic proofs
- Applying domain-specific validation logic

ASP does not guarantee correctness, completeness, or quality of artifacts.

---

## 7. Discovery and Reuse

ASP does not define how artifacts are discovered.

Agents MAY locate artifacts using any mechanism outside the scope of ASP, including:

- Search engines
- Repositories
- Peer-to-peer networks
- Local caches
- Private or public indexes

If an artifact is reused, the consuming agent is responsible for verification.

---

## 8. Storage

ASP does not define storage requirements.

Artifacts and metadata may be stored on:

- Git repositories
- IPFS or similar content-addressed systems
- Cloud object storage
- Local or private servers
- Any publicly or privately accessible location

Storage choice does not affect protocol compliance.

---

## 9. Example Use Case

Agent A audits an ERC20 smart contract and produces an audit report.

Agent A publishes an ASP artifact describing the completed audit and provides a location to the report.

Later, Agent B receives a request to audit the same contract.

Agent B MAY locate the existing artifact, verify its validity, and reuse the result instead of performing a full recomputation.

---

## 10. Versioning and Evolution

ASP uses semantic versioning:

- v0.x — Experimental drafts, subject to change
- v1.0 — Stable core protocol

Backward compatibility is not guaranteed during v0.x.

---

## 11. License

ASP is released under the MIT License.

Any individual, organization, or system may implement the protocol freely.
