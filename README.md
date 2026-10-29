# AI Dev Cockpit

AI Dev Cockpit 是给 AI 开发者用的 Windows 网络诊断工具。访问 ChatGPT、OpenAI API、Claude、GitHub 等服务出现连接失败或延迟高时，它会分别检测 DNS、TCP 和 HTTPS，再结合系统代理和应用代理的设置，帮你判断问题出在哪一层。

本仓库只用于发布安装包和收集反馈，源码暂未公开。

内置 6 个探测目标：ChatGPT（chatgpt.com）、OpenAI API（api.openai.com）、OpenAI 登录（auth.openai.com）、Claude（claude.ai）、GitHub（github.com）、ZCode（zcode.z.ai），暂不支持自定义目标。

## 下载

前往 [Releases](https://github.com/159357xxj/ai-dev-cockpit-releases/releases) 下载最新版本。每个版本的发布说明里都列出了安装包的 SHA-256，下载后建议先核对：

```powershell
Get-FileHash .\AI-Dev-Cockpit_<版本>_x64-setup.exe -Algorithm SHA256
```

安装包目前没有代码签名，Windows 可能提示"Windows 已保护你的电脑"。核对哈希无误后，点"更多信息 → 仍要运行"即可。

## 它会做什么，不会做什么

- 只在你点击时探测，并且只探测内置的固定目标。
- 设计上不修改系统代理、DNS、TUN 或防火墙设置。
- 历史记录和导出报告保存在本机，不会上传；用户主动诊断时，应用会向所选内置目标发送不携带用户凭证的 HTTPS 请求。
- 导出的报告默认已脱敏。

## 反馈

请在 [Issues](https://github.com/159357xxj/ai-dev-cockpit-releases/issues) 中反馈，附上应用导出的诊断报告即可。请不要粘贴含有个人路径、账号或密钥的内容。
