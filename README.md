[![TestBuild](https://github.com/Naturalclar/issue-action/workflows/test/badge.svg)](https://github.com/Naturalclar/issue-action) [![Assign](https://github.com/Naturalclar/issue-action/workflows/assign/badge.svg)](https://github.com/Naturalclar/issue-action) [![Label](https://github.com/Naturalclar/issue-action/workflows/label/badge.svg)](https://github.com/Naturalclar/issue-action)

# Issue Action

Github action for automatically adding label or setting assignee when a new Issue is opened.

## Usage

### Assignee

Automatically assign `@username` when Issue title or body contains "test"

```yaml
name: "Set Assignee"
on:
  issues:
    types: [opened]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: naturalclar/issue-action
        with:
          keywords: "test"
          action: "assign username"
          github-token: "${{ secrets.GITHUB_TOKEN }}"
```

### Label

Automatically set `HELP` label when Issue title or body contains `help` or `wanted`

```yaml
name: "Set Issue Label"
on:
  issues:
    types: [opened]

jobs:
  test:
    runs-on: ubuntu-latest
    steps:
      - uses: naturalclar/issue-action
        with:
          keywords: "help wanted"
          action: "label HELP"
          github-token: "${{ secrets.GITHUB_TOKEN }}"
```
