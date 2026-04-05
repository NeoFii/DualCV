# 贡献指南

感谢你对 DualCV 的关注！欢迎通过以下方式参与贡献。

## 🐛 报告问题

- 在 [Issues](https://github.com/your-username/DualCV/issues) 页面提交
- 请包含：问题描述、复现步骤、TeX 发行版及操作系统信息
- 如有编译错误，请附上完整的日志输出

## 💡 提交功能建议

- 先在 Issues 中搜索是否已有类似提议
- 提交新 Issue 时，说明使用场景和预期效果

## 🔧 提交代码

### 1. Fork & Clone

```bash
git clone https://github.com/your-username/DualCV.git
cd DualCV
```

### 2. 创建分支

```bash
git checkout -b feat/your-feature
```

分支命名建议：

| 类型     | 前缀       | 示例                      |
| -------- | ---------- | ------------------------- |
| 新功能   | `feat/`    | `feat/add-cover-letter`   |
| 修复     | `fix/`     | `fix/cjk-font-fallback`   |
| 文档     | `docs/`    | `docs/update-readme`      |
| 样式调整 | `style/`   | `style/section-spacing`   |

### 3. 本地测试

提交前请确保两种模式均能正常编译：

```bash
# 求职版
xelatex resume.tex   # \documentclass[..., job]{dualcv}

# 学术版
xelatex resume.tex   # \documentclass[..., academic]{dualcv}
```

### 4. 提交 & 推送

```bash
git add .
git commit -m "feat: 简要描述你的改动"
git push origin feat/your-feature
```

Commit message 建议使用 [Conventional Commits](https://www.conventionalcommits.org/) 格式：

- `feat:` 新功能
- `fix:` 修复
- `docs:` 文档变更
- `style:` 排版 / 样式调整（不影响逻辑）

### 5. 发起 Pull Request

- 目标分支：`main`
- PR 描述中说明改动内容与动机
- 如涉及模板结构变更，请附编译后的 PDF 截图

## 📋 贡献范围

欢迎但不限于以下方向：

- 新的简历模块（如求职信、推荐信模板）
- 字体兼容性改进（macOS / Linux 适配）
- 排版细节优化（间距、对齐、分页策略）
- 文档翻译（英文版 README）
- Bug 修复与编译兼容性修复

## 📄 许可证

提交贡献即表示你同意将代码以 [MIT License](LICENSE) 授权发布。
