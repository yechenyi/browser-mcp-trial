# browser_mcp_notes_v01

更新时间：2026-04-23

## 当前结论
- Playwright MCP 本地可行
- 普通 Chrome 路线可行
- nginx 本机反代可行
- ChatGPT 网页端不能直接接受 localhost
- 后续必须做 HTTPS 公网入口

## 当前本地链路
Chrome
→ Playwright MCP :8932
→ nginx 反代 :8787
→ /sse 正常返回 sessionId

## 已踩坑
1. Cloudflare Tunnel 先不作为优先方案
2. nginx 要关闭 buffering / cache
3. Host 头必须写成 localhost:8932
4. proxy_pass 要写 localhost:8932，不要写 127.0.0.1:8932
5. 端口占用不是服务坏了
6. ChatGPT 网页端会拦 localhost，报 Unsafe URL

## 下一步
1. 保持本地链路不丢
2. 整理最小 nginx 配置
3. 决定公网入口：现有域名或 DuckDNS
4. 做最小 HTTPS 公网入口
5. 再接 ChatGPT
