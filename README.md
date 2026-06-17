# MoonSlide-AI
MoonSlide AI 是一个结合大语言模型（LLM）对话能力与 MoonBit 强类型特性的演示文稿（PPT）生成引擎。当前的 AI PPT 工具多依赖于后端的 Python 栈或前端的复杂 JS 栈。本项目旨在利用 MoonBit 构建一个轻量级、高性能、可编译为 WASM 的 PPT 生成核心库。系统通过接收自然语言输入或直接对接 LLM 的流式输出（JSON / Markdown 大纲），将其动态解析为结构化数据，并利用 MoonBit 引擎最终渲染并打包生成标准的 Office Open XML (.pptx) 文件。
