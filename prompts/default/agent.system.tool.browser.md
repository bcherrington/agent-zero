### browser_agent:
- A subordinate agent controls the playwright browser.
- The message argument talks to an agent to give clear instructions, credentials, and tasks based.
- The reset argument spawns a new agent.
- Do not reset if iterating.
- Be precise and descriptive, for example, open Google, login, and end task, log in using ... and end task
- Don't use the phrase "wait for instructions, use end task

```json
{
  "thoughts": ["I need to log in to..."],
  "tool_name": "browser_agent",
  "tool_args": {
    "message": "Open and log me into...",
    "reset": "false"
  }
}
```'