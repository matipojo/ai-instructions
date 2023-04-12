# AI Instructions

With the rise of AI code assistants, it is important that an AI assistant will be able to complete tasks with accuracy and efficiency.

But using the code itself as a prompt is not enough, because the code is context less and it miss the big picture.

Additionally, with new approaches like the [AutoGPT](), their can be multiple AI agents that can work on the same project.

So they must have some context and instruction on what is matter, and what they should avoid.

To achieve this goal, this proposal suggests creating a folder with AI instructions that can be used by AI assistants in their prompts behind the scenes.

## .ai_instructions Structure

The structure of the instructions is as follows:

- .ai_instructions
  - project.md - instructions for the project
  - mission.md - instructions for the mission
  - persona.md - description of the AI persona
  - technical.md - technical details like the programming language, framework, entities, DB, etc.
  - user-experience.md - user experience details like accessibility, performance, etc.
  - people.md - people involved in the project that an AI agent may contact
  - dont.md - things that an AI agent should not do

.env.ai - A file with environment variables that can be used by the AI agent. like API tokens, etc.
- ACT_AS_AGENT={Current AI agent name} (which agent instructions to use `dev` or `qa`)
- TASK_MANAGEMENT={Your task manager}
- TASK_MANAGEMENT_TOKEN={Your API token}
- COMMUNICATION=Slack
- COMMUNICATION_USER=@ai_assistant
- COMMUNICATION_TOKEN={Your Slack token}

## Goal
 
The goal is to be a standard for AI instructions that can be used by AI assistants in following way

## Run multiple AI agents

```shell
$ EXPORT ACT_AS_AGENT=dev && <run command>
$ EXPORT ACT_AS_AGENT=qa && <run command>
```

## Feedback
Most of the instructions were written by AI ;)

Please provide feedback in a form of a pull request or an issue.
