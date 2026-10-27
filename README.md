# 夯拉投票

从夯到拉，一目了然 —— 一个通用评级投票网站。

- 任意创建投票题目与选项（例：AI 大模型，ChatGPT / Claude / Gemini…）
- 每个选项按 **夯爆 / 夯 / 一般 / 有点拉 / 拉胯** 五档评级
- 投票时可附一句 50 字内**锐评**，结果页以弹幕形式滚动展示（按评分染色）
- 公网 IP 识别 + 设备指纹兜底，**防重复投票**（同一标识每题限一份选票，重复提交视为修改）
- 结果页实时刷新：均分排名、评分分布、参与人数按 IP 去重

## 运行模式

| 模式 | 触发条件 | 说明 |
|---|---|---|
| 云端模式 | 部署在绑定的正式域名（`hongla-vote.app.workbuddy.host`） | 数据存于 WorkBuddy 云数据库（PostgreSQL），全网实时同步 |
| 自动跳转 | 从 GitHub Pages（`slatinwine.github.io`）访问 | 云端网关按 Origin 白名单拦截跨域请求，镜像页自动跳转到全区共享的正式版链接 |
| 本地模式 | 其他来源且云端探测失败 | 数据保存在本浏览器 localStorage，链接仅同一浏览器有效 |

单文件应用（`index.html`），无构建步骤；云 SDK 同源托管于仓库（`workbuddy-cloud-sdk.js`），加载失败时自动回退 CDN。

## 联系我

<div align="center">
  <img src="qrcode.jpg" width="180" alt="公众号二维码">&nbsp;&nbsp;&nbsp;
  <img src="xhs-qr.jpg" width="180" alt="小红书二维码">
  <p>
    <b>扫码关注公众号</b>：知识地下城 · 更多 AI 游戏与更新<br>
    <b>小红书 · 酒里加盐</b>（小红书号 6100441379）：酒馆会往酒里加盐，让顾客越喝越渴
  </p>
</div>
