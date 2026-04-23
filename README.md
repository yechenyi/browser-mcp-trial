# browser-mcp-trial

当前状态：
- Playwright MCP 本地已跑通
- Chrome 现有浏览器路线已跑通
- nginx 本机反代已跑通
- ChatGPT 网页端不能直接连接 localhost
- 下一步是给本地 MCP 挂 HTTPS 公网入口

当前链路：
Chrome
→ Playwright MCP :8932
→ nginx 反代 :8787
→ /sse 正常返回 sessionId
