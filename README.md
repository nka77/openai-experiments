# agentic-experiments

# OpenAI API vs LangChain for LLM-based Agent System

## 1. Initial Approach: Direct OpenAI API

I initially implemented the system by calling the OpenAI API directly. This involved:

- Writing system and user prompts manually.
- Handling structured outputs via `function_call` parameters.
- Manually orchestrating multiple steps and agents.
- Executing tools (e.g., data preprocessing, analysis, visualization) in Python and passing outputs back to the model.

### Pros of Using Direct OpenAI API

- **Full Control:** Complete flexibility over prompts, function calls, and response formatting.
- **Lightweight:** Minimal external dependencies.
- **Immediate Access:** No abstraction layer, so the latest OpenAI features are available instantly.

### Cons of Using Direct OpenAI API

- **Manual Orchestration:** Managing multi-step pipelines and multiple agents required a lot of custom code.
- **Complex Error Handling:** Needed to handle retries, invalid outputs, and function call validation manually.
- **Scalability Challenges:** Harder to maintain as the number of agents or tools grew.
- **Limited Reusability:** Functions and prompts were tightly coupled to the workflow, making future modifications tedious.

---

## 2. Transition to LangChain

To address the challenges above, I switched to **LangChain**, which provides:

- Prebuilt abstractions for **agents, tools, and chains**.
- Built-in support for **structured outputs** and function calls.
- Easier orchestration of multi-step pipelines.
- Integration with external data sources and persistent memory.

### Benefits Observed After Switching

- **Modular Agent Architecture:** Each agent (preprocessing, analysis, visualization) could be defined independently and reused easily.
- **Cleaner Orchestration:** LangChain handled agent routing, tool execution, and chaining of steps.
- **Improved Maintainability:** Changes to prompts, tools, or agent logic no longer required refactoring the entire workflow.
- **Integration-Friendly:** Easy to connect to databases, vector stores, or document stores like LlamaIndex for retrieval-augmented generation.

### Summary

Switching from **direct OpenAI API calls** to **LangChain** significantly improved:

- Maintainability of multi-agent workflows.
- Reusability of tools and agents.
- Ease of debugging and extending the system.
- Integration with structured data sources and persistent memory.

Overall, LangChain provided the **right balance between flexibility and abstraction** for building a scalable, production-ready LLM-based agent system.
