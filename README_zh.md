# Claude Code 设置和命令 - 氛围编程

为增强开发工作流程而设计的 Claude Code 配置和自定义命令精选集合。此设置包括专门用于功能开发（Kiro 工作流程）、代码分析、GitHub 集成和知识管理的命令。

[AI软件工程](https://www.wxyaonline.top/article/2353459e-7dca-8092-9384-ce0f495e97d2)

## 中文文档说明

本目录包含所有命令文件的中文翻译版本，旨在为中文开发者提供更好的使用体验。所有翻译都保持了原英文文档的结构和功能，同时适应了中文技术文档的表达习惯。

### 文档结构

- `commands/` - 命令文件的中文翻译
  - `cc/` - 代码协作相关命令
  - `gh/` - GitHub 集成相关命令
  - `kiro/` - Kiro 工作流程相关命令
  - `gm/` - 通用管理相关命令

### 使用建议

1. **首次使用**：建议先阅读本 README.md 了解整体架构
2. **命令查找**：根据需求在对应目录下查找相关命令
3. **双语对照**：可与英文原版对照使用，确保理解准确
4. **反馈改进**：如有翻译不准确或表达不清的地方，欢迎提出改进建议

## 设置

```sh

# 备份原始 claude 设置
mv ~/.claude ~/.claude.bak

# 克隆 claude-code-settings
git clone https://github.com/feiskyer/claude-code-settings.git ~/.claude

# 安装 GitHub Copilot API 代理
npm install -g copilot-api

# 下面内容按需使用，配置 放在 settings.json.bak 文件中，复制到 settings.json 中即可

# 授权你的 GitHub Copilot 账户
copilot-api auth

# 为了方便，使用 tmux 在后台运行 copilot-api
tmux new-session -d -s copilot 'copilot-api start'
```

> **注意：** 此配置通过 [copilot-api](https://github.com/ericc-ch/copilot-api) 代理使用 GitHub Copilot 作为 Claude Code 模型提供者。

## 命令

### 开发工作流程

**Kiro 工作流程** - 从规范到执行的完整功能开发。Kiro 命令为功能开发提供结构化工作流程：

1. `/kiro:spec [功能]` - 创建需求和验收标准
2. `/kiro:design [功能]` - 开发架构和组件设计
3. `/kiro:task [功能]` - 生成实施任务列表
4. `/kiro:execute [任务]` - 执行特定实施任务
5. `/kiro:vibe [问题]` - 快速开发协助

### 分析与反思

- `/think-harder [问题]` - 增强分析思维
- `/think-ultra [复杂问题]` - 超全面分析
- `/reflection` - 分析和改进 Claude Code 指令
- `/reflection-harder` - 全面会话分析和学习
- `/eureka [突破]` - 记录技术突破

### GitHub 集成

- `/gh:review-pr [PR编号]` - 全面 PR 审查和评论
- `/gh:fix-issue [问题编号]` - 完整问题解决工作流程

### 文档与知识

- `/cc:create-command [名称] [描述]` - 创建新的 Claude Code 命令

## 指导文档

- [使用 GitHub Copilot 作为模型提供者的 Claude Code](guidances/github-copilot.md)

## 许可证

本项目基于 MIT 许可证发布 - 详情请参见 [LICENSE](LICENSE)。
