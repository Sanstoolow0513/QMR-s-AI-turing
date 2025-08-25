# Claude Code Router 使用指南

## 先获取APIKey

  这里使用魔搭作为例子
  假设你得到了字段如下（只是展示不是真的需要“openai这样的字段”）

```js
OPENAI_API_KEY=your-api-key
OPENAI_BASE_URL=https://api-inference.modelscope.cn/v1
OPENAI_MODEL=Qwen/Qwen3-Coder-480B-A35B-Instruct
OPENAI_MODEL=Qwen/Qwen3-235B-A22B-Instruct-2507
OPENAI_MODEL=ZhipuAI/GLM-4.5
```

## ccr install

1. 安装ccr：

```bash
pnpm add -g @musistudio/claude-code-router 
```
2. 启动ccr

```bash
ccr start
```

  在第一次配置的时候可以瞎填    

## 配置文件修改

在 `C:\users\用户名\.claude-code-router` 目录下有一个名为 `config.json` 的文件，内容如下：

  原始内容是什么不重要，这里给出一个可能的版本，瞎填的字段很明显

```js
{
  "LOG": false,
  "OPENAI_API_KEY": "",
  "OPENAI_BASE_URL": "",
  "OPENAI_MODEL": "",
  "Providers": [
    {
      "name": "dasd",
      "api_base_url": "asdsad",
      "api_key": "sadasd",
      "models": [
        "asdsas"
      ]
    }
  ],
  "Router": {
    "default": "dasd,asdsas"
  }
}
```

修改为以下内容：
```json
{
  "LOG": true,
  "LOG_LEVEL": "info",
  "PORT": 3456,
  "API_TIMEOUT_MS": 600000,
  "Providers": [
    {
      "name": "modelscope",
      "api_base_url": "https://api-inference.modelscope.cn/v1/chat/completions",
      "api_key": "你自己的key",
      "models": [
        "Qwen/Qwen3-Coder-480B-A35B-Instruct",
        "Qwen/Qwen3-235B-A22B-Thinking-2507",
        "deepseek-ai/DeepSeek-V3.1",
        "ZhipuAI/GLM-4.5",
        "moonshotai/Kimi-K2-Instruct"
      ],
      "transformer": {
        "use": [
          [
            "maxtoken",
            {
              "max_tokens": 65536
            }
          ],
          "enhancetool"
        ],
        "Qwen/Qwen3-235B-A22B-Thinking-2507": {
          "use": ["reasoning"]
        }
      }
    }
  ],
  "Router": {
    "default": "modelscope,Qwen/Qwen3-Coder-480B-A35B-Instruct",
    "background": "modelscope,Qwen/Qwen3-Coder-480B-A35B-Instruct",
    "think": "modelscope,Qwen/Qwen3-235B-A22B-Thinking-2507",
    "longContext": "modelscope,Qwen/Qwen3-Coder-480B-A35B-Instruct",
    "longContextThreshold": 60000,
    "webSearch": "modelscope,Qwen/Qwen3-Coder-480B-A35B-Instruct"
  }
}

```

主要修改你自己的 API Key，添加推理模型，这个很重要，默认要加载推理模型，不配置的话，会出现推理模型连接错误，无法运行。

记得 config.json 修改后，运行 `ccr restart` 重启后然后运行 `ccr code`。