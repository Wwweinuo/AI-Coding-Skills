# AI-Coding-Skills

AI Coding Skills 是一组可复用的 Agent Skill 集合，为 AI 编码助手提供专业化能力扩展。每个 Skill 以独立目录的形式组织，包含完整的配置、说明和依赖信息。

## 项目结构

```
AI-Coding-Skills/
└── Skills/
    ├── document-converter/
    │   ├── SKILL.md        # Skill 定义与使用说明
    │   └── metadata.json   # 元数据信息
    └── karpathy-guidelines/
        ├── SKILL.md
        └── metadata.json
```

## 已有 Skills

| Skill | 说明 | 分类 |
|-------|------|------|
| [document-converter](./Skills/document-converter/) | Markdown、DOCX、PDF 格式之间的双向文档转换 | data |
| [karpathy-guidelines](./Skills/karpathy-guidelines/) | 面向编码与代码评审的行为准则，帮助减少 LLM 常见开发失误 | coding |

### document-converter

文档格式双向转换工具，支持：

- **TO Markdown**：DOCX → Markdown、PDF → Markdown
- **FROM Markdown**：Markdown → DOCX、Markdown → PDF
- **直接转换**：PDF → DOCX

核心特性：

- 自动检测并选择最优转换工具（MarkItDown、Pandoc、PyMuPDF4LLM、Gemini API 等）
- 级联回退机制确保转换成功率
- 支持批量处理与并发转换
- 图像提取与嵌入
- 转换质量验证与报告

主要依赖：`pandoc>=2.0`、`python3>=3.8`，可选依赖包括 `markitdown`、`pymupdf4llm`、`google-genai`、`pdf2docx`。

### karpathy-guidelines

编码行为准则型 Skill，适合在写代码、Review、重构时使用，重点强调：

- 先澄清假设与边界，避免带着误解直接实现
- 优先选择最简单、最小化的改动方案
- 只修改与当前任务直接相关的代码
- 为每一步定义可验证的成功标准

适用场景：

- 约束 AI 编码助手避免过度设计
- 在重构和修复问题时保持“手术式”改动
- 让任务拆解和验收标准更明确

## 如何使用

将所需的 Skill 目录复制到你的 AI 编码助手的 Skills 配置目录中即可启用。详细使用方式请参考各 Skill 目录下的 `SKILL.md` 文件。

## 许可证

MIT License
