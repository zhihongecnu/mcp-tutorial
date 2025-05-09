# 快速开始

## 安装MCP

```bash
npm install mcp-protocol
```

## 基本使用

```javascript
const mcp = require('mcp-protocol');

// 创建MCP连接
const connection = mcp.createConnection({
  host: 'localhost',
  port: 8080
});

// 发送消息
connection.send('Hello MCP!');
```

## 下一步

- [深入了解MCP协议](./advanced.md)
- [查看API文档](./api.md)