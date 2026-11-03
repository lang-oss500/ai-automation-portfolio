[返回作品集](../README.md)

# TrendRadar｜按主题监控加密资产资讯

## 项目背景
用开源 TrendRadar 试验一个小范围资讯订阅服务，观察选定主题能否产生值得推送的消息。[上游项目](https://github.com/sansan0/TrendRadar)

## 解决的问题
把反复浏览多个资讯源的工作拆成订阅、筛选、调度和通知四步，每一步分别核验。

## 技术栈
Python、RSS、YAML、GitHub Actions、Telegram Bot。采集、匹配和通知实现来自上游。

## 我的具体工作
我选定了加密资产资讯和 Telegram 单渠道通知作为试验范围。账号下的配置提交修改了资讯源、主题词和运行工作流，包含 CoinDesk、Cointelegraph 等订阅以及每小时第 33 分钟的调度规则。[配置提交](https://github.com/lang-oss500/TrendRadar/commit/7b5a0e795db10a5d414d22ba1b91b76f595c12c6)

## AI 工具如何参与
开发记录中，Codex 梳理了上游 RSS 和 Telegram 流程，建议先用测试 Fork 验证消息效果，并协助准备配置和检查手动运行状态。

## 遇到的问题
工作流已有手动触发记录，但一直停在排队阶段。现有记录无法定位排队原因。

## 人工判断与修复
我将试验范围限定为 Telegram 推送，并要求核对运行结果。工作流引用了 GitHub Secrets 中的机器人凭据和会话配置。排队问题仍待诊断，通知是否送达另以接收端记录核对。[该版本工作流](https://github.com/lang-oss500/TrendRadar/blob/7b5a0e795db10a5d414d22ba1b91b76f595c12c6/.github/workflows/crawler.yml)

## 验证结果
2026-11-03 检查仓库全部可见 Actions 运行，共 1 次。10 月 27 日手动触发的 Get Hot News 对应提交 `7b5a0e79`，第 1 次尝试，结论为空，作业 0 个、产物 0 个。[运行列表](https://github.com/lang-oss500/TrendRadar/actions) · [该次运行](https://github.com/lang-oss500/TrendRadar/actions/runs/40479920527)

| 状态 | 次数 | 解释 |
| --- | ---: | --- |
| queued | 1 | 已排队，还没有作业步骤可查 |
| running（GitHub 字段 in_progress） | 0 | 没有正在执行的运行 |
| success | 0 | 没有成功结束的运行可供核对采集、筛选或推送步骤 |
| failure | 0 | 没有以失败结束的运行 |

## 当前限制
未取得该次运行的 Telegram 发送响应或接收端消息记录。定时调度的实际执行、采集条数和通知送达均待验证。

**截图位** · 同次运行的步骤、提交号，以及隐去账号信息的 Telegram 收件截图。  
**Demo 位** · 待补一条从匹配到送达的实际样例。
