<h1 align="center">DualCV</h1>

<p align="center">
  支持求职版 / 学术版一键切换的中文 LaTeX 简历模板
</p>

<p align="center">
  <img src="https://img.shields.io/badge/engine-XeLaTeX-3776AB">
  <img src="https://img.shields.io/badge/license-MIT-2ea44f">
</p>

## 📝 简介

DualCV 是一个面向中文用户的 LaTeX 简历模板，支持 **求职版** 和 **学术版** 一键切换。只需修改一个选项，同一份 `.tex` 源文件即可编译出风格迥异的两版简历：

```
job 模式      →  实习经历 / 项目经历 / 技能证书 / 荣誉奖励
academic 模式 →  研究经历 / 论文发表 / 竞赛奖项 / 技能与语言
```

## 👀 效果预览

| 求职版 | 学术版 |
| :---: | :---: |
| [job.template.pdf](assets/job.template.pdf) | [academic.template.pdf](assets/academic.template.pdf) |

## ✨ 主要特性

- **双模式切换**：`\documentclass[..., job]{dualcv}` 或 `academic`，一个选项控制全部内容分流
- **语义化命令**：`\cveducation`、`\cvinternship`、`\cvproject`、`\cvresearchentry`、`\cvpublication` 等，只需填内容
- **中文优化**：CJK 字体开箱即用（SimSun / SimHei），中英文混排友好
- **照片支持**：圆形 / 矩形头像，左 / 右对齐可选
- **学术论文列表**：自动编号，作者姓名加粗高亮
- **主题色区分**：求职版默认红色，学术版默认海军蓝，可自定义

## 🚀 快速开始

### 环境准备

- TeX 发行版：[TeX Live](https://www.tug.org/texlive/) 或 [MiKTeX](https://miktex.org/)
- 编译引擎：**XeLaTeX**（必须，CJK 字体依赖）
- 中文字体：SimSun / SimHei（Windows 自带；macOS / Linux 需自行安装或在 `dualcv.cls` 中替换）

也可以直接使用 [Overleaf](https://www.overleaf.com/) 在线编译（需上传字体文件）。

### 1. 复制模板

```bash
cp resume.template.tex resume.tex
cp refs.template.bib refs.bib
```

### 2. 填写个人信息

编辑 `resume.tex`，修改以下字段：

```latex
\name{你的姓名}
\mobile{138-0000-0000}
\email{your-email@example.com}
\photo[circle,noedge,left]{avatar}   % 替换为你的照片文件名（不含扩展名）
% \github{your-github-id}
```

### 3. 选择模式

```latex
% 求职版
\documentclass[11pt, a4paper, job]{dualcv}

% 学术版
\documentclass[11pt, a4paper, academic]{dualcv}
```

### 4. 编译

```bash
xelatex resume.tex
```

如有参考文献：

```bash
xelatex resume.tex
biber resume
xelatex resume.tex
```

## ⚙️ 自定义

### 切换主题色

编辑 `dualcv.cls` 中的颜色定义：

```latex
% 求职版默认红色，学术版默认海军蓝
\definecolor{awesome-red}{HTML}{DC3522}
\definecolor{awesome-navy}{HTML}{1A3A5C}
```

### 标题高亮开关

在 `resume.tex` 中：

```latex
\setbool{acvSectionColorHighlight}{true}   % true 开启，false 关闭
```

### 字体替换

如果系统无 SimSun / SimHei，在 `dualcv.cls` 中修改：

```latex
\setCJKmainfont[AutoFakeBold=2.5]{你的字体名}
\setCJKsansfont{你的字体名}
```

## 📁 文件结构

```
.
├── dualcv.cls              # 模板类文件（核心）
├── resume.template.tex     # 简历模板（填入你的信息即可）
├── refs.template.bib       # 参考文献模板
├── avatar.png              # 示例头像
├── assets/
│   ├── job.template.pdf    # 求职版示例
│   └── academic.template.pdf  # 学术版示例
├── CONTRIBUTING.md
├── .gitignore
├── LICENSE
└── README.md
```

## 🤝 贡献

欢迎提交 Issue 和 Pull Request，详见 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 📄 许可证

本项目基于 [MIT License](LICENSE) 开源。
