# MCP快速开始

## 什么是MCP

MCP(Message Control Protocol)是一种轻量级的消息控制协议，主要用于:
- 微服务间通信
- 设备间消息传递
- 实时数据传输

## 安装MCP

```bash
npm install mcp-protocol
# 或者使用yarn
yarn add mcp-protocol
```

## 基本使用

### 1. 创建连接
```javascript
const mcp = require('mcp-protocol');

// 创建MCP连接
const connection = mcp.createConnection({
  host: 'localhost',  // 服务器地址
  port: 8080,        // 端口号
  timeout: 5000      // 超时时间(毫秒)
});
```

### 2. 发送消息
```javascript
// 发送简单文本消息
connection.send('Hello MCP!');

// 发送JSON格式消息
connection.send({
  type: 'message',
  content: 'This is a test message'
});
```

### 3. 接收消息
```javascript
connection.on('message', (data) => {
  console.log('收到消息:', data);
});
```

## 最佳实践

1. 错误处理
```javascript
connection.on('error', (err) => {
  console.error('连接错误:', err);
});
```

2. 心跳检测
```javascript
// 每30秒发送心跳包
setInterval(() => {
  connection.send('PING');
}, 30000);
```

## 下一步

- [深入了解MCP协议](./advanced.md)
- [查看API文档](./api.md)