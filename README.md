# Copilot code review plugin

Use **Code Review** to review local Git changes. You can download the plugin without signing in. To run a review, sign in to your client with an account that has Copilot access.

## Get the plugin for CLI or VS Code

From the [latest release](https://github.com/github/copilot-code-review-plugin-dist/releases/latest), download `copilot-code-review-v<version>.zip` under **Assets**, not either **Source code** archive. Extract the ZIP and locate `copilot-code-review/`, the folder containing `plugin.json`.

### Copilot CLI: load it for one session

Start [Copilot CLI](https://docs.github.com/en/copilot/how-tos/copilot-cli/set-up-copilot-cli/install-copilot-cli) **from the repository you want reviewed**, not the plugin folder. Pass the full path to the folder containing `plugin.json`; this example assumes it's directly under Downloads:

```sh
copilot --plugin-dir "$HOME/Downloads/copilot-code-review" --agent code-review:main
```

This loads the plugin for one session without installing it. Use `/login` if prompted, then `/agent` to confirm **Code Review** before [your first review](#run-your-first-review).

### VS Code: install from the extracted folder

1. Open your repository in a trusted workspace where agent plugins are allowed. Select **Copilot** as the session target.
2. Run **Chat: Open Customizations**. Under **Plugins**, use **+** to [install from source](https://code.visualstudio.com/docs/agent-customization/agent-plugins#_install-a-plugin-from-source), or run **Chat: Install Plugin from Source** from the Command Palette. Enter the extracted folder's full path.
3. In a new Copilot chat in that workspace, select **Code Review** from the agent picker.

## GitHub Copilot desktop app: install from a marketplace

The [app installs plugins from marketplaces](https://docs.github.com/en/copilot/how-tos/github-copilot-app/customize-github-copilot-app#adding-plugins). Neither this repository nor the ZIP is a marketplace. If `code-review` isn't already installed and you don't have an approved marketplace that lists it, use the CLI or VS Code instead.

1. To install, open **Customize**. If needed, add the supplied marketplace's GitHub repository or Git URL using the settings beside the marketplace dropdown. Find `code-review` under **Browse** and select **Install**.
2. Under **Customize** > **Installed**, confirm `code-review` is enabled.
3. To review changes staged locally, [start a session](https://docs.github.com/en/copilot/how-tos/github-copilot-app/agent-sessions#starting-a-session) for your repository with **This computer** and **Current checkout** selected. Choose **Code Review** from the agent picker.

## Run your first review

In the checkout your session is using, stage a change and check that `git diff --staged --stat` lists it. Ask **Code Review**:

> Review my staged changes with Lite effort.

Look for findings with file and line references, or a report that the reviewers found no issues. "Nothing to review" means there were no staged changes, not that the review passed.
