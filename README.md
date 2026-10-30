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

In the DeepSeek Harness Web UI, open the Plugins page, choose **Install a third-party plugin** and enter:

    github:postdovo/dsh-postdovo

Or from a terminal:

    dsh plugin --profile web add "github:postdovo/dsh-postdovo"

Then give it a PostDovo access token. In PostDovo, open the **AI Agents** page, create a token under **Access tokens** and copy it (it is shown once). Export it before starting DeepSeek Harness:

    export POSTDOVO_TOKEN=your-token
    dsh web

On Windows PowerShell use `$env:POSTDOVO_TOKEN = "your-token"`. Restart the profile after installing.

## Check it

PostDovo's tools appear as `mcp__postdovo__*`. Ask the agent: *"Which social accounts do I have connected in PostDovo?"*

Without a token the server answers 401 and no PostDovo tools are registered; DeepSeek Harness keeps starting.

## Control and privacy

The PostDovo account owner can switch drafts, scheduling and publishing on or off for assistants on the AI Agents page, and can delete the token there at any time. Publishing right away always shows a preview first and needs a clear yes. More about PostDovo, including its privacy policy: https://postdovo.com

## License

MIT, for the files in this repository. PostDovo itself is a hosted service.
