# 项目文件结构

[English](project-structure.md) | [简体中文](project-structure.zh-CN.md)

```text
final-state-delivery/
├── AGENTS.md                         # 英文版项目级最终状态交付规范
├── README.md                         # 英文 GitHub 主页
├── README.zh-CN.md                   # 中文 GitHub 主页
├── .gitignore                        # 本地文件和生成文件排除规则
├── case-materials/
│   ├── README.md                      # 英文来源、隐私和版权说明
│   ├── README.zh-CN.md                # 中文来源、隐私和版权说明
│   ├── provided-discussion.md         # 用户提供讨论的英文综合
│   └── provided-discussion.zh-CN.md   # 用户提供讨论的中文综合和原帖链接
├── docs/
│   ├── README.md / README.zh-CN.md    # 文档导航
│   ├── project-structure.md           # 英文文件结构说明
│   ├── project-structure.zh-CN.md     # 中文文件结构说明
│   ├── problem-statement.md / .zh-CN.md # 问题定义
│   ├── llm-analysis.md / .zh-CN.md    # LLM 与上下文分析
│   ├── vibe-coding-analysis.md / .zh-CN.md # Vibe Coding 分析
│   ├── anti-patterns.md / .zh-CN.md   # 反模式
│   ├── best-practices.md / .zh-CN.md  # 最佳实践
│   ├── agent-adapters.md / .zh-CN.md  # 工具适配
│   ├── evaluation.md / .zh-CN.md      # 评估和验收
│   ├── references.md / .zh-CN.md      # 参考资料
│   └── examples/
│       ├── tomato-egg.md / .zh-CN.md  # 核心案例
│       ├── feature-removal.md / .zh-CN.md # 删除功能案例
│       └── scope-boundary.md / .zh-CN.md # 作用域案例
└── templates/
    ├── AGENTS.md                      # 英文可复制规范
    ├── AGENTS.zh-CN.md                # 中文解释版本
    ├── task-spec.md / .zh-CN.md       # 任务规格模板
    └── pr-template.md / .zh-CN.md     # PR 模板
```

## 文件职责

- `AGENTS.md` 和 `templates/AGENTS.md` 是规范来源。
- `README.md` 和 `README.zh-CN.md` 是双语项目入口。
- 每个说明性 Markdown 文件都有对应的 `.zh-CN.md` 中文版本。
- `AGENTS.md` 保持英文；`templates/AGENTS.zh-CN.md` 仅用于中文理解，不是规范来源。
- `docs/` 保存问题分析、案例、工具适配、评估和参考资料。
- `case-materials/` 保存来源材料，不会自动变成项目规范。
- `templates/` 保存可复制到其他 AI 编程项目的模板。
