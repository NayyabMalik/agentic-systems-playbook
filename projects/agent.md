# Deep Agents Project Context

## Workspace Focus

- Learn and prototype context engineering and Deep Agents.
- Build research assistants for Artificial Intelligence topics and papers.

## Current Notebook Conventions

- Create agents with the Python `deepagents.create_deep_agent` API.
- The example model is `openrouter:openai/gpt-4o-mini`.
- Load credentials from environment variables with `python-dotenv`.
- Expected environment variables include `OPENROUTER_API_KEY` and `TAVILY_API_KEY`.
- Never hard-code or print API key values.

## Research-Agent Guidance

- Identify the research question and break broad topics into focused tasks.
- Use subagents for independent research tasks when parallel work is useful.
- Prefer primary sources such as papers, official documentation, and announcements.
- Verify dates and distinguish published results from claims.
- Cite sources next to the claims they support. Do not invent citations or present uncertain information as established fact.
- Summarize papers by covering the problem, approach, key findings, limitations, and relevance to the question.
- Synthesize subagent findings, call out disagreements or evidence gaps, and avoid repeating the same result in multiple sections.

## Implementation Notes

- Keep prompts explicit about role, task, evidence standards, and output shape.
- Keep secrets in local environment configuration, not notebooks or source.
- When adding tools, confirm they are actually available to the agent before instructing it to use them.