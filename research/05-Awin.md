---
title: Awin｜联盟网络深度竞品研究
date: 2026-10-14
status: 公开证据版
tags: [SaaS, Affiliate, Awin]
---
# Awin：联盟网络中的验证、应付与付款

## 1 产品概述与商业模式

[官] Awin 连接广告主和 Publisher，提供伙伴发现、推广、报表、佣金规则和支付。广告主套餐为 Access、Accelerate、Advanced。[广告主产品页](https://www.awin.com/gb/advertisers)（A1）。

[析] Awin 同时提供平台和网络组织能力，研究时不能仅把它视为一套供商家自建联盟的 SaaS。其价值包含发现与连接伙伴、约定交易验证规则、跨广告主收益管理。广告主、Publisher、代理机构和网络平台有不同责任。

[官] 英国定价页观察值：Access £99 + VAT/月，加交易额3.5% tracking fee；Accelerate £199 + VAT/月起，加2.5%；Advanced 定制报价。伙伴佣金另由广告主设定。[英国广告主定价](https://www.awin.com/gb/pricing/advertisers)（A2）。价格不可推广至全球合同。

## 2 端到端业务流程

[析] 重构 Publisher 收益链路；拒绝、付款阻塞和多币种需分支处理。

```plaintext
[广告主开通 Programme / 配置佣金与追踪]
                       |
[Publisher 加入网络 -> 选择/加入广告主计划]
                       |
              [获取链接/素材 -> 推广]
                       |
              [追踪交易 Pending review]
                       |
               [广告主验证交易]
                 /            \
          [Declined]       [Approved]
          原因查询              |
                         [网络支付处理]
                               |
                           [Payable]
                               |
              [币种余额 + 门槛 + 收款资料检查]
                         /             \
                   [被阻塞]        [进入付款批次]
                   修复资料              |
                                   [付款记录]
```

| 动作 | 功能承接 | 痛点 | 证据 |
|---|---|---|---|
| 寻找合作品牌/媒体 | 目录与伙伴发现 | 招募难、合作匹配低效 | [官] A1 |
| 验证有效成交 | Pending/Approved/Declined | 退款及无效交易不可直接付佣 | [官] A3/A4 |
| 分清可付与审核完成 | Approved 和 Payable 分开 | “审核通过为什么没钱” | [官] A3 |
| 定位付款阻塞 | Earnings Summary 提示 | 门槛/账户错误难自助排查 | [官] A3 |
| 解释拒绝或付款明细 | 交易报告与导出 | 争议缺少逐单证据 | [官] A4 |

## 3 三级功能清单

| 一级 | 二级 | 三级动作/功能 | 状态与来源 |
|---|---|---|---|
| 网络 | 发现 | 广告主目录、伙伴档案 | [官] A1 |
| 网络 | 发现 | 个性化伙伴推荐 | [官] A1；营销描述 |
| 网络 | 合作 | 计划加入与推广 | [官] A6 |
| 推广 | 链接 | 创建可追踪链接 | [官] A6 |
| 推广 | 素材 | 获取推广图片/素材 | [官] A6 |
| 推广 | 商品 | 商品 feed | [官] A9；仅确认主题与接口场景 |
| 佣金 | 分组 | 产品ID/类别规则 | [官] A2 |
| 佣金 | 分组 | 新老客规则 | [官] A2 |
| 佣金 | 高级规则 | SKU/优惠码/活动/Publisher | [官] A1/A2；套餐有别 |
| 佣金 | 高级规则 | Sub-partner/交易日期 | [官] A1/A2 |
| 佣金 | 企业规则 | 自定义追踪/归因规则 | [官] A2；Advanced |
| 验证 | 人工 | 广告主批准或拒绝 | [官] A5 |
| 验证 | 自动 | 广告主可配置自动验证期 | [官] A5；非统一60天 |
| 报表 | 交易 | 日期、广告主、订单号筛选 | [官] A4 |
| 报表 | 交易 | 交易状态与类型筛选 | [官] A4 |
| 报表 | 付款 | Paid/Payable 筛选 | [官] A4 |
| 报表 | 原因 | 悬停/导出查看拒绝原因 | [官] A4 |
| 报表 | 数据 | CSV/Excel 导出 | [官] A4 |
| 报表 | 数据 | 优惠码及点击到成交间隔 | [官] A4 |
| 资金 | 生命周期 | Pending review/Approved/Payable | [官] A3 |
| 资金 | 概览 | 下次付款日与阻塞状态 | [官] A3 |
| 资金 | 门槛 | 显示距离最低支付金额差额 | [官] A3 |
| 资金 | 币种 | 按币种查看收益与要求 | [官] A3 |
| 资金 | 周期 | 每月1日或15日付款批次 | [官] A3；节假日顺延 |
| 协作 | 通信 | Communication Center | [官] A2 |
| 协作 | 通信 | 自动伙伴邮件 | [官] A2 |
| 分析 | 深度 | 旅程/产品/伙伴报告及基准 | [官] A1/A2；套餐差异 |
| 系统 | 账号 | 团队成员及双因素认证 | [官] A2 |
| 开放 | 集成 | API/Zapier 连接 | [官] A7 |
| 开放 | 权益 | 广告主 API 受套餐限制及例外 | [官] A7 |
| 审计 | 重算 | 历史规则版本与全量佣金重算 | [待] 未完整核验 |
| 风控 | 退款 | 部分退款、已付款追偿全过程 | [待] 不能由拒绝状态推定 |

## 4 官方页面与交互分析

[官] 官方2026冬季版本发布页介绍新的广告主 Dashboard、关键指标、建议与待办，并提供演示。[官方版本发布与演示](https://www.awin.com/gb/product-releases/winter-2026)（A8）。

![Awin官方2026版本发布展示：Campaign创建成功与发布入口](attachments/awin-campaigns.webp)

[官] 来源为上述A8官方版本发布页。这是官方营销合成展示图，已视觉核验，可见活动摘要、优惠码、日期和 Publish campaign，不是本次登录后台操作截图，也不能充当 Earnings Summary 或交易验证页截图。[析] 创建与发布两个动作分离，有利于先确认活动配置再公开；当前产品是否有发布前检查及撤回，仍待实测。

**截图完成度：已有官方Campaign展示图，并补充下方Classic商品分类映射真实截图；收益与交易验证页仍待补。**

[析] 根据 A3 官方交互说明，收益组件把颜色与任务绑定：绿色表示可进入下一批付款，黄色提示距离门槛的差额，红色提示收款信息阻塞，并提供设置入口。这比只有金额卡片更适合自助排障。应保留文字原因，避免仅用颜色表达。

[析] A4 的交易报告将付款状态和交易验证状态分别筛选，支持解释“Approved 中同时有已付与未付”。拒绝原因可悬停或导出，有利于逐单沟通。[待] 移动端原因查看、筛选持久化、复杂币种提示和异常修复后的即时反馈尚未实测。以上是文档交互分析，非截图观察。

![Awin官方帮助截图：Classic商品Feed分类映射](attachments/awin-feed-mapping.png)

[官] 本次2026-10-15下载自[A10 Adding a Product Feed](https://help.awin.com/developers/docs/managing-your-feed)，该文更新于2025-10-21。对应Awin Classic的商品Feed分类映射，不是新后台收益或交易审核页面。[析] 用未映射分类列表与逐项映射，帮助运营定位数据错误；商品数据配置体验不能替代付款审核体验的验证。

## 5 对象、关系、状态、规则、异常、权限、资金、API

### 5.1 概念模型

```plaintext
Advertiser -- Programme -- 参与关系 -- Publisher
Programme -- Commission Group / 规则
Publisher -- Tracking Link / Creative / Feed
Click -- Transaction -- Validation
Transaction -- Commission -- 币种余额 -- Payment Run
Transaction Query / Bonus -- 交易报表
```

[析] Programme 的市场和合同边界重要；网络账户、广告主计划、Publisher 参与关系应区分。实际关联基数及内部字段未验证。

### 5.2 状态和规则

[官] 交易先 Pending review，由广告主验证后 Approved 或 Declined；Approved 不等于 Payable，后者需要网络支付处理完成。达到门槛且收款资料正确后进入付款批次。[交易状态与付款过程](https://success.awin.com/articles/en_US/Knowledge/Understanding-Transaction-Status-and-Payment-Process)（A3；2026-07-09 更新）。

[官] 验证时间因广告主而异；平台显示的 Validation Period 是历史平均值，不是保证时限；Auto Validation Period 可以为 None。[验证周期](https://success.awin.com/articles/en_US/Knowledge/How-long-does-it-take-for-an-advertiser-to-approve-a-transaction)（A5）。[析] 平均周期、自动批准规则和约定账期是三个概念，报告不把“60天自动批准”推广到全部计划。

[官] 交易报表可查看手工 Bonus、查询等类型，Approved 视图包含已付和未付。[交易报告](https://success.awin.com/articles/en_US/Knowledge/Publisher-Transaction-Report)（A4）。

### 5.3 资金责任与异常

[析] 付款涉及广告主、网络与 Publisher 的多方链路，交易有效性只是可付的一个条件；网络处理、门槛、币种和收款资料均可能影响发款。真实资金责任须依地区合同和具体支付方案核实，不能由状态推断平台对所有广告主信用兜底。

| 异常 | 文档已证实 | 待验 |
|---|---|---|
| Approved 未收到钱 | 尚可能未 Payable（A3） | 广告主资金、网络处理与合同责任 |
| 余额不足门槛 | 黄色提示差额（A3） | 跨币种是否可合并 |
| 账户错误 | 红色付款阻塞提示（A3） | 修复后的批次与到账时间 |
| 超过平均验证时间 | 平均时间不是 SLA（A5） | 申诉升级和超期规则 |
| 交易拒绝 | 可查拒绝原因（A4） | 部分拒绝与重提 |
| 已支付后退款 | [待] 缺少完整验证 | 负余额、追偿和账单调整 |

### 5.4 权限、API 和系统

[官] A7 指出广告主 API 通常需 Accelerate/Advanced 或多计划，Conversion API 等有例外；Zapier 连接使用 API token、账号类型、计划/Publisher ID 和时区。[API 集成说明](https://help.awin.com/apidocs/step-by-step)。[待] 未完整列出交易验证接口、签名、限流、重试和权限枚举。

[析] 需分别测试广告主、Publisher、代理机构及团队成员，尤其是“能查询报告”与“能验证交易/修改账户/付款”的分离。API 支持与套餐权益是不同问题。

## 6 产品经营与商业模式

[析] Awin 的网络供给与数据规模有助于伙伴发现，软件自动化和服务深度形成套餐升级。交易额比例费用使成本跟业务增长相关；商家预算必须同时计算平台费、tracking fee、伙伴佣金与可能的服务费。

[官] 英国 Access 页面示例：£100 销售、伙伴6%佣金时，伙伴得£6、Awin tracking fee £3.50（A2）。[析] 该 tracking fee 基数是销售额，不是伙伴佣金的3.5%，二者成本差异显著。[待] 跨市场价格、退款退费、税项及特殊行业替代费率需按合同验证。

## 7 产品经理可借鉴机制

| 机制 | 原因与价值 | 局限 |
|---|---|---|
| Approved 与 Payable 分离 | [析] 有效交易不等于满足发款条件；帮助解释等待 | 状态更多，需要原因与责任主体 |
| 金额卡片连接修复入口 | [析] 让用户从“发现问题”直接到“解决问题” | 收款修改可能仍需审核 |
| 历史平均周期明确非承诺 | [析] 有参考值又避免误导 | 用户仍需要超期升级路径 |
| 网络发现+经营工具 | [析] 连接供给与运营，降低冷启动 | 网络接入不保证高质量转化 |
| 地区计划与本地币种 | [析] 可以适应市场差异 | 多市场配置与对账复杂 |

## 8 结论与待验证项

[析] Awin 最值得借鉴的是多方联盟网络中的验证、可付与实际付款分离。它与自建联盟 SaaS 的比较必须纳入伙伴网络和费用结构，不能只比功能数量。

| 优先级 | 验证场景 | 验收证据 |
|---|---|---|
| P0 | 同一 Approved 交易到 Payable 到 Paid | 三阶段条件、责任方、时间记录 |
| P0 | 付款资料错误与修复 | 阻塞原因、审核和后续批次 |
| P0 | 部分退款/已支付后拒绝 | 佣金、tracking fee 及余额变化 |
| P1 | 自动验证 None 与有期限计划 | 实际策略、超期处理 |
| P1 | 多币种与最低门槛 | 各币种独立账单及付款 |
| P1 | 后台静态截图与角色对照 | 真实页面、时间、版本和演示录屏 |

### 来源目录

A1：[广告主产品](https://www.awin.com/gb/advertisers)；A2：[英国定价](https://www.awin.com/gb/pricing/advertisers)；A3：[状态与付款](https://success.awin.com/articles/en_US/Knowledge/Understanding-Transaction-Status-and-Payment-Process)；A4：[交易报告](https://success.awin.com/articles/en_US/Knowledge/Publisher-Transaction-Report)；A5：[验证时间](https://success.awin.com/articles/en_US/Knowledge/How-long-does-it-take-for-an-advertiser-to-approve-a-transaction)；A6：[Publisher 入门](https://www.awin.com/ca/publishers)；A7：[API/Zapier](https://help.awin.com/apidocs/step-by-step)；A8：[2026冬季发布](https://www.awin.com/gb/product-releases/winter-2026)；A9：[商品feed FAQ](https://help.awin.com/advertisers/docs/en/product-feed-faqs)。主要检索于2026-10-13，编写于2026-10-14。


A10：[商品Feed添加与分类映射，2025-10-21](https://help.awin.com/developers/docs/managing-your-feed)。截图补验日期：2026-10-15。
