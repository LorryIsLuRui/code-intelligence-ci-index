# code-intelligence-ci-index

可发布到 GitHub Marketplace 的 Action 已准备好：

- `action.yml`：Marketplace 入口（仓库根目录）
- `intelligence-code/.github/actions/run-increase-index/action.yml`：具体执行逻辑

## 使用方式

```yaml
name: Run increase index

on:
  workflow_dispatch:

jobs:
  run:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4
      - name: Run increase index action
        uses: LorryIsLuRui/code-intelligence-ci-index@v1
        with:
          increase-command: ./scripts/increase-index.sh
          working-directory: .
```

## 发布到 Marketplace

1. 保持仓库为 **Public**。
2. 在默认分支保留根目录 `action.yml`（已完成）。
3. 创建并推送语义化标签（例如 `v1.0.0`），并额外维护主版本标签（例如 `v1`）。
4. 在仓库页面进入 **Releases** 创建 release（可使用刚才的 tag）。
5. 在仓库右侧或设置中进入 **GitHub Marketplace**，按页面向导发布该 Action。
