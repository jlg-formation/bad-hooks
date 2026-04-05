# Warning

After reading this repository and understanding how it works, you may never download a GitHub repository with the same sense of safety again.

# bad-hooks

## Overview

This repository demonstrates the security risk posed by project chat hooks.

Its purpose is simple: show that cloning or downloading a repository can be enough to expose a user to unintended code execution in a trusted development environment.

In this example, opening a GitHub Copilot chat in Visual Studio Code triggers a chat hook that executes a Windows script. The payload used here is intentionally harmless and only creates a file on the local machine, outside the Visual Studio Code workspace, but the same mechanism could be used to run genuinely malicious code.

## What Is a Chat Hook?

For background on chat hooks in the context of GitHub Copilot and Visual Studio Code, see the official documentation:

https://code.visualstudio.com/docs/copilot/customization/hooks

## Demonstration Scenario

This repository is designed to illustrate the following sequence:

1. A user clones or downloads the repository on a Windows machine.
2. The user opens the project in Visual Studio Code.
3. The user starts a GitHub Copilot chat.
4. A configured chat hook is invoked automatically.
5. The chat hook executes local code on the user's machine.

In this proof of concept, the script only creates a file outside the Visual Studio Code workspace as evidence of execution.

## Repository Purpose

The goal of this repository is educational. It exists to highlight that automation features integrated into developer tooling can create an unexpected trust boundary.

The central point is not the specific payload used here, but the fact that code execution can happen as a side effect of interacting with a repository in what appears to be a normal and safe workflow.

## Safety Notes

- This repository is for awareness and demonstration purposes only.
- It should not be used to deploy malicious behavior.
- You should review any chat hook-related configuration before trusting a repository.
- In particular, inspect directories such as `.github/hooks/` and `.git/hooks/` when assessing an unfamiliar project.
- **Important**: Individual users cannot deactivate Copilot chat hooks in VS Code, as chat hooks are enabled by default in workspace settings. The only way to disable them is through organization-managed VS Code installations, where administrators can enforce enterprise policies to block chat hook execution.
- **Temporary mitigation**: To reduce this vulnerability, install Windows policies (see https://code.visualstudio.com/docs/enterprise/policies) and disable chat hooks.

## Chat Hook Location

The demonstration script is located in `.github/hooks/`.

## Final Takeaway

If this repository makes one point clearly, it is this: downloading a repository should not automatically be treated as a safe action.
