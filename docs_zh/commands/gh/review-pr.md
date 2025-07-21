---
description: 审查 GitHub 拉取请求，提供详细的代码分析
argument-hint: [pr编号]
allowed-tools: Write, Read, LS, Glob, Grep, Bash(gh:*), Bash(git:*)
---

# 审查 PR

你是一位专家代码审查员。按照以下步骤审查 GitHub PR $ARGUMENTS：

1. 如果参数中没有提供 PR 编号，使用 Bash(`gh pr list`) 显示开放的 PR
2. 如果提供了 PR 编号，使用 Bash(`gh pr view $ARGUMENTS`) 获取 PR 详情
3. 使用 Bash(`gh pr diff $ARGUMENTS`) 获取差异
4. 分析更改并提供彻底的代码审查，包括：
    - PR 功能的概述
    - 代码质量和风格分析
    - 改进的具体建议
    - 任何潜在问题或风险
5. 提供代码审查评论，仅包含建议和必需的更改：
    - 不要评论 PR 做了什么或总结 PR 内容
    - 仅专注于建议、代码更改和潜在问题及风险
    - 使用 Bash(`gh api repos/OWNER/REPO/pulls/PR_NUMBER/comments`) 发布你的审查评论

保持你的审查简洁但彻底。专注于：

- 代码正确性
- 遵循项目约定
- 性能影响
- 测试覆盖
- 安全考虑

用清晰的章节和要点格式化你的审查。

## gh 命令参考

```sh
# 列出 PR
gh pr list

# 查看 PR 描述
gh pr view 78

# 查看 PR 代码更改
gh pr diff 78

# 审查评论应发布到更改的文件
gh api repos/OWNER/REPO/pulls/PR_NUMBER/comments \
    --method POST \
    --field body="[你的评论]" \
    --field commit_id="[commitID]" \
    --field path="path/to/file" \
    --field line=lineNumber \
    --field side="RIGHT"

# 获取 commitID 的示例命令
gh api repos/OWNER/REPO/pulls/PR_NUMBER --jq '.head.sha'
``` 