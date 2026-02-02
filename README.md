# ASP — Agent Sharing Protocol

**ASP is an open, minimal protocol that allows AI agents to share completed work results as reusable artifacts.**

AI agents should not redo work that another agent has already completed.

Instead of sharing abilities or skills, agents using ASP share **verifiable outcomes** — audits, analyses, research, reasoning results, and structured computation outputs — so other agents can reuse them without recomputing the original task.

ASP is a protocol, not a platform.

---

## Why ASP Exists

Today, AI agents repeatedly perform the same kinds of work:

- Code audits on identical contracts
- Analysis of the same papers, datasets, or repositories
- Reasoning over identical problem statements
- Parsing and transforming the same structured inputs

Even when user prompts differ slightly, **large portions of the underlying work are identical or overlapping**.

This results in massive duplicated computation across agents, systems, and organizations.

ASP defines a shared language that allows agents to say:

> “This work has already been done.  
> Here is the result.  
> You can verify it and reuse it.”

---

## What ASP Is (and Is Not)

### ASP **is**
- An open protocol
- Permissionless and decentralized
- Focused on *results*, not capabilities
- Compatible with any agent architecture
- Storage-agnostic and infrastructure-neutral

### ASP **is not**
- A skill-sharing network
- An agent marketplace
- A hosting platform
- A centralized registry
- A monetization system
- A blockchain or token protocol

ASP does not coordinate agents.  
ASP does not manage identities.  
ASP does not enforce economics.

ASP only standardizes how **completed work results** are described, published, discovered, and verified.

---

## Core Concept: Artifacts

In ASP, agents share **artifacts**.

An artifact is a completed, self-contained work result produced by an agent after performing a task, such as:

- A smart contract audit report
- A static analysis result
- A research summary or literature review
- A data transformation output
- A reasoning trace or decision justification
- A structured JSON or CSV output

Artifacts are **outputs**, not behaviors.

ASP intentionally avoids sharing:
- Prompts
- Agent logic
- Internal chains of thought
- Skills or execution strategies

---

## How ASP Works (30 seconds)

1. An agent completes a task and produces a result
2. The agent publishes the result as an ASP artifact with a standardized descriptor
3. Other agents discover the artifact, verify it, and reuse the result instead of recomputing

Computation happens once.  
Reuse happens many times.

---

## Verification Over Trust

ASP does not require trust between agents.

Artifacts can be verified through:
- Recomputing the task
- Matching input/output hashes
- Digital signatures
- Cryptographic proofs (optional)

Each agent decides **its own verification threshold**.

ASP only defines the metadata needed to make verification possible.

---

## Storage and Discovery

ASP does not mandate where artifacts live.

Artifacts may be stored on:
- GitHub repositories
- IPFS or other content-addressed systems
- Cloud storage
- Public servers
- Local or private infrastructure

ASP standardizes **how artifacts are described**, not **where they are stored**.

Discovery mechanisms are intentionally left open to allow experimentation.

---

## Status

**Status: Early Draft (v0.1)**

ASP is an early-stage protocol proposal.

The specification is stable enough for experimentation but not finalized.

Breaking changes may occur as the protocol evolves.

---

## Who Should Care About ASP

ASP is relevant for:

- AI agent developers
- Autonomous agent frameworks
- Research automation systems
- Code analysis and auditing agents
- Organizations operating large fleets of agents
- Anyone interested in reducing redundant AI computation

You do **not** need to adopt ASP fully to experiment with it.

Partial, informal, or experimental implementations are encouraged.

---

## Getting Started

- Read the full protocol specification: **[SPEC.md](./SPEC.md)**
- Experiment with producing ASP-compatible artifacts
- Open issues or discussions to propose improvements
- Share feedback, critiques, or alternative designs

ASP grows through usage, not authority.

---

## Vision

ASP enables a future where AI agents build on top of each other’s completed work instead of repeatedly starting from zero.

Over time, this forms a distributed, verifiable layer of reusable intelligence across the AI ecosystem.

---

## License

ASP is released under the MIT License.

Anyone may implement, extend, or fork the protocol freely.
