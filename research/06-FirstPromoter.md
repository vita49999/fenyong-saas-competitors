---
title: FirstPromoter｜订阅联盟深度竞品研究
date: 2026-10-14
status: 公开证据版
tags: [SaaS, Affiliate, FirstPromoter]
---
# FirstPromoter：围绕订阅账单组织奖励与付款

## 1 产品概述与商业模式

[官] FirstPromoter 以 Campaign 组织推广者，每个 Campaign 有自己的奖励、注册页、联盟门户和邮件；同一推广者可以加入多个 Campaign，并拥有对应链接。[Campaign 配置](https://help.firstpromoter.com/en/articles/8971305-how-to-set-up-and-configure-a-campaign)（P1）。

[官] 原生计费集成包括 Stripe、Paddle、Chargebee、Recurly、Braintree；可以处理比例或固定奖励及循环计佣。[循环佣金](https://help.firstpromoter.com/en/articles/8971339-recurring-commissions-and-monetary-rewards)（P2）。

[析] 核心场景是商家自建订阅推荐/联盟项目，而非加入一个成熟广告联盟网络。商家经营 Campaign，Promoter 推广，Referral 是被推荐的客户，实际计费事件产生佣金。

## 2 端到端业务流程

```plaintext
[创建 Campaign -> 配奖励与注册页]
                  |
         [Promoter 注册/获邀]
                  |
         [分享独立链接/优惠码]
                  |
[Click -> Referral(邮箱/UID) -> 计费客户匹配]
                  |
   [账单平台发送支付/退款/升级/取消事件]
                  |
       [佣金计算与自动/人工审核]
           /                 \
    [退款负佣金]           [有效佣金]
           +--------+--------+
                    |
            [按月份生成 Payout]
                    |
        [NET 条款 + 最低支付门槛]
                    |
       [集成付款/托管/外部付款登记]
                    |
        [Promoter 门户查看与对账]
```

[析] 流程按官方文档重构，具体支付通道的状态和到账依产品配置。

| 动作 | 功能 | 痛点 | 证据 |
|---|---|---|---|
| 同时运营不同伙伴群 | 多 Campaign | 奖励与门户混杂 | [官] P1 |
| 建立推荐客户身份 | 邮箱/UID Referral 追踪 | 点击不能直接匹配后续账单 | [官] P3 |
| 奖励长期收入 | 生命周期/时长/次数佣金 | 只算首单忽略续费 | [官] P2 |
| 处理退款 | 负佣金调整 | 退款与佣金不在同一系统 | [官] P4 |
| 管理付款优先级 | Next/Overdue Payouts | 月末人工追账 | [官] P5 |
| 奖励非现金权益 | Webhook 发放积分/免费月 | 推广成本不必全现金 | [官] P4；应用需执行 |

## 3 三级功能清单

| 一级 | 二级 | 三级动作/功能 | 证据 |
|---|---|---|---|
| Campaign | 组织 | 多 Campaign 并行 | [官] P1 |
| Campaign | 组织 | 同一人加入多个活动 | [官] P1 |
| Campaign | 门户 | 独立注册页、Dashboard、邮件 | [官] P1 |
| Promoter | 奖励 | 单人自定义奖励覆盖默认 | [官] P4 |
| 追踪 | 点击 | 网站主脚本记录点击 | [官] P3 |
| 追踪 | 客户 | 邮箱/UID 发送 Referral | [官] P3 |
| 追踪 | Cookie | 默认60天且可调 | [官] P3 |
| 追踪 | 链接 | 多链接、自有域名、Sub-ID | [官] P6 |
| 追踪 | 优惠码 | Stripe 优惠码追踪 | [官] P6 |
| 追踪 | 控制 | first/last-click | [官] P6 |
| 奖励 | 金额 | 百分比/固定额 | [官] P2 |
| 奖励 | 周期 | 客户生命周期持续 | [官] P2 |
| 奖励 | 周期 | 限定月数 | [官] P2 |
| 奖励 | 周期 | 限定收费次数、仅首单 | [官] P2 |
| 奖励 | 分段 | 首期/后续不同费率 | [官] P2 |
| 奖励 | 范围 | 按产品或 plan 配费率/排除 | [官] P4 |
| 奖励 | 限制 | 单 Referral/伙伴累计上限 | [官] P4 |
| 奖励 | 里程碑 | 客户数/收入达标奖金 | [官] P4 |
| 奖励 | 非现金 | 免费月、积分、额度、折扣 | [官] P4 |
| 审核 | 方式 | 自动或手工审核 | [官] P4 |
| 审核 | 阈值 | 大于指定金额留待审核 | [官] P4 |
| 退款 | 调整 | 自动生成负佣金 | [官] P4；Braintree 例外 |
| 付款 | 聚合 | 月末后生成上月 Payout | [官] P5 |
| 付款 | 账期 | NET-15/30/45/60/Custom | [官] P5 |
| 付款 | 门槛 | 最低金额与跨月累计 | [官] P5 |
| 付款 | 待办 | Next/Overdue Payouts | [官] P5 |
| 付款 | 通道 | Stripe、PayPal、Wise CSV | [官] P4 的付款入口 |
| 集成 | Stripe | 支付、退款、升级、取消同步 | [官] P7 |
| 集成 | 测试 | Stripe Test mode | [官] P7 |
| 开放 | API | Admin/Affiliate/Tracking API | [官] P6/P8 |
| 开放 | Webhook | 非现金权益履约通知 | [官] P4/P8 |
| 开放 | 运维 | Webhook delivery/retries 文档 | [官] P8；具体参数待验 |
| 权限 | 人员 | 团队角色完整权限表 | [待] 未完成核验 |
| 审计 | 规则 | 旧佣金快照与批量重算 | [待] 未完成核验 |

## 4 官方真实界面展示与交互分析

![FirstPromoter 官方展示：Campaign 名称、链接、Cookie 时长及自动批准推广者](attachments/firstpromoter-rules.png)

[官] 来源：[奖励与佣金产品页](https://firstpromoter.com/features/affiliate-commission-software)。这是官网发布的界面展示图，非本次租户截图。已按实际画面确认：图中是 Campaign 配置，不能因为所在章节名称就称作“佣金期限配置”。

[析] 活动名、默认链接和 Cookie 有效期在同一区域，有利于活动负责人检查基本追踪条件。“自动批准推广者”与“自动批准佣金”是不同开关，产品培训应明确区分身份准入和收益审核。

![FirstPromoter 官方展示：Stripe Payouts 集成](attachments/firstpromoter-plans.png)

[官] 同一官方产品页发布的图，实际内容是 Stripe Payouts，并非图片文件名暗示的 coupon。展示受限 API key 与连接状态。[析] 清楚列出所需权限有助于接入，但“已连接”不证明资金可付，应进一步检查收款方 onboarding、余额与到账。[待] 当前产品对多账号切换的未完成佣金迁移提示需验证。

![FirstPromoter官方帮助截图：Stripe集成已连接与Test mode](attachments/firstpromoter-stripe-help.png)

[官] 本次2026-10-15从[P7官方Stripe集成帮助](https://help.firstpromoter.com/en/articles/8971438-how-to-integrate-stripe)下载的真实界面图，官方图片文件名包含2024-03-29；显示连接状态和测试模式，访问日期不是界面版本日期。[析] 用显式连接状态降低接入不确定性，但绿色已连接不能证明所有销售都已正确匹配Referral，仍需完整测试交易。

## 5 对象、关系、状态、规则、异常、权限、资金、API

### 5.1 对象关系

```plaintext
Campaign -- Rewards / Signup Page / Portal / Emails
Promoter -- Campaign Membership -- Referral Link
Click -- Referral(email/UID) -- Billing Customer
Billing Charge/Refund -- Commission -- Monthly Payout
Non-monetary Commission -- Fulfilment Webhook -- 商家应用
```

[析] 一人多 Campaign 的关系意味着奖励属于活动上下文，不应把推广者只有一个佣金率作为数据模型假设。

### 5.2 计佣、审核与账期

[官] 比例或固定奖励可以按客户生命周期、时长或收费次数终止；可以配置前后两段不同费率。[P2](https://help.firstpromoter.com/en/articles/8971339-recurring-commissions-and-monetary-rewards)。

[官] 产品页明确：计佣来自确认的计费事件；0金额账单不生成佣金，但 Referral 仍可追踪。默认自动批准，也可人工审核或设金额阈值；没有基于计时器的佣金自动批准，延迟付款应放到 payout terms。[P4](https://firstpromoter.com/features/affiliate-commission-software)。

[官] Payout 为某个月佣金的聚合；默认 NET-30 示例是3月佣金在4月30日支付，不是每笔交易发生后30天。Custom 无固定到期日，最低金额可跨月累计。[P5](https://help.firstpromoter.com/en/articles/9019492-how-payouts-work-in-firstpromoter)。[析] 审核、账期和门槛分别约束真实性、风险时间和支付效率。

### 5.3 异常、权限与资金

[官] 退款产生负佣金并减少未付余额；Braintree 的退款需人工处理。Stripe 集成文档确认销售、退款、升级与取消同步，并提供 Test mode。[P4](https://firstpromoter.com/features/affiliate-commission-software)、[P7](https://help.firstpromoter.com/en/articles/8971438-how-to-integrate-stripe)。

| 情形 | 已验证机制 | 待核验细节 |
|---|---|---|
| 试用/0元账单 | Referral 与付佣分离 | 后续首付是否沿用正确活动 |
| 部分退款 | 官方有退款负佣金机制 | 舍入、原币、已付后负余额 |
| 更换 plan | 按 plan 可设奖励 | 旧订单和跨期 prorations |
| 低于门槛 | 跨月累计 | 多币种聚合与汇率 |
| Custom terms | 无固定到期日 | 逾期看板如何处理 |
| 切换 Stripe 账号 | 先 Disconnect 再连接 | 未完余额和历史数据影响 |

[析] 商家承担佣金政策和付款责任；原生计费追踪不代表所有支付通道都自动付款。[待] 托管 payout 资格、费用、税表适用地区以及团队内审核/付款分权需另验。

### 5.4 API 与系统机制

[官] 官方文档将点击、Referral 和 Sales 追踪分开；Referral 需要邮箱或 UID 匹配计费客户，其他计费系统可通过 API 发送销售。[How it works](https://docs.firstpromoter.com/how-it-works)（P3）。开发文档还提供 Webhooks、事件类型、payload、投递和重试主题。[文档](https://docs.firstpromoter.com/introduction)（P8）。

[析] 应验收“前端推荐身份→计费客户→收费事件→佣金”的连接完整性。仅集成账单回调而没有 Referral 身份，无法保证正确归因。[待] API 鉴权头、事件唯一键、重试上限、签名和回调乱序未逐项验证，报告不列猜测值。

## 6 产品经营与商业模式

[官] 定价页观察：Starter $49/月、Business $99/月、Enterprise $149/月；分别对应月度联盟收入≤$5,000、≤$15,000、>$15,000的页面描述；有年付与14天试用。[定价](https://firstpromoter.com/pricing)（P6）。Enterprise 具体商业条件仍应询价。

[析] 按联盟收入分档使软件价值与客户增长关联；活动和个体覆盖满足从标准联盟到重点伙伴议价。奖励复杂性、托管支付与集成构成扩展价值。没有证据证明这些能力能独立带来某个平均增收比例。

## 7 产品经理可借鉴机制

| 机制 | 原因与价值 | 局限 |
|---|---|---|
| Campaign 默认+个体覆盖 | [析] 大多数规则一致，少数需议价 | 覆盖多了难审计，需清单 |
| 时长与次数分开 | [析] 月付年付不能只按一个时间维度处理 | 暂停/恢复和计费调整有边界 |
| 审核与付款等待分开 | [析] 有效性确认不必等于立刻付款 | 用户容易误解 Approved |
| 退款负佣金 | [析] 保留原收益并显示抵减，容易解释 | 已付款仍需追偿/抵扣机制 |
| 非现金权益用履约通知 | [析] 软件算奖、商家应用发权益 | 回调失败可能已算奖未兑现 |

## 8 结论与待验证项

[析] FirstPromoter 适合研究订阅生命周期佣金、活动隔离和按月付款组织；比泛化“支持循环佣金”更有价值的是收费次数、时长、规则覆盖和退款抵减如何结合。

| 优先级 | 验证用例 | 应取证据 |
|---|---|---|
| P0 | 试用→首付→续费→升级→退款 | 账单与佣金逐笔关联 |
| P0 | 年付与月付、按次数和按月数规则 | 截止边界、首次/后续费率 |
| P0 | 已批准未付及已付款后的退款 | 负佣金、余额和付款恢复 |
| P1 | 同一 Promoter 多 Campaign | 归属、冲突优先级 |
| P1 | 非现金 Webhook 重复/失败/重试 | 幂等履约与最终状态 |
| P1 | 改规则、更换计费账号 | 历史规则、权限和审计 |

### 来源目录

P1：[Campaign](https://help.firstpromoter.com/en/articles/8971305-how-to-set-up-and-configure-a-campaign)；P2：[循环佣金，2026-07-16](https://help.firstpromoter.com/en/articles/8971339-recurring-commissions-and-monetary-rewards)；P3：[追踪链路](https://docs.firstpromoter.com/how-it-works)；P4：[奖励和佣金](https://firstpromoter.com/features/affiliate-commission-software)；P5：[付款组织，2026-06-05](https://help.firstpromoter.com/en/articles/9019492-how-payouts-work-in-firstpromoter)；P6：[定价](https://firstpromoter.com/pricing)；P7：[Stripe，2025-03-20](https://help.firstpromoter.com/en/articles/8971438-how-to-integrate-stripe)；P8：[API/Webhooks 文档](https://docs.firstpromoter.com/introduction)。检索2026-10-13，编写2026-10-14。

