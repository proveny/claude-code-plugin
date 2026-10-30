# Proveny for Claude Code

Make short video ads of your products from Claude Code with [Proveny](https://proveny.ai). The
plugin adds the Proveny MCP server and a skill that guides Claude through a video: who you sell to,
one sell angle, the length, the script, the price, then the render.

## Install

```bash
claude plugin marketplace add proveny/claude-code-plugin
claude plugin install proveny@proveny
```

Then restart Claude Code, run `/mcp`, select `proveny` and choose **Authenticate**. Your browser
opens Proveny; sign in if you need to and allow Claude Code for your workspace.

Your workspace needs Proveny's MCP access. You can find the setup in Proveny under
**MCP** (left menu).

## Use another Proveny server

The plugin connects to `https://api.proveny.ai/mcp`. To connect to another Proveny server (for
example a test server), copy its **Server URL** from **MCP** (left menu) on that server and
add it by hand:

```bash
claude mcp add --transport http proveny-test <Server URL>
```

Then run `/mcp`, select `proveny-test` and choose **Authenticate**.

## What it can do

- Read your products and their sell angles.
- Write the script with you, for one sell angle at a time.
- Show the price in Credits and wait for your yes before it spends any.
- Render the video, or remix your existing footage, and tell you when it is ready.

## Disconnect

In Proveny, open **MCP** (left menu) and click **Disconnect** next to Claude Code.
