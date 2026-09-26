# Futu API Options Skill

通过 Futu OpenD 和 Futu API 查询美股期权链、合约行情快照及 Greeks。连接失败时会提示用户先登录 OpenD；该 skill 仅用于读取行情，不会下单。

## 内容

- `SKILL.md`：连接、登录、查询期权链与读取快照的完整流程
- `agents/openai.yaml`：Codex skill 显示信息

## 前置条件

1. 安装 Futu OpenD 和 Python SDK `futu-api`。
2. 在 OpenD 中由用户登录富途账号，并保持 OpenD 运行。
3. 确认账号具备所需的美股期权行情权限。

默认连接本机 `127.0.0.1:11111`。不要把 OpenD 端口暴露到局域网或互联网；不要在聊天或脚本中保存登录密码或验证码。

## 安装

将仓库目录放入 Codex 的用户 skills 目录：

```text
~/.codex/skills/futu-api-options/
```

也可将同一目录放入兼容的个人 Agent skills 目录：

```text
~/.agents/skills/futu-api-options/
```

## 使用

在 Codex 中请求连接 Futu 并查询标的和到期日，例如：

> 使用 Futu API 查询 SPX 2026-09-28 的期权链、报价和 Greeks。

期权链返回合约元数据；动态报价和 Greeks 通过后续快照查询获取。每个合约有自己的更新时间，休市时可能显示上一交易时段的数据。

## 官方文档

- [OpenD 介绍](https://openapi.futunn.com/futu-api-doc/opend/opend-intro.html)
- [OpenD 安装与首次登录](https://openapi.futunn.com/futu-api-doc/quick/opend-base.html)
- [权限、额度与合规确认](https://openapi.futunn.com/futu-api-doc/intro/authority.html)
- [获取期权链](https://openapi.futunn.com/futu-api-doc/quote/get-option-chain.html)
- [获取行情快照](https://openapi.futunn.com/futu-api-doc/quote/get-market-snapshot.html)
