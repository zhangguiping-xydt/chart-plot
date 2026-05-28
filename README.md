# Chart Generator

OpenClaw 图表生成插件 — 支持柱状图、折线图、饼图、散点图、面积图，输出纯 SVG，零依赖。

## 安装

```bash
openclaw plugins install clawhub:chart-generator
```

## 使用

安装后在对话中直接让 agent 生成图表：

> 把这份销售数据画成柱状图

插件会注册一个 `chart` 工具，agent 自动调用。

## 支持的图表类型

| 类型 | tool `type` 参数 |
|------|-----------------|
| 柱状图 | `bar` |
| 折线图 | `line` |
| 饼图 | `pie` |
| 散点图 | `scatter` |
| 面积图 | `area` |

## 配置

```jsonc
{
  "plugins": {
    "entries": {
      "chart-generator": {
        "enabled": true,
        "config": {
          "defaultWidth": 800,   // 默认宽度 (200–4000)
          "defaultHeight": 500   // 默认高度 (200–4000)
        }
      }
    }
  }
}
```

## 开发

```bash
git clone https://github.com/zhangguiping-xydt/chart-generator.git
cd chart-generator

# 编译
npx esbuild index.ts --outfile=index.js --format=esm --platform=node --bundle --external:'openclaw/plugin-sdk/*' --external:'node:*' --target=node24
```

## 许可

MIT
