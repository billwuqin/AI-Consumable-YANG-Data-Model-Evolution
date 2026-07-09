# AI Consumable YANG Data Model Evolution (ACTION) Work

This page provides a short description of a proposed IETF ACTION work. The ACTION work will explore how to make IETF developed YANG AI ready and better consumed
by AI Agent and Large AI Models.
The intention of this page is to capture the scope of the ACTION work that the proponents believes is in IETF scope and needs special attention.
Our expection is that Area Directors will help us dispatch this to a place to do the work:

- an existing working group
- a new working group

## Background

Network management has evolved towards model-driven programmability using YANG (RFC 7950). While YANG provides a deterministic human readable structure for data, it was designed for
deterministic software clients rather than the probabilistic reasoning of Large Language Models (LLMs). Consequently, when LLMs Consume YANG Data Models,e.g., tools use LLMs to
translate legacy CLI scripts into IETF-compliant YANG data payloads or generate Python scripts utilizing libraries like pyang or the model acts as an agent, converting a user’s
high-level natural language intent ("Set up a secure loopback interface") into structural XML/JSON payloads that match the exact syntax specified by the YANG file, AI agents are
often struggling with logical reasoning to navigate complex YANG hierarchies across independent nodes with numerous import, include, augment, when, must and feature statements,
which might leads to incorrect configuration logic.

The emerging Model Context Protocol (MCP) provides a framework for connecting Large AI models to external tools and data. However, there is currently no standardized way
to make YANG primitives (e.g., ontology, constraints, context, semantics) easily consumed by MCP components (Resources, Tools, and Prompts). the challenges of consuming raw YANG models in LLM-based agentic loops include:

- Semantic Ambiguity: LLMs lack the contextual hints needed to understand the operational impact of specific YANG nodes.

- Interoperability Barriers: AI agents require customized "glue code" for every vendor's unique interpretation of how a YANG model should be exposed to an AI.

- Scaling Issues: Massive YANG schemas exceed LLM context windows, requiring standardized methods for YANG schema registration and discovery.

## Goals

The primary goal of the ACTION Initiative is to provide operational guidance to make IETF YANG models "AI-ready." This includes defining a
standardized framework for mapping between YANG data structures and AI-native MCP interfaces to enable autonomous network operations.
The ACTION Initiative can be tasked with the following goals:

- YANG tools for AI:  Refactoring YANG-based network operations into AI-invocable tools using the Model Context Protocol (MCP) or Defining how YANG Data Nodes map to
  MCP URIs (Resources) and how RPC and Action statements map to MCP Tool schemas.

- Semantic Metadata: Utilizing YANG Model to provide the Metadata related to Context or Constraint information required by LLMs.

- Token Efficient Encoding: Development of a token-efficient YANG serialization mechanism tailored to agentic consumption.

- Declarative Intent/Policy Overlay: Overlay ontology model encapsulated with invariants, business constraints, and dynamic behavioral policies.

Protocol changes or extensions to the YANG language itself remain the responsibility of the NETCONF WG and NETMOD WG respectively.
