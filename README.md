# Copilot code review plugin

**Code Review** reviews your local Git changes and combines feedback from multiple reviewers into one report.

## Run a review with Copilot CLI

Under **Assets** on the [latest release](https://github.com/github/copilot-code-review-plugin-dist/releases/latest), download `copilot-code-review-v<version>.zip`, not a **Source code** archive. Extract the ZIP and find `copilot-code-review/`, the folder containing `plugin.json`.

From the repository you want reviewed, load the plugin for this session. Replace the example path with the full path to the extracted folder:

```sh
copilot --plugin-dir "$HOME/Downloads/copilot-code-review" --agent code-review:main
```

With a change staged in that repository, ask:

> Review my staged changes with Lite effort.

A completed review lists findings with file and line references, or says the reviewers found no issues.
