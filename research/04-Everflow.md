---
title: Everflow｜Partner Marketing 深度竞品研究
date: 2026-10-14
status: 公开证据版
tags: [SaaS, Affiliate, Everflow]
---
# Everflow：事件归因、收入成本与伙伴账单

## 1 产品概述与商业模式

[官] Everflow 覆盖伙伴管理、Offer、追踪、分析、自动账单和支付，并提供 Marketplace 与 Everflow Pay。[产品与定价页](https://www.everflow.io/pricing)（E1）。公开页未取得稳定可确认的统一报价，本报告不填历史流传价格。

[析] 其核心是面向多增长渠道的经营平台：客户可以管理广告主、伙伴与 Offer，既计算收入，也计算付给伙伴的成本。运营者、广告主和伙伴是不同访问角色。软件账单、客户应收、伙伴应付及 Everflow Pay 转账也应分开。

## 2 端到端业务流程

[析] 按官方资料重构；核心记录是转化事件，而非必须来自同一电商平台的订单。

```plaintext
[配置 Advertiser / Partner]
             |
[Offer -> Base/Additional Conversion Events]
             |
[配置 Revenue/Payout 与归因优先级]
             |
[链接/SDK 点击 -> transaction_id]
             |
[广告主 SDK / S2S 发送转化事件]
             |
[识别事件 -> 归因 -> 去重/审核/限额判断]
             |
[转化报表及收入/伙伴成本]
             |
[Partner Invoice: 手动或自动生成]
             |
      +------+--------------------+
      |                           |
[Approve & Pay]              [外部已付款]
[集成付款通道]              [Mark as Paid]
      |                           |
[付款处理中/完成/拒绝]       [仅更新账面记录]
      +-------------+-------------+
                    |
                 [对账复盘]
```

| 动作 | 功能 | 解决问题 | 证据 |
|---|---|---|---|
| 跟踪多阶段价值 | Base + Additional Events | 一次销售无法表达完整漏斗 | [官] E2 |
| 区分收入与成本 | 事件 Revenue/Payout | 同一结果不同商业单价 | [官] E2 |
| 处理链接与优惠码冲突 | Advertiser 归因优先级 | 多来源争佣 | [官] E3 |
| 组织付款 | 自动/手动账单、调整、同步 | 海量伙伴人工算账 | [官] E4 |
| 区别登记与转账 | 两种付款动作 | 账面已付但未转款 | [官] E4/E5 |

## 3 三级功能清单

| 一级 | 二级 | 三级功能/动作 | 证据 |
|---|---|---|---|
| Offer | 事件 | 基础事件命名 | [官] E2 |
| Offer | 事件 | 添加额外事件 | [官] E2 |
| Offer | 全局复用 | 关联广告主级全局事件 | [官] E2 |
| Offer | 收入 | 事件收入模型 | [官] E2 |
| Offer | 支出 | 事件伙伴 Payout 模型 | [官] E2 |
| Offer | 可见性 | 额外事件 Public/Private | [官] E2 |
| Offer | 审核 | 手工审核转化开关 | [官] E2 |
| Offer | 去重 | Allow Duplicate Conversion | [官] E2 |
| Offer | 限额 | 额外事件超限转 Pending | [官] E2 |
| 追踪 | SDK | 选择事件生成脚本 | [官] E2 |
| 追踪 | S2S | event_id/adv_event_id 参数 | [官] E2 |
| 归因 | 优先级 | Click Based | [官] E3 |
| 归因 | 优先级 | Coupon Based | [官] E3 |
| 归因 | 识别 | 显式/ Cookie Transaction ID | [官] E3 |
| 归因 | 补充 | 指纹、邮件、优惠码、Clickless | [官] E3；需相应数据和开关 |
| 回传 | Partner | 按事件发送伙伴 Postback | [官] E2 |
| 账单 | 创建 | 手动选择伙伴/期间/付款条款 | [官] E4 |
| 账单 | 创建 | 自动生成与起始日期 | [官] E4 |
| 账单 | 维护 | 添加金额/备注/调整 | [官] E4 |
| 账单 | 维护 | 同步最新报表数据 | [官] E4 |
| 账单 | 状态 | Unpaid/In Progress/Paid/Deleted | [官] E4 |
| 账单 | 导出 | PDF/CSV/JSON/QuickBooks | [官] E4 |
| 账单 | 税项 | 小计、VAT、总额分列 | [官] E4；非税务适用承诺 |
| 支付 | 执行 | Approve & Pay | [官] E5 |
| 支付 | 记账 | Mark as Paid | [官] E5 |
| 支付 | 检查 | Partner Is Payable | [官] E5 |
| 支付 | 通道 | Everflow Pay/PayPal/Tipalti 等 | [官] E5 |
| 支付 | 外部 | 收集银行信息、外部自行支付 | [官] E5 |
| 支付 | 批量 | 批量付款与总额确认 | [官] E5 |
| 支付 | 异常 | Rejected、In-Progress 检查 | [官] E5 |
| 资金 | 未开票 | Request Outstanding Balances | [官] E5 |
| 资金 | 已开票 | Invoice Outstanding Balance | [官] E4 |
| 开放 | REST | Network/Affiliate/Advertiser API | [官] E6 |
| 开放 | 事件 | Webhooks 与 JS SDK | [官] E6 |
| 权限 | 员工 | 字段级及金额审批组合 | [待] API 角色不等于员工权限全表 |

## 4 官方真实页面截图与交互分析

![Everflow 官方截图：Offer 转化事件关联全局事件开关](attachments/everflow-events.png)

[官] 来源：[设置转化事件，2026-09-04 更新](https://helpdesk.everflow.io/customer/how-to-set-up-conversion-events)。截图用遮罩高亮 Global Advertiser Event 关联开关；保留官方原图，未重绘。

[析] 收入和 Payout 放在事件页使运营围绕“什么动作值得支付”配置。全局事件复用可以把审核或 Postback Controls 规则传播到多个 Offer，减少重复配置；同时带来影响面扩大的风险，应关注修改全局事件后是否有依赖预览和版本记录。[待] 当前界面是否展示所有受影响 Offer、回滚和差异视图未实测。

[析] 官方给出“创建事件不会自动触发追踪”的提醒，说明配置与数据接入是两个完成条件。适合借鉴的交互是把配置成功、测试事件收到、成功归因、产生金额四个检查点分别显示，避免只有“保存成功”。

## 5 对象、关系、状态、规则、异常、权限、资金、API

### 5.1 对象关系

[析] 概念关系：

```plaintext
Advertiser 1 -- N Offer 1 -- N Conversion Event
Advertiser 1 -- N Global Event <- 可被多个 Offer Event 关联
Partner -- 追踪链接/点击 Transaction ID -- Conversion
Conversion -- Revenue / Partner Payout -- Reporting
Partner -- Invoice -- Payment / Adjustment
```

Offer 不是订单；Conversion 也不必等于一次付款。一个点击可能关联多个漏斗事件，重复是否允许依事件配置。

### 5.2 归因规则

[官] Click Based 默认优先顺序为显式 Transaction ID、Cookie 内 ID、指纹、邮件（需开启）、优惠码、Clickless。Coupon Based 把优惠码移到首位，其余依序回退；优惠码优先的 Postback 必须携带广告主 `aid`，否则可能回退到 Transaction ID。[归因优先级](https://helpdesk.everflow.io/customer/everflows-conversion-attribution-priority)（E3；2026-07-10 更新）。

[析] “多方法支持”不意味着所有方法同时可信。必须验证数据缺失、优惠码冲突及来源伪造场景；指纹能力也不等于跨设备确定识别。

[官] 事件可设置手工审核和重复转换开关；Private 额外事件不会向伙伴展示，也不支付该事件 Payout；额外事件达到收入/支出限额后，新转化可转 Pending。[E2](https://helpdesk.everflow.io/customer/how-to-set-up-conversion-events)。[待] 完整转化状态枚举、退款接口、规则改动追溯范围尚未覆盖。

### 5.3 资金和异常

[官] 账单状态与付款状态分开。Mark as Paid 只更改记录；Approve & Pay 依配置通道处理资金，但未配置付款方式时可能仅标记 Paid、方式 None、不发生转款。[伙伴账单](https://helpdesk.everflow.io/customer/processing-partner-invoices)（E4）、[伙伴付款](https://helpdesk.everflow.io/customer/processing-partner-payments)（E5）。

[官] 账单页 Outstanding Balance 是已开票未付金额，伙伴管理的 Outstanding Balances 报告是未开票金额。自动开票开启时删除历史账单可能导致重复纳入未来账单，官方明确警告。[E4](https://helpdesk.everflow.io/customer/processing-partner-invoices)。

| 异常 | 官方可确认处理 | 设计含义/缺口 |
|---|---|---|
| 未设置付款方式 | 可能仅标记已付、无真实转账 | [析] 必须核查通道与付款凭证 |
| 回传重复 | 依事件重复开关 | [待] 多次销售、重复通知的业务键区别 |
| 超事件限额 | 新转化 Pending | [待] 解除限额后是否自动恢复 |
| 开票后报表变化 | 可同步账单 | [待] 已付款后冲正与差额账单 |
| 外部付款 | 平台不跟踪实际结果 | [析] 要保留外部支付凭证 |
| 自动开票期间删账单 | 官方提示可能重复支付 | [析] 删除与财务撤销不应混同 |

### 5.4 API 与权限

[官] REST 基地址 `https://api.eflow.team/v1`，EU 账户另用 `https://api-eu.eflow.team/v1`；通过 `X-Eflow-API-Key` 鉴权。Network API 管理平台资源，Affiliate 和 Advertiser API 有各自范围，并有 Webhooks、JS SDK。[开发者文档](https://developers.everflow.io/)（E6）。

[官] S2S 转化事件的 `adv_event_id` 与 `event_id` 是不同层级 ID，不可把界面显示的 Offer 级 ID 随意塞入广告主级参数（E2）。[待] 生产限流、回调签名、幂等键与失败补发未实测；不假定存在资金 API 的 exactly-once 保证。

## 6 产品经营与商业模式

[析] Offer/事件/分析建立运营价值，Marketplace 降低伙伴发现成本，Pay 延伸至资金流程；多渠道和多事件能力有利于增加客户使用深度，但实施成本来自追踪集成、归因规则和对账治理。

[官] Everflow Pay 费用说明按月付款规模等计费，跨境 USD 和非 USD FX 费用有差异，具体报价需要账户经理确认。[Pay 费用，2026-07-10](https://helpdesk.everflow.io/customer/understanding-everflow-pay-fees-who-pays-them)（E7）。[待] 平台当前订阅价、各币种支付资格和通道费用总额不在本次确定范围。

## 7 产品经理可借鉴机制

| 机制 | 原因 | 价值 | 局限 |
|---|---|---|---|
| Event 独立于 Offer | [析] 同一漏斗多阶段有不同价值 | 分阶段计价和优化 | 易重复计费，需清晰事件语义 |
| Revenue/Payout 分开 | [析] 客户收入不等于伙伴成本 | 支持网络经营与毛利分析 | 汇率、税费及调整需另算 |
| 全局事件复用 | [析] 广告主有一致跨 Offer 政策 | 减少重复配置 | 单次变更影响面大 |
| 账单与付款双状态 | [析] 应付确认和资金执行不同 | 对账可解释 | None 通道标记已付仍有误读风险 |
| 未开票/未付区分 | [析] 两类负债生命周期不同 | 财务工作量与现金需求更清晰 | 同名 Balance 容易混淆 |

## 8 结论与待验证项

[析] Everflow 是本批次研究复杂事件、归因和伙伴应付最有价值的对象之一。可配置面广，需要同步研究“配置正确”和“追踪真的触发”两套验收链路。

| 优先级 | 验证用例 | 证据 |
|---|---|---|
| P0 | A 点击、B 优惠码，含/不含 aid | 归属原因、转化日志 |
| P0 | 重复 event_id 与独立业务交易 | 去重结果、收入与 Payout |
| P0 | 无付款方式点击付款、外部标付、集成失败 | 账单/付款状态和真实凭证 |
| P0 | 自动开票后退款/调整 | 差额处理、重复开票防护 |
| P1 | 全局事件规则修改 | 影响 Offer 清单、历史快照 |
| P1 | 伙伴权限和不同 API key 越权 | 服务端访问边界与日志 |

### 来源目录

E1：[产品/定价](https://www.everflow.io/pricing)；E2：[设置转化事件](https://helpdesk.everflow.io/customer/how-to-set-up-conversion-events)；E3：[归因优先级](https://helpdesk.everflow.io/customer/everflows-conversion-attribution-priority)；E4：[伙伴账单](https://helpdesk.everflow.io/customer/processing-partner-invoices)；E5：[伙伴付款](https://helpdesk.everflow.io/customer/processing-partner-payments)；E6：[API](https://developers.everflow.io/)；E7：[Pay 费用](https://helpdesk.everflow.io/customer/understanding-everflow-pay-fees-who-pays-them)。检索于2026-10-13，编写于2026-10-14。

