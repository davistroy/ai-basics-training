# AI Practitioner Training Glossary

## A

**Agent** - An AI system that can autonomously perform multi-step tasks, make decisions, and interact with external tools without human intervention at each step.

**ASK-CONTEXT-CONSTRAINTS-EXAMPLE Framework** - Block 1 prompting methodology. ASK = clear request, CONTEXT = background information, CONSTRAINTS = limitations/requirements, EXAMPLE = desired output format.

## B

**Bulkhead Pattern** - Reliability pattern that isolates failures by partitioning system components, preventing cascading failures across the entire system.

## C

**Capstone** - End-of-block project demonstrating mastery of block skills. Required for certification.

**Checkpoint** - Inter-block assessment verifying readiness to proceed.

**Circuit Breaker Pattern** - Reliability pattern that prevents repeated calls to a failing service, allowing time for recovery before resuming normal operation.

**Context Window** - The maximum amount of text (measured in tokens) that an AI model can process in a single interaction, including both input and output.

## D

**Domain Memory** - Structured external memory for AI agents consisting of three pillars: Explicit Goals, Progress Records, and Operating Procedures.

## G

**Graceful Degradation** - Design approach where a system continues to function at reduced capacity rather than failing completely when components encounter errors.

## L

**LLM-as-Judge Pattern** - Quality evaluation technique where an AI evaluates another AI's output against defined criteria.

## M

**MCP (Model Context Protocol)** - Protocol enabling AI assistants like Claude to access external resources (files, databases, APIs) through configured servers.

**Micro-Agent Pattern** - Design pattern using small, focused agents (3-20 steps) within deterministic workflows.

## O

**Orchestration** - Coordination of multiple agents or workflow steps to accomplish complex tasks.

## Q

**Quality Gate** - Automated checkpoint in a workflow that evaluates output quality before proceeding.

**Quality Rubric** - Structured evaluation criteria with defined scoring (typically 1-5 scale).

## S

**Setup Agent** - In the Two-Agent Pattern, the agent responsible for preparing context, gathering resources, and configuring the environment before task execution.

## T

**Token** - The basic unit of text that AI models process. Roughly 4 characters or 0.75 words in English. Used to measure context window size and API costs.

**Two-Agent Pattern** - Core Block 3 architecture using an Executor agent (performs tasks) and Evaluator agent (assesses quality).

## W

**Worker Agent** - In the Two-Agent Pattern, the agent that executes the core task, operating within the context prepared by the Setup Agent.

**Workflow** - Multi-step automated process connecting AI operations with triggers, conditions, and outputs.
