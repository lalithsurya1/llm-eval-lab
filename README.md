# llm-eval-lab
Custom evaluation framework to analyze failure modes in large language models beyond standard benchmarks.

Motivation

Large language models are commonly evaluated using benchmarks that focus on final answer accuracy. While these benchmarks are useful, they often fail to capture how models behave in realistic, real-world scenarios.

In practical use, LLMs are expected to follow instructions, reason over multiple steps, handle uncertainty, and avoid fabricating information. A model that gives a correct answer for the wrong reasons, or that fails silently under ambiguity, can be unreliable or even harmful in real systems.

This project is motivated by the gap between benchmark performance and real-world reliability. Instead of asking “Did the model get the answer right?”, we focus on “Did the model behave correctly?”.

The goal is to evaluate LLMs based on behavioral robustness rather than surface-level accuracy.

What This Project Studies

This project studies three common failure modes observed in large language models during real-world use.

Instruction Drift

Instruction drift occurs when a model gradually deviates from the original user instruction. This can happen in longer conversations or multi-step tasks, where the model subtly changes the goal, ignores constraints, or introduces its own assumptions.

In real applications, instruction drift can cause models to produce outputs that look reasonable but do not actually satisfy the user’s intent.

Multi-step Reasoning Failure

Multi-step reasoning failure happens when a model starts a task correctly but breaks down partway through a reasoning chain. The model may make an early mistake, lose track of intermediate steps, or jump to an incorrect conclusion.

These failures are especially problematic in tasks that require planning, step-by-step logic, or decision-making, where partial correctness is not sufficient.

Hallucination under Ambiguity

Hallucination under ambiguity occurs when a model is given incomplete or underspecified information and responds by inventing details instead of asking for clarification or acknowledging uncertainty.

In real-world systems, this behavior can lead to confidently incorrect outputs, which is often worse than refusing to answer or requesting more information.

This project designs custom tasks to expose these failure modes and evaluates how different language models behave under such conditions. The emphasis is on understanding why failures occur and how they can be detected, rather than optimizing models for benchmark scores.
