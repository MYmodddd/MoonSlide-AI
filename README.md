# MoonSlide AI

**MoonSlide AI** 是一个结合大语言模型（LLM）对话能力与 MoonBit 强类型特性的次世代演示文稿（PPT）生成引擎与前端交互展示平台。本项目旨在验证“前端纯净输入 -> 极速底层核心解析 -> 前端边缘端物理打包”的终极架构。

## 简介
当前的 AI PPT 工具多依赖于沉重的 Python 后端栈或复杂的纯前端组件框架。MoonSlide AI 旨在探索以轻量级、高性能、对 WASM 原生支持的 **MoonBit** 语言作为后端解析与生成核心，结合极具现代感的 Vanilla 前端界面，打造一款端到端的对话式 PPT 生成工具。

## 目的
本项目的愿景是提供一套可脱离沉重后端计算资源、能在浏览器或极简边缘设备上独立高效运行的 PPT 生成器，让任何创意或灵感通过对话即可瞬间转换为标准结构化、且能被本地 Office 直接打开的 `.pptx` 文件。

## 功能特性 (Core Features)
- **参数动态下发管道**：通过 Node.js 中间件，前端用户输入的 prompt 能够无缝、动态地传递给底层的 MoonBit 引擎。
- **大模型架构兼容 (Mock LLM)**：内建了灵活的大语言模型参数接口，目前使用动态组装的 Mock 数据，未来可无缝对接 OpenAI/Moonshot 等真实 API。
- **纯净版 PPTX 组装引擎**：基于 MoonBit 构建底层的 XML 节点树，并在内存中组装出 `.pptx` 必需的全部底层 XML 结构，通过安全的自定义定界符全量透传。
- **浏览器端边缘打包 (Browser-Side ZIP)**：引入了 `JSZip` 技术，后端无需涉及文件 IO，前端即可在浏览器内存中直接将 XML 虚拟树打包压制为真实的 `.pptx` 文件并触发下载。
- **商业级前端工作流界面**：
  - **多模态语音输入 (Speech-to-Text)**：原生集成了 Web Speech API，一键即可通过麦克风将语音实时转写为 Prompt，实现动嘴做 PPT。
  - **极致视觉**：采用 Glassmorphism（毛玻璃）、霓虹辉光背景、全响应式的暗黑科技风格。
  - **模块化页面**：包含完整顺滑的登录 / 注册界面的切换。
  - **沉浸式布局**：带有左侧可收起历史记录栏 (Sidebar)、全局设置模态框 (Settings Modal)，以及极致的移动端自适应排列。

## 状态
**项目状态：活跃 (Alpha 完整版)**。目前核心解析引擎、前后端交互数据流与边缘物理打包已彻底完备，形成了首个真正的全栈业务闭环。

## 技术栈
- **后端 / 核心引擎**：[MoonBit](https://www.moonbitlang.com/)
- **中间件服务器**：原生 Node.js (0 npm 依赖)
- **前端 / UI**：原生 HTML5 + Vanilla CSS3 (CSS Variables, Flexbox/Grid, Animations) + Vanilla JavaScript
- **序列化与打包**：Office Open XML 规范 + JSZip

## 兼容性
- **CLI 核心库**：跨平台（Windows, macOS, Linux），支持编译为 WebAssembly (Wasm-GC) 及 JavaScript。
- **前端界面**：兼容所有现代浏览器（Chrome, Edge, Firefox, Safari），支持 PC 与移动端的无缝响应式切换。

## 安装指南
在本地运行本项目，您需要安装 MoonBit 工具链与 Node.js 环境。

1. **安装环境**：
   - 安装 Node.js。
   - 参考 [MoonBit 官方文档](https://docs.moonbitlang.com/) 安装 MoonBit CLI。
2. **克隆项目**：
   ```bash
   git clone <repository_url>
   cd "MoonSlide AI"
   ```

## 使用说明

**一键启动与体验**：
无需安装复杂的 `node_modules`，直接在项目根目录运行自带的极简服务器：
```bash
node server.js
```
终端提示启动成功后，请在浏览器中打开：👉 **[http://localhost:3000](http://localhost:3000)**

1. 进入登录页，随便输入账号密码点击 **Login** 即可进入主工作区。
2. 在左下方聊天框输入你需要生成 PPT 的提示词（Prompt），或者**点击麦克风图标直接进行语音输入**，确认后点击 **Generate PPT**。
3. 等待引擎极速运算，右侧面板渲染出生成的文件树后，点击 **Download .pptx**，即可下载并在 PowerPoint 中打开体验真实成果！

## 版本历史
- **v0.2.0 (全栈闭环架构)**
  - 完善全栈交互：新增商业级工作流界面（登录/注册、侧边栏、设置、响应式适配），并接入**原生语音转文字 (Speech-to-Text)** 多模态交互。
  - 打通底层数据流：加入指令动态解析与 XML 全量输出。
  - 实现真实打包：引入 JSZip 完成浏览器端物理文件下载。
- **v0.1.0 (MVP 架构)**
  - 确立 MoonBit 工程模块划分（`moonslide` 库与 `cli` 入口）。
  - 实现 AST 解析与 OpenXML 标签拼接机制。

## 贡献指南
欢迎所有对 MoonBit 语言、WebAssembly 或者现代 Web 视觉设计感兴趣的开发者参与贡献！
1. Fork 本仓库。
2. 创建您的 Feature Branch (`git checkout -b feature/AmazingFeature`)。
3. 提交您的修改 (`git commit -m 'Add some AmazingFeature'`)。
4. 推送至分支 (`git push origin feature/AmazingFeature`)。
5. 发起 Pull Request。

## 许可证
本项目采用 **Apache License 2.0** 许可证进行开源。详见项目声明。

## 联系方式与致谢
- **维护者**：MoonSlide AI Team
- **致谢**：感谢 MoonBit 团队提供如此优秀的下一代工具链环境，以及 JSZip 对前端原生文件操作的大力支持。
