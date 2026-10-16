---
title: Tapfiliate｜联盟管理深度竞品研究
date: 2026-10-14
status: 公开证据版
tags: [SaaS, Affiliate, Tapfiliate]
---
# Tapfiliate：追踪与佣金管理，明确结算和转账边界

## 1 产品概述与商业模式

[官] Tapfiliate 提供联盟推广追踪、伙伴管理、佣金、报表、素材、自动化及集成，适用于电商、SaaS 和订阅场景。[定价与能力表](https://tapfiliate.com/pricing/)（T1）、[追踪产品](https://tapfiliate.com/tracking-and-attribution/)（T2）。

[析] 其主要形态是商家自建联盟项目的管理工具，核心业务是把外部转化变成可审核、可结算的佣金，实际付款可以由商家或外部通道完成。产品的 Payment 记录不能直接理解为银行转账。

[官] 当前月付页面列 Launch $89、Scale $179、Enterprise 定制。Launch 有1项目、50联盟成员、每月5,000点击及500转化等限制；Scale 扩大配额及高级佣金、Trolley 等能力（T1）。[待] 超额、币种、税费和最终合同另验。

## 2 端到端业务流程

```plaintext
[Program 配置 -> 网站/平台集成]
                 |
[Affiliate 准入 -> 独立链接/优惠码/素材]
                 |
[访问 -> Cookie/客户识别 -> Conversion]
                 |
            [生成佣金 Pending]
                 |
     +-----------+-------------+
     |                         |
[退款/作弊/重复]           [审核通过]
[拒绝/金额调整]                 |
     |                  [Affiliate Balance]
     |                         |
     |              +----------+------------+
     |              |                       |
     |        [手工 Settle]            [API 自动化]
     |        生成付款 CSV          外部支付后登记 Payment
     |              |                       |
     |        [商家外部转账]                  |
     |              +----------+------------+
     |                         |
     |                [余额扣减/付款历史]
     +-------------------------+
       已付后退款可形成负余额
```

[析] Trolley 是另一条已集成付款分支，需要配置和审核，不等于标准 CSV 过程自动转账。

| 业务动作 | 功能 | 痛点 | 证据 |
|---|---|---|---|
| 归因回访购买 | 链接 Cookie/优惠码/S2S | 点击与购买不同时发生 | [官] T2/T3 |
| 控制无效佣金 | Pending 后审核、拒绝 | 退款/作弊/测试单 | [官] T5 |
| 形成可付汇总 | Balance 与最低金额 | 分散佣金难付款 | [官] T4 |
| 外部付款对接 | CSV 或 API | 不同收款方式 | [官] T4/T7 |
| 已付后调整 | 负余额 | 退款后超付 | [官] T5 |

## 3 三级功能清单

| 一级 | 二级 | 三级动作/功能 | 来源 |
|---|---|---|---|
| Program | 配置 | 项目和 General settings | [官] T3/T4 |
| Affiliate | 准入 | 招募与管理 | [官] T1 |
| Affiliate | 分组 | 分组、私有素材 | [官] T1；套餐有别 |
| Affiliate | 层级 | 多级佣金及目标 | [官] T1；套餐有别 |
| 推广 | 链接 | 独立 referral 参数 | [官] T3 |
| 推广 | 链接 | Deep/Short links | [官] T1；套餐有别 |
| 推广 | 素材 | 创意素材与 XML feeds | [官] T1；套餐有别 |
| 追踪 | 浏览器 | JS Base Tracking + Conversion script | [官] T3 |
| 追踪 | 窗口 | Cookie Duration 配置 | [官] T3；范围有冲突 |
| 追踪 | 优惠码 | 平台集成/API/Zapier/Make | [官] T3 |
| 追踪 | 服务端 | S2S Postback | [官] T2/T3 |
| 追踪 | 数据 | Conversion metadata | [官] T2 |
| 佣金 | 类型 | 标准、循环佣金 | [官] T1 |
| 佣金 | 差异 | Group、商品/类别费率 | [官] T1；Scale |
| 佣金 | 奖励 | Bonus system | [官] T1；Scale |
| 审核 | 人工 | 批准、拒绝佣金 | [官] T4/T5 |
| 审核 | 自动 | Automatically approve commissions | [官] T4 |
| 退款 | 调整 | 取消/退款后拒绝 | [官] T5 |
| 退款 | 部分 | 修改已批准佣金金额 | [官] T5 |
| 退款 | 集成 | Stripe/WooCommerce 自动处理开关 | [官] T5 |
| 余额 | 计算 | 已批准佣金减已结算金额 | [官] T4/T5 |
| 余额 | 异常 | 负余额展示 | [官] T4/T5 |
| 付款 | 结算 | 单人或全部 Settle | [官] T4 |
| 付款 | 范围 | Up to 截止日期、最低金额 | [官] T4 |
| 付款 | 导出 | 生成 CSV 与付款资料 | [官] T4 |
| 付款 | 历史 | Payment History | [官] T4 |
| 付款 | 撤销 | Cancel 恢复余额 | [官] T4 |
| 付款 | 外部集成 | Trolley 连接与结算数据同步 | [官] T6 |
| 开放 | 自动化 | 查询余额/收款方式 | [官] T7 |
| 开放 | 自动化 | 外部付款后 Create a Payment | [官] T7 |
| 开放 | REST | 转化/佣金修改、批准/拒绝 | [官] T8 |
| 工作流 | 自动化 | Triggers/Zapier/邮件 | [官] T1/T4 |
| 权限 | 团队 | Permission system | [官] T1；具体矩阵待验 |
| 支付 | 原生服务 | Hands-Free Payout Service | [待] 定价页仍标 Coming soon，不计为已上线 |

## 4 官方真实页面截图与交互分析

![Tapfiliate 官方帮助截图：商家 Payments Balances 列表](attachments/tapfiliate-balance1.png)

[官] 来源：[结算与付款文件](https://support.tapfiliate.com/en/articles/13272686-the-payout-process-settling-balances-and-generating-a-payout-file)。已视觉核验，可见 Settle all balances、截止日期、Export 和逐伙伴余额。

[析] 结算工作集中在余额列表，批量动作适合周期付款；正负金额用颜色区分，能提示超付。风险在于“结算”会让余额扣减，而钱仍可能尚未转出。操作确认应明确外部付款步骤并标出缺失收款资料的成员。[待] 当前弹窗的默认选项和批量排除逻辑需实测。

![Tapfiliate 官方帮助截图：联盟成员 Dashboard 负佣金余额](attachments/tapfiliate-balance2.png)

[官] 同一官方文章的伙伴端截图，可见待审核与负佣金金额。[析] 商家和伙伴两端均展示负余额有利于透明解释；但负数为何产生需要可下钻到原始佣金、退款和结算记录，仅显示金额不足以消除争议。

## 5 对象、关系、状态、规则、异常、权限、资金、API

### 5.1 概念模型

```plaintext
Program -- Affiliate Membership -- Referral Link / Coupon
Click / Customer -- Conversion -- Commission
Commission Approval -- Affiliate Balance
Balance -- Settlement / Payment Record -- 外部支付凭证
Refund / Adjustment -- Commission 改变 -- Balance 改变
```

[析] Conversion 与 Commission 应区分；一次转化可涉及不同佣金逻辑。余额不是不可变账本，修改已批准佣金会影响它，需核验是否能追溯金额变更。

### 5.2 归因和文档冲突

[官] 官方集成说明写默认 Cookie45天，并给配置范围及最高365天；营销追踪页又描述1天到 lifetime。[集成说明，2026-09-10](https://support.tapfiliate.com/en/articles/12960344-understanding-how-the-integration-works)（T3）、[营销页面](https://tapfiliate.com/tracking-and-attribution/)（T2）。

[待] 这可能由套餐、版本或营销措辞造成，不能选择一个范围写成通用承诺。应查看当前租户 Program 设置与销售确认。Cookie 支持也不等于拒绝 Cookie、跨设备或浏览器限制下必定归因。

### 5.3 审核、退款与资金

[官] 默认追踪转化 Pending；退款、退货、作弊、自购、重复及测试订单可拒绝。已支付佣金拒绝后扣减当前余额，部分调整可修改佣金金额。Stripe/WooCommerce 智能集成提供退款自动处理开关。[退款和作废](https://support.tapfiliate.com/en/articles/13272809-how-to-handle-refunds-and-voiding-commissions)（T5）。

[官] 标准流程 Settle 会扣余额、生成 CSV；它不表示款项已从商家账户转出，也无法证明收款到账。未填写收款资料的人若被纳入结算，仍可能标 Settled；可 Cancel 恢复余额（T4）。[析] Balance 公式中的 paid/settled 是系统登记语义，应以外部支付凭证确认真实资金。

[官] Trolley 连接从 Scale 起、首笔订阅付款后可用，试用期间不可用；结算数据传给 Trolley，仍需在 Trolley 完成支付。取消涉及两系统处理。[Trolley，2026-01-16](https://support.tapfiliate.com/en/articles/7190765-automating-payouts-with-trolley)（T6）。[待] 原生 Hands-Free 服务仍有 Coming soon 文案，不因“将在2026年”推定已上线。

| 异常 | 官方处理 | 剩余验证 |
|---|---|---|
| CSV 生成但未付 | 系统可仍为 Settled | 支付文件与记录自动对账 |
| 缺收款资料仍结算 | Cancel 后补资料再结算 | 批量警告和默认行为 |
| 已付后退款 | 负余额/差额扣减 | 离场伙伴如何追偿 |
| Trolley 取消 | 两边都要处理 | 失败补偿和状态一致性 |
| Webhook/API重复 | [待] 未验 | 防重复佣金与重复付款 |
| Cookie 文档范围冲突 | [待] 未验 | 当前套餐及实际输入限制 |

### 5.4 API、权限和系统

[官] API 自动化的官方顺序是：获取余额及收款信息→通过支付方 API 实际付款→在 Tapfiliate Create a Payment 登记。[REST付款流程](https://support.tapfiliate.com/en/articles/13342050-automated-payouts-using-rest-api)（T7）。[析] “创建 Payment”本身不是转账。

[官] REST 文档有 `PATCH /1.6/commissions/{commission_id}/` 和批准/拒绝等能力，示例使用 `X-Api-Key`。[REST](https://tapfiliate.com/docs/rest/)（T8）。[待] 文档部分示例存在 Api-Key/X-Api-Key 名称差异，接入时应以当前接口实际鉴权说明验证，不复制任意样例。限流、幂等、密钥范围和权限矩阵未实测。

## 6 产品经营与商业模式

[析] Launch 的规模配额与 Scale 高级佣金/付款集成形成升级路径。除 SaaS 订阅，还需考虑超额及外部支付服务费用；只比较软件月费会遗漏运营和对账成本。自建联盟工具的价值主要来自降低追踪和结算管理成本，伙伴招募质量仍依赖商家运营。

[官] 定价页列的 Scale 自动付款是 Trolley，原生 Hands-Free 项目仍写 Coming soon（T1）。[待] 不将路线图能力作为采购可用能力。

## 7 产品经理可借鉴机制

| 机制 | 原因与价值 | 局限 |
|---|---|---|
| 佣金审核后形成余额 | [析] 先确认结果、再汇总付款 | 要区分审核和到期风险 |
| 正负余额同屏 | [析] 让超付可见，支持未来抵扣 | 不代表钱已追回 |
| 结算范围按日期筛选 | [析] 给退款等待期留出空间 | 手工执行仍可能选错 |
| API先付款后登记 | [析] 便于使用任意支付方 | 中间失败会状态不一致 |
| 集成退款开关 | [析] 减少人工冲正 | 各平台事件和行为可能不同 |

## 8 结论与待验证项

[析] Tapfiliate 的研究重点应是佣金与余额管理的可解释性，以及“Settled≠到账”。不宜以默认流程没有转账就写成完全不支持自动支付，也不宜把未来原生服务视为已交付。

| 优先级 | 用例 | 证据 |
|---|---|---|
| P0 | 缺收款资料参与批量结算 | 弹窗、CSV、余额、修复路径 |
| P0 | CSV外部失败后取消重付 | 平台和支付方记录不重复 |
| P0 | 已付佣金部分退款 | 原佣金、差额、负余额 |
| P1 | Trolley 失败/取消 | 两边状态及责任方 |
| P1 | Cookie 1天/365天/lifetime | 当前套餐实际限制 |
| P1 | API付款成功但登记失败重试 | 幂等业务键与补偿 |

### 来源目录

T1：[定价](https://tapfiliate.com/pricing/)；T2：[追踪](https://tapfiliate.com/tracking-and-attribution/)；T3：[集成说明](https://support.tapfiliate.com/en/articles/12960344-understanding-how-the-integration-works)；T4：[结算与CSV](https://support.tapfiliate.com/en/articles/13272686-the-payout-process-settling-balances-and-generating-a-payout-file)；T5：[退款与作废](https://support.tapfiliate.com/en/articles/13272809-how-to-handle-refunds-and-voiding-commissions)；T6：[Trolley](https://support.tapfiliate.com/en/articles/7190765-automating-payouts-with-trolley)；T7：[API付款自动化](https://support.tapfiliate.com/en/articles/13342050-automated-payouts-using-rest-api)；T8：[REST API](https://tapfiliate.com/docs/rest/)。检索跨2026-10-13至14。

