# xdu-thesis-skill

面向 Codex 的西安电子科技大学本科毕业设计（论文）辅助 skill，用于审查和改进基于 `xduugthesis` / XDUTS 的 LaTeX 论文项目。

它关注三件事：

- 论文结构是否完整：题名信息、中英文摘要、关键词、致谢、参考文献和章节组织。
- LaTeX 写法是否稳妥：`xdusetup`、图表公式、交叉引用、引用文献、编译检查。
- 学术表达是否规范：术语首次出现、中英文摘要一致性、章节衔接、结论与证据对应。

## 快速使用

把本目录放入 Codex skills 目录：

```text
~/.codex/skills/xdu-thesis-skill/
```

在 Codex 中提出类似请求即可触发：

```text
请使用 xdu-thesis-skill 检查我的西电本科毕业论文 LaTeX 项目。
```

## 与 XDUTS 配合

本 skill 不分发学校模板、logo、字体或论文样例文件。建议读者自行使用 XDUTS 或本学院要求的模板。

可从 Overleaf 快速查看 XDUTS 西电本科生毕业论文模板：

https://www.overleaf.com/latex/templates/xduts-xi-dian-ben-ke-sheng-bi-ye-lun-wen-mo-ban/qjnyrqwqrvrr

Overleaf 页面说明该模板基于 XDUTS，并标注模板许可证为 LaTeX Project Public License 1.3c。模板页面也提示模板可能不是最新，实际使用时建议以 XDUTS 官方版本、学校/学院当年通知和本地模板要求为准。

XDUTS CTAN 页面：

https://www.ctan.org/pkg/xduts

## 目录结构

```text
xdu-thesis-skill/
├── SKILL.md
├── agents/
│   └── openai.yaml
└── references/
    ├── official-requirements.md
    ├── template.md
    ├── writing-style.md
    ├── latex-patterns.md
    └── validation.md
```

## 开源说明

本仓库只包含通用审查流程和写作/排版参考，不包含任何个人论文正文、实验结果、学生信息、导师信息、学校 logo、字体或官方模板文件。

公开规范可能随年份和学院要求变化。本 skill 会尽量区分“公开来源规则”“官方 Word 规范摘录后的 LaTeX 检查建议”“本地模板推断”和“写作建议”，最终应以学校、学院和导师的当前要求为准。

## License

MIT License. See [LICENSE](LICENSE).
