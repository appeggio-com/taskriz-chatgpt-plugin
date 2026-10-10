# Taskriz for ChatGPT

A ChatGPT plugin that lets ChatGPT send a person a request through
[Taskriz](https://www.taskriz.com): an interface they answer in the Taskriz app, a browser or
by email. ChatGPT then reads their answer and carries on.

It connects ChatGPT to the hosted Taskriz MCP server (signing in with OAuth) and adds a skill
for the request and reply loop. It's packaged in OpenAI's portable plugin format
([Package your plugin](https://developers.openai.com/plugins/build/plugins)).

## Install

**ChatGPT desktop app (Work mode or Codex) and the Codex CLI.** This repository is a plugin
marketplace. Add it:

```
codex plugin marketplace add appeggio-com/taskriz-chatgpt-plugin
```

Restart the ChatGPT desktop app, open the Plugins Directory, choose the **Taskriz**
marketplace and install the plugin. You sign in to your Taskriz account when it's installed.

**A ChatGPT workspace.** A workspace admin can publish the installed plugin to the workspace
(Plugins → Personal → the plugin's ⋯ menu → Publish), choosing which roles get it. It stays
inside the workspace; it isn't added to the public Plugins Directory.

You need a Taskriz account.

## Contents

- `.agents/plugins/marketplace.json`: the marketplace, listing one plugin.
- `plugins/taskriz/plugin.json`: the plugin manifest.
- `plugins/taskriz/mcp.json`: the Taskriz MCP server (currently `https://dev.taskriz.com/mcp`),
  signing in with OAuth (dynamic client registration).
- `plugins/taskriz/skills/taskriz/SKILL.md`: when and how ChatGPT uses it.
