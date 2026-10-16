# PartnerStack：把B2B伙伴贡献接到月度佣金与提现

研究日期：2026-10-15。主要范围：伙伴项目、链接/Lead/Deal、触发奖励、审核与月度账单。所有[官]表示官方文档确认，非本次登录租户。

## 1 产品概述与商业模式

[官] PartnerStack提供Marketplace、伙伴招募和赋能、链接追踪、Lead/Deal登记、佣金和支付。当前Launch/Growth/Enterprise套餐的开放范围不同；Launch描述链接或Lead/Deal二选一，Enterprise描述完整三类模式。[S1 套餐](https://partnerstack.com/pricing)。

[析] 主要面向B2B伙伴增长。它既有联盟式链接转化，也有伙伴主动登记与共同推进商机，不能把所有来源都当作Cookie归因。商家设计项目、Group与Offer，伙伴贡献客户或商机，平台组织佣金及支付。

[官] 支付产品页描述按事件、固定或比例奖励、按伙伴Group差异化结构及月度统一invoice。[S2 Payouts](https://partnerstack.com/payouts)。[待] 不采用第三方价格中位数，本次官方页未确认固定数字报价、实施费和合同处理费率。

## 2 端到端流程与动作映射

[析] 三种贡献入口汇合到佣金和账单；路径是否开放依套餐与Group配置。

<!-- MAIN_FLOW -->

| 动作 | 功能 | 痛点 | 证据 |
|---|---|---|---|
| 引入伙伴 | Marketplace、项目与分组 | 缺少渠道来源和运营分层 | [官] S1/S2 |
| 链接带客 | 链接与Referral | 标准线上转化来源难识别 | [官] S3 |
| 登记商机 | Group级Deal表单与阶段 | 长销售周期不能只追踪点击 | [官] S4 |
| 匹配后续收费 | Customer key/provider key | 客户与订阅收费身份脱节 | [官] S5 |
| 按时分期奖励 | Drip delay/cycle/occurrences | 年付收入不应立即全发佣金 | [官] S6 |
| 审核异常 | New/Approved/Declined/Hold | 可疑或未完成业务需暂缓 | [官] S7 |
| 企业付款与伙伴提现 | 月度invoice→可提现 | 佣金批准不能证明现金到位 | [官] S8 |

## 3 三级功能清单

| 一级 | 二级 | 三级功能/动作 | 证据/范围 |
|---|---|---|---|
| 网络 | 发现 | Marketplace接入 | [官] S1 |
| 伙伴 | 赋能 | Onboarding、培训、资源 | [官] S1/S3 |
| 伙伴 | 分组 | Group差异化佣金与资源 | [官] S2/S3 |
| 推广 | 链接 | 默认/自定义推荐链接 | [官] S3；需启用 |
| 推广 | 数据 | Clicks/Referred/Sold/Earned | [官] S3 |
| 客户 | 推荐 | 链接客户、Lead/Deal转成客户 | [官] S3 |
| 客户 | 补录 | 手工Add Customer | [官] S5 |
| 客户 | 匹配 | customer_key/provider_key | [官] S5 |
| 交易 | 补录 | Record a transaction | [官] S5 |
| 交易 | 商品 | product_key/category_key | [官] S5；规则依赖时必需 |
| Deal | 启用 | 按Group开放登记 | [官] S4 |
| Deal | 表单 | 新建/从其他Group复制 | [官] S4 |
| Deal | 字段 | Stage/Close date/Amount必填 | [官] S4 |
| Deal | 协作 | 分配给伙伴、同步CRM | [官] S4 |
| Deal | 规则 | 阶段触发佣金/分组/标签 | [官] S4 |
| 佣金 | 触发 | 按注册/交易等事件 | [官] S2 |
| 佣金 | 金额 | 固定/百分比 | [官] S2 |
| 佣金 | 分期 | Drip延迟、周期、次数 | [官] S6 |
| 佣金 | 分期 | Created/Terminated/Complete | [官] S6 |
| 佣金 | 审核 | 单笔和批量批准/拒绝/Hold | [官] S7 |
| 佣金 | 透明 | 对伙伴展示拒绝/Hold原因 | [官] S7 |
| 佣金 | 详情 | 伙伴、客户、金额、触发来源 | [官] S7 |
| 风控 | 暂缓 | 可疑佣金Hold不自动入票 | [官] S7/S8 |
| 账单 | 周期 | 月度生成与审核窗口 | [官] S8 |
| 账单 | 调整 | 添加、移入、导入佣金 | [官] S8 |
| 账单 | 延后 | Remove from invoice下期再入 | [官] S8 |
| 账单 | 删除 | Permanently delete区别于延后 | [官] S8 |
| 账单 | 控制 | Pause/Unpause、Pay invoice now | [官] S8 |
| 账单 | 审计 | Invoice activity变更日志 | [官] S8 |
| 付款 | 企业 | 卡/ACH到账后释放佣金 | [官] S8 |
| 提现 | 伙伴 | 可提现及已提现状态 | [官] S7 |
| 提现 | 渠道 | Direct deposit/Stripe/PayPal | [官] S2/S3；资格待验 |
| 报表 | 两层 | 项目Performance与跨项目Reporting | [官] S3 |
| 通信 | 运营 | Messages与触发邮件 | [官] S3 |
| 开放 | Partner API | Bearer、游标分页、毫秒时间戳 | [官] S9 |
| 开放 | Deal API | POST v2/deals及阶段/金额等字段 | [官] S10 |
| 权限 | 企业 | Billing权限控制账单查看 | [官] S8 |
| 权限 | 全量 | 细分角色及金额审批组合 | [待] 未完整核验 |
| 退款 | 已付后 | 自动追回与跨期抵扣全链 | [待] 不把负向调整视为真实追回 |

## 4 官方截图与交互分析

![PartnerStack官方帮助截图：佣金详情与审核侧栏](attachments/partnerstack-review.png)

[官] 来源：[S7 Reviewing partner commissions](https://support.partnerstack.com/hc/en-us/articles/360009840773-Reviewing-partner-commissions)。本次下载官方帮助附件；实际画面需与图录核对。非本次操作截图，截图日期/版本不等于访问日期。

[析] 列表到详情侧栏的设计保留审核上下文；把触发Offer、客户和佣金金额放在详情中，能帮助审核者解释来源。[待] Approved不可直接撤销时，错误批准后的账单删除路径是否有即时引导，需租户测试。

![PartnerStack官方帮助截图：伙伴跨项目首页](attachments/partnerstack-dashboard.png)

[官] 来源：[S3 伙伴Dashboard概览](https://support.partnerstack.com/hc/en-us/articles/360016866594-Comprehensive-overview-of-the-partner-dashboard)。官方图的版式/数据是文档示例，不作真实业务规模证据。

[析] 跨项目首页适合伙伴管理多个合作，项目内则聚焦该项目的链接、客户和资源；不开放的业务模式隐藏相应菜单，有助于减少无关操作。截图完整性与小屏可读性仍需实际浏览验证。

## 5 对象、关系、状态、规则、异常、权限、资金、API

### 5.1 领域对象

<!-- OBJECT_FLOW -->

[析] Group决定伙伴适用入口、资源和规则；Customer与Transaction分开才能持续追踪多次收费；Deal不是已成交客户。内部关系基数、数据库表名和业务键唯一性未经验证。

### 5.2 审核与分期状态

[官] 企业审核视图包含New、Approved、Declined、Hold、Paid；Paid也可能表示外部已付款的登记。伙伴侧则显示Pending Approval、On hold、Approved & pending payment、Funds Available、Withdrawn等阶段。月末符合条件的New可自动批准入票，不能把“还没人工审核”解释为不会付款。[S7](https://support.partnerstack.com/hc/en-us/articles/360009840773-Reviewing-partner-commissions)。

<!-- STATE_FLOW -->

[官] Drip通过延迟、周期、次数分摊奖励，状态为Created/Terminated/Complete；官方说明已经发出的payout无法claw back。因此延迟/分期用于降低取消风险，但不能保证消除已付部分损失。[S6](https://support.partnerstack.com/hc/en-us/articles/360020352173-Drip-commissions)。

[析] “按每次续费算佣金”和“单笔年费佣金按月分期”是两种机制：收入触发次数与奖励释放次数不同，需要分别测试。

### 5.3 客户、商机和接口字段

[官] 手工补客户后若要匹配后续payment webhook，需正确的customer_key和provider_key；按商品/类别规则的交易缺product_key/category_key可能不生成佣金。[S5](https://support.partnerstack.com/hc/en-us/articles/360009039214-Adding-a-customer-creating-a-transaction-and-changing-customer-attribution)。

[官] Deal登记按Group启用，Stage、Close date、Amount为不可移除的核心字段，阶段可触发佣金等动作。[S4](https://support.partnerstack.com/hc/en-us/articles/6021325335699-Using-deal-submission)。[析] 此处的“登记”不自动证明存在类似CRM报备的保护期、撞单优先权和申诉治理；这些列入待验。

[官] Partner API使用Bearer，示例GET /api/v2/rewards，并有starting_after/ending_before游标。企业Deal创建接口POST /api/v2/deals列金额单位cents、Group和阶段约束；这与Partner API不是同一权限语境。[S9](https://docs.partnerstack.com/docs/partner-api)、[S10](https://docs.partnerstack.com/reference/post_v2-deals)。[待] 不把Partner Bearer鉴权套用到所有企业接口；生产幂等、限流、签名及回调重试未实测。

### 5.4 账单、权限和资金异常

[官] 月度账单有7个完整审核日；通常7日末/8日晨按时区扣款，卡与ACH的资金处理不同；新建/待审核/已批准佣金可入票，Hold不入票。移除可下期再入，永久删除不同；账单有activity记录且由Billing权限控制。[S8](https://support.partnerstack.com/hc/en-us/articles/360022372354-Partner-commission-invoices)。

| 事件 | 当前证据 | 待验/风险 |
|---|---|---|
| 错误批准 | [官] 不能直接改Approved，需账单处理（S7） | 完整删除审计、伙伴通知 |
| 暂缓审核 | [官] Hold不自动入票（S7/S8） | 长期悬置提醒、SLA |
| 月度扣款未完成 | [官] 资金处理后才释放提现（S8） | 失败、重试和手续费 |
| 延后某笔佣金 | [官] Remove后可下期再入（S8） | 不应误当永久拒付 |
| 已发佣金后退款 | [官] 官方不承诺追回（S6） | 负余额或人工抵扣策略 |
| 缺交易标识 | [官] 会影响匹配与规则（S5） | 数据补偿和重复交易 |
| 两伙伴登记同一商机 | [待] 无完整证据 | 查重、保护期、归属裁决 |

## 6 产品经营与商业模式

[析] Marketplace降低伙伴发现门槛，CRM/Deal能力连接长销售周期，奖励支付把平台带入月度经营。产品价值需从“有效伙伴产生多少净收入”衡量，不能只看网络规模。

[官] 套餐从单一业务入口到更完整模式、培训、激励、MDF和高级集成分层（S1）。[析] 企业应按链接联盟、转介和共同销售需求选择，而不是根据“有PRM”字样推定所有报备能力。[待] 当前合同价格、佣金处理费率、各国家提现资格和税表规则未完整核验；页面营销数字不等于独立经营数据。

## 7 产品经理可借鉴机制

| 机制 | 原因与价值 | 局限 |
|---|---|---|
| 多贡献入口汇合为佣金 | [析] 覆盖不同B2B伙伴模式 | 各入口真实性与归属规则不同 |
| 按Group配置表单与资源 | [析] 减少一套流程强套所有伙伴 | Group迁移后的历史规则需明确 |
| Drip延迟与分期 | [析] 奖励节奏贴合取消风险 | 已付部分仍有风险 |
| Hold与Declined分开 | [析] 调查不等于拒付 | 需要到期提醒避免无限挂起 |
| 账单审核与提现分层 | [析] 清晰承接企业资金责任 | 伙伴可能误读Approved为到账 |
| 变更日志 | [析] 多人调整账单时可以追溯 | 完整权限与日志导出仍需验收 |

## 8 结论与待验证项

[析] PartnerStack在本批次位于联盟增长与B2B渠道协作交汇处。值得深入研究的是不同贡献入口、Group/Offer规则与月度资金兑现如何相接；不能把Lead/Deal直接等同纷享销客完整CRM治理。

| 优先级 | 用例 | 证据 |
|---|---|---|
| P0 | New未人工审核到月末 | 自动批准、入票、通知 |
| P0 | Approved误批后处理 | 账单更改和审计 |
| P0 | 年费Drip中途取消 | 已释放/未释放金额、终止事件 |
| P0 | 企业扣款失败/ACH处理中 | 企业账单与伙伴可提现状态 |
| P1 | Customer/provider key缺失再补录 | 后续续费和重复计佣 |
| P1 | 伙伴同商机登记/Group迁移 | 查重、归属、历史Offer |
| P1 | API重试和跨伙伴访问 | 防重、权限、错误码 |

### 官方来源

S1：[Pricing](https://partnerstack.com/pricing)；S2：[Payouts](https://partnerstack.com/payouts)；S3：[伙伴Dashboard](https://support.partnerstack.com/hc/en-us/articles/360016866594-Comprehensive-overview-of-the-partner-dashboard)；S4：[Deal submission](https://support.partnerstack.com/hc/en-us/articles/6021325335699-Using-deal-submission)；S5：[客户交易与归属](https://support.partnerstack.com/hc/en-us/articles/360009039214-Adding-a-customer-creating-a-transaction-and-changing-customer-attribution)；S6：[Drip](https://support.partnerstack.com/hc/en-us/articles/360020352173-Drip-commissions)；S7：[佣金审核](https://support.partnerstack.com/hc/en-us/articles/360009840773-Reviewing-partner-commissions)；S8：[佣金账单](https://support.partnerstack.com/hc/en-us/articles/360022372354-Partner-commission-invoices)；S9：[Partner API](https://docs.partnerstack.com/docs/partner-api)；S10：[Deal API](https://docs.partnerstack.com/reference/post_v2-deals)。访问：2026-10-15。

