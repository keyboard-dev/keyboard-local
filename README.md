# Keyboard

**Connect your AI to your apps—securely run code, automate tasks, and stay in control.**

[![Docs](https://img.shields.io/badge/docs-keyboard.dev-blue)](https://docs.keyboard.dev/) [![License](https://img.shields.io/badge/license-Apache%202.0-green)](LICENSE) [![Discord](https://img.shields.io/badge/discord-join-7289da)](https://discord.gg/UxsRWtV6M2)

## What is Keyboard?

Keyboard is a universal Model Context Protocol (MCP) server allowing you to connect all your apps to your favorite AI client, like Claude. It provides a flexible and secure platform for connecting your internal applications to your AI client and executing complex tasks across various domains via direct code execution and task automation.

## 🚀 Quick Demo

Below is a quick demo of Claude creating an online survey through Keyboard using the Typeform API.

<img src="https://raw.githubusercontent.com/keyboard-dev/keyboard-local/main/Gif4readme.gif" width="1000">

See the full demo [here](https://app.supademo.com/demo/cmd6bnb3t5xwac4kjx91usuv3)

## How does it work

### How it works in 3 steps:

1. **Ask Claude** to execute a task using your connected tools
2. **Review & approve** the generated code in the desktop app
3. **Watch it execute** safely in your own GitHub Codespace

```mermaid
flowchart LR
    A[📱 Claude Request] -->|"Send email via Gmail"| B[🔍 Keyboard Generates Code]
    B -->|📋 Shows preview| C[✅ You approve/reject]
    C -->|✅ Approved| D[☁️ Executes in Codespace]
    D -->|📊 Results| A
```

### Full breakdown

Keyboard’s MCP server enables remote code execution in a GitHub codespace tied to your GitHub account that can then execute tasks in the connected apps via their APIs. When you ask your AI Client to have Keyboard  to execute a task for you, Keyboard spins up a codespace and writes a node.js script to execute that task for you. The AI Client will walk you through the steps it’s taking and you have the ability to approve any code before it gets executed in the AI Client on your behalf. Once the code is executed you then have the option accept or reject sending the response back to a MCP client like Claude to better ensure your privacy.

## When should I use Keyboard?

When you want your AI Client (Claude, ChatGPT, etc.) to execute tasks on your behalf. Connect your tools to your own secure GitHub Codespace, ask Claude to execute something in one of them and watch Keyboard go to work. With Keyboard, you don’t need to install an MCP server for each app or service you’d like to connect to your AI Client. Instead, any app with an API key can be connected to Keyboard while giving you control to approve or deny the actions.

## Key Features

- **Connect Your Tools:** One MCP, all your tools. Provide Keyboard access to third party tools in your own GitHub environment.
- **Private:** Keyboard doesn't have access to your API keys, it only has access to the GitHub Codespace.
- **Secure Workflows:** Run code safely within your own controlled environment with human oriented approval workflows.
- **Human Control:** You approve what code is executed, you also approve what data is sent is back to MCP clients like Claude.

## Getting Started

Keyboard is available to use today for free. If you want to use Keyboard see the [quickstart](https://docs.keyboard.dev/docs/quickstart) guide to get started quickly. 

### Documentation

Full docs can be found at https://docs.keyboard.dev/ but see below for direct links to a few docs that will help you use Keyboard after you get set up:

* [Learn how to connect your third party apps](https://docs.keyboard.dev/docs/third-party-apps)
* [Tips for using Keyboard with Claude](https://docs.keyboard.dev/docs/usability-tips-with-claude)

### Run & Contribute to Keyboard

If you want to run the whole codebase and contribute to both the MCP server and the desktop client see the instructions below.

1️⃣ Clone the monorepo (with submodules)

```bash
git clone --recursive https://github.com/keyboard-dev/keyboard-local.git
cd keyboard-local
```

2️⃣ Start Approver Client (Electron Desktop App)

```bash
cd apps/approver-client
git checkout main
git pull origin main
npm install && npm run dev
```

3️⃣ Start Keyboard MCP Server

In a separate terminal:

```bash
cd apps/keyboard-mcp
git checkout main
git pull origin main
npm install && npm run build
```

## 🔥 Important: How to Contribute

✅ DO THIS:

* Make changes in apps/approver-client/ or apps/keyboard-mcp/
* Create branches and commits like normal
* Submit PRs to the individual repos:

Approver Client changes → https://github.com/keyboard-dev/approver-client

Keyboard MCP changes → https://github.com/keyboard-dev/keyboard-mcp

❌ DON'T DO THIS:

* Don't submit PRs to this monorepo (unless changing this README)
* Don't worry about "updating submodules" - handled automatically

That's It! Work like you normally would. This repo just saves you from cloning multiple repositories.

---

## ⚠️ Disclaimer

**Use at your own risk.** Keyboard is experimental software that executes code in your GitHub Codspace environment. While we've designed it with security in mind, you should:

- Review all code before approving execution
- Only connect trusted applications
- Understand that API calls may have real-world effects
- Use in non-production environments initially

This software is provided "as is" without warranty of any kind, express or implied.

---

**⭐ If Keyboard helps you work more securely with AI, please give us a star!**

Join our [Discord](https://discord.gg/UxsRWtV6M2) if you have any questions. We'd love to hear from you.

*Built with ❤️ by the Keyboard team*
