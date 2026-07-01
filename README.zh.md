# HTML 可视化编辑器
原项目自大佬cxq0517的https://github.com/cxq0517/htmltool2

一个极简、完全本地运行的所见即所得 HTML 编辑器，适合微调 AI 生成的单页 HTML。

最简洁的 HTML 文字编辑器，可以直接修改 HTML 上的文字，并保证原渲染效果不变。现在可以随时微调你用 AI 生成的 HTML 格式的 PPT、简历、信息图等各种 HTML 文件。

它专注做两件事：

- 直接点击页面里的文字进行修改
- 点击元素空白区域后调整背景色和文字颜色

除了文字和颜色，页面结构、布局、CSS、图片和动画会尽量保持原样。

[English README](README.md)

## 特性

- 单文件应用：打开 `index.html` 即可使用
- 完全本地：文件读取、编辑和保存都在浏览器里完成
- 无需构建：不依赖 Node、打包器或后端服务
- 安全预览：默认不执行被编辑 HTML 中的脚本
- 交互预览：可选开启脚本，用于动画 PPT、翻页和 JavaScript 驱动页面
- 纯文本编辑：粘贴内容时自动去掉富文本格式
- PPT 式位置调整：拖动选中元素，使用八个控制点缩放；拖动角点时按住 `Shift` 可等比缩放
- 颜色面板：支持背景色、文字色、HEX 输入和快捷色板
- 状态提示：显示当前文件是否已经修改
- 拖拽加载：可直接把 `.html` / `.htm` 文件拖到窗口中
- 图片保留：保存时会尽量把已加载的 `<img>` 图片内嵌到 HTML 中

## 快速开始

直接用浏览器打开：

```text
index.html
```

然后点击「打开 HTML」选择文件，或把 HTML 文件拖进窗口。

如果你的 HTML 依赖本地相对路径资源，例如 `./style.css`、`./image.png`，建议在项目目录中启动本地静态服务后访问编辑器：

```bash
python -m http.server 8765
```

再打开：

```text
http://127.0.0.1:8765/index.html
```

## 使用方法

1. 打开 `index.html`
2. 点击「打开 HTML」或拖入一个 HTML 文件
3. 打开「编辑模式」
4. 点击文字进行编辑
5. 点击元素空白区域选中元素
6. 拖动选框移动元素，或拖动控制点缩放；拖动角点时按住 `Shift` 可保持宽高比
7. 点击悬浮调色按钮打开颜色面板
8. 点击「保存」下载 `原文件名-edited.html`

如果要编辑带动画、翻页效果的 HTML PPT，请先打开「交互预览」。这样页面自己的 JavaScript 可以初始化幻灯片、动画和翻页导航。

快捷键：

| 快捷键 | 作用 |
| --- | --- |
| `Ctrl` / `Cmd` + `Z` | 撤销 |
| `Ctrl` / `Cmd` + `Y` | 重做 |
| `Ctrl` / `Cmd` + `Shift` + `Z` | 重做 |
| `Ctrl` / `Cmd` + `S` | 保存当前结果 |
| `Esc` | 先关闭颜色面板，再取消元素选中 |

## 安全说明

编辑器默认通过 iframe 预览用户 HTML，并移除了 `allow-scripts` 权限，因此被编辑页面里的脚本不会运行。只有打开「交互预览」时才会执行页面脚本。这可以降低恶意 HTML 影响编辑器本体的风险。

仍需注意：

- 不要编辑来源不明、包含敏感内容的 HTML
- 只对可信的本地文件或 AI 生成文件开启「交互预览」
- 保存结果来自浏览器序列化后的 DOM，格式可能和原文件不完全一致
- 如果页面依赖运行时 JavaScript 渲染内容，默认预览可能不会展示脚本生成的部分

## 已知限制

- 保存后的 HTML 可能发生属性顺序、空白、大小写等格式变化
- 不支持新增、删除和拖拽排序元素
- 移动和缩放会写成 inline 几何样式，约束较强的 flex/grid 布局可能与自由定位的 PPT 元素表现不同
- 颜色修改会写入 inline style
- 相对路径资源在 `srcdoc` 预览中可能无法按原 HTML 所在目录解析
- 浏览器无法读取的图片会保留原路径
- JavaScript 驱动页面需要先开启「交互预览」再编辑
- Firefox 对 `contenteditable="plaintext-only"` 的支持与 Chromium 系浏览器不同

## 浏览器兼容性

推荐使用最新版 Chrome 或 Edge。

Safari 和 Firefox 可以尝试使用，但编辑行为和颜色选择器可能存在差异。

## 文件结构

```text
.
+-- index.html        # 编辑器本体
+-- test.html         # 测试页面
+-- README.md         # English README
+-- README.zh.md      # 中文说明
+-- LICENSE           # MIT License
+-- CONTRIBUTING.md   # 贡献指南
+-- SECURITY.md       # 安全策略
+-- CHANGELOG.md      # 变更记录
```

## 路线图

- 撤销 / 重做
- 多文件标签页
- 字号和字体编辑
- 渐变背景编辑
- 更精确的文本节点编辑模式
- 可选脚本预览模式
- Chrome 扩展版本

## 贡献

欢迎提交 issue 和 pull request。开始前请阅读 [CONTRIBUTING.md](CONTRIBUTING.md)。

## 许可证

[MIT](LICENSE)
