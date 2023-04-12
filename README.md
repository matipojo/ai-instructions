# AI Instructions

With the rise of AI code assistants, it is important that they are able to complete tasks accurately and efficiently. However, using the code alone as a prompt is insufficient as it lacks context and the big picture. 

Additionally, with new approaches like AutoGPT, multiple AI agents may be working on the same project, requiring context and guidance on what matters and what to avoid.

To address this, the proposal is creating a folder of AI instructions that can be used by AI assistants as prompts behind the scenes.

## .ai_instructions Structure

The structure of the instructions is as follows:

### .ai_instructions
  - project.md - Instructions for the project
  - persona.md - Description of the AI persona (for all agents)
  - technical.md - Technical details like the framework, DB, entities, etc.
  - user-experience.md - User experience details like accessibility, performance, etc.
  - people.md - People involved in the project that an AI agent may contact
  - dont.md - Things that an AI agent should not do
  - agent-[name].md - Instructions for a specific AI agent (with multiple files, e.g. dev, qa, etc.)

### .env.ai

A file with environment variables that can be used by the AI agent, like API tokens, etc.
  - ACT_AS_AGENT={Current AI agent name} (which agent instructions to use, `dev` or `qa`)
  - TASK_MANAGEMENT={Your task manager}
  - TASK_MANAGEMENT_TOKEN={Your API token}

### .env.ai.[agent name]
  - COMMUNICATION=Slack
  - COMMUNICATION_USER=@ai_assistant
  - COMMUNICATION_TOKEN={Your Slack token}

### /folder/.ai_instructions

Each folder can have its own set of instructions. This is useful for projects with multiple components, like a frontend and backend.

## Goal

The goal is to establish a standard for AI instructions that can be used by AI assistants.

## Running Multiple AI Agents

```shell
$ EXPORT ACT_AS_AGENT=dev && <run command>
$ EXPORT ACT_AS_AGENT=qa && <run command>

```

## Feedback
Most of the instructions were written by AI ;)

I would love to hear your thoughts and suggestions. 
Please submit any feedback via pull request or issue.
