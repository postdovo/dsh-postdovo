# dsh-postdovo

A [DeepSeek Harness](https://github.com/deepseek-ai/deepseek-harness) (`dsh`) plugin that connects the agent to [PostDovo](https://postdovo.com), so it can draft, schedule and publish social media posts on your connected accounts.

It is a configuration bundle: one row for DeepSeek Harness's built-in MCP client that points at PostDovo's remote MCP server, `https://app.postdovo.com/mcp`. It contains no code and ships no binaries.

## What the agent can do

- See your workspaces, connected social accounts and posts.
- Create a post for one account or several, with an optional title, first comment, picture or video that you provide.
- Plan several posts in one request; you see every date, time and text and approve once before anything is created.
- Schedule drafts for a time you choose, or take them back to drafts.
- Publish right away, but only after a preview of exactly what goes out where and your clear yes.

It cannot change a post that is already published.

## Install

In DeepSeek Harness, open the Plugins page in the sidebar, add a plugin and enter:

    github:postdovo/dsh-postdovo

Or from a terminal. The desktop app uses the profile `desktop`; if you start DeepSeek Harness with `npx @deepseek-ai/dsh web`, use `--profile web` instead:

    dsh plugin --profile desktop add "github:postdovo/dsh-postdovo"

## Give it a token

In PostDovo, open the **AI Agents** page, create a token under **Access tokens** and copy it (it is shown once). DeepSeek Harness reads it from the `POSTDOVO_TOKEN` environment variable when it starts, so set it in the terminal window you start DeepSeek Harness from.

**Mac app:** quit the app if it is open, then run both lines in Terminal. An app opened from the Dock or Launchpad does not see a variable exported in Terminal, so start it this way each time:

    export POSTDOVO_TOKEN=your-token
    "/Applications/DeepSeek Harness.app/Contents/MacOS/DeepSeek Harness"

**Without the app, or on Windows or Linux:** set the token and start DeepSeek Harness from the same terminal (needs Node.js):

    export POSTDOVO_TOKEN=your-token
    npx @deepseek-ai/dsh web

On Windows PowerShell use `$env:POSTDOVO_TOKEN = "your-token"` instead of `export`. Restart DeepSeek Harness after installing the plugin.

## Check it

PostDovo's tools appear as `mcp__postdovo__*`. Ask the agent: *"Which social accounts do I have connected in PostDovo?"*

Without a token the server answers 401 and no PostDovo tools are registered; DeepSeek Harness keeps starting.

## Control and privacy

The PostDovo account owner can switch drafts, scheduling and publishing on or off for assistants on the AI Agents page, and can delete the token there at any time. Publishing right away always shows a preview first and needs a clear yes. More about PostDovo, including its privacy policy: https://postdovo.com

## License

MIT, for the files in this repository. PostDovo itself is a hosted service.
