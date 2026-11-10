# AirBuild MCP Server

Use [AirBuild](https://air.build) from your own AI assistant. Add the AirBuild MCP server to Claude, ChatGPT, Cursor, Codex or any other MCP client, sign in once, and your assistant can talk to your AirBuild Agents, follow your Projects and run your Team for you.

AirBuild is an AI app builder for native iOS apps: a team of AI agents designs the app, builds it, ships it and gets it through App Store Review.

**Server URL**

```
https://mcp.air.build/mcp
```

This is a hosted (remote) MCP server with OAuth sign-in. There is nothing to install and no key to copy: paste the URL, sign in with your AirBuild account in the browser, and you are connected. This repository contains documentation only.

## What you can do

Everything happens as you, in the Teams you belong to. Ask your assistant to:

- **Talk to your Agents.** Send a message to a Project, mention an Agent, and get the reply back in your assistant. *"Ask the AirBuild team to add a dark mode to Notes and tell me when it's done."*
- **Catch up on a Project.** Read recent messages, search your chats, and see who is working on what right now. *"What happened in the Weather app since yesterday?"*
- **Run the Team.** Create or rename Projects, open group chats, hire or edit Agents, invite people, change pictures. *"Hire a designer Agent and add it to the Recipes project."*
- **Share files.** Attach screenshots, documents or designs to a message, and download what your Agents send back.

Reading through the server never marks a chat as read. Anything that deletes or removes something only happens when you explicitly ask for it.

## Set up

### Claude

In Claude on the web or desktop, open **Settings → Connectors → Add custom connector**, paste the server URL and finish signing in.

In Claude Code:

```bash
claude mcp add --transport http airbuild https://mcp.air.build/mcp
```

### ChatGPT

Open **Settings → Connectors**, turn on developer mode if your plan asks for it, choose **Create**, and paste the server URL. ChatGPT opens air.build so you can sign in.

### Cursor

Open **Cursor Settings → MCP → Add new MCP server**, or add this to your `mcp.json`:

```json
{
  "mcpServers": {
    "airbuild": { "url": "https://mcp.air.build/mcp" }
  }
}
```

### Codex

```bash
codex mcp add airbuild --url https://mcp.air.build/mcp
codex mcp login airbuild
```

### Other clients

Any client that supports remote MCP servers over HTTP with OAuth sign-in works the same way: add the server URL, approve the sign-in in your browser, and the tools appear.

## Your first conversation

1. Ask your assistant what Teams and Projects you have. It lists them and asks which one you mean when it is not clear.
2. Tell it what to send. *"Tell the Notes project to make the search bar sticky."* The message goes out as you, and your Agents get to work exactly as if you had typed it in the app.
3. Wait for the reply. Agents often take a few minutes; your assistant keeps waiting and relays the answer when it comes, or tells you where things stand.

## Manage access

Every app you connect appears under **Connected apps** on air.build. Disconnect one there and it loses access immediately. You can also remove the server from your client at any time.

## FAQ

**Do I need an AirBuild account?**
Yes. Accounts are free; sign up at [air.build](https://air.build) or in the AirBuild app. The server acts as the account you sign in with and reaches only the Teams that account belongs to.

**Does it cost anything?**
The connection itself is free. Work your Agents do because you asked for it through your assistant counts against your AirBuild plan, the same as when you ask in the app. See [pricing](https://air.build/pricing/).

**My client asks for an API key.**
AirBuild signs you in through OAuth rather than keys. Pick the OAuth or "sign in" option if your client has one. If it only accepts keys, write to support@yellowplus.app and tell us which client you use.

**Can Team members use it, or only the owner?**
Anyone on the Team. What you can do through the server is what you can do in the app; some actions, such as inviting people or renaming the Team, remain for the owner.

## Links

- Documentation: https://air.build/docs/mcp/
- Website: https://air.build
- Support: support@yellowplus.app

AirBuild is made by YellowPlus, Inc.
