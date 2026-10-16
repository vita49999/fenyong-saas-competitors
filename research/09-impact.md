# impact.com：以合同约定贡献、以锁定确认应付

研究范围：Performance；不把 Creator、Advocate 的专属能力混入。本版2026-10-15重新核验核心官方页面并重写，旧版仅作线索，不直接继承未经支持的资金规则。

## 1 产品概述与商业模式

[官] Template Terms 包含合作条件与支付规则，伙伴申请或接受条款后形成双方合同。模板可以覆盖多个 Event Types、币种、Credit Group 及自定义附件。[I1 合同模板](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/contracts-and-template-terms/template-terms/create-template-terms)。

[析] 它把关系、贡献、奖励与应付时间组织在一套执行框架内。品牌负责政策、业务真实性和资金准备；伙伴负责推广；平台追踪并按约定处理。适合研究“合作协议如何成为系统规则”，不宜简单视为订单返佣插件。

[官] 官方集成门户区分 Brand、Partner、Agency API。[I7 集成门户](https://integrations.impact.com/)。[待] 本次未核验当前各套餐报价，不填第三方价格；品牌平台费、伙伴奖励、税费和资金服务费用须分别询价。

## 2 端到端业务流程与动作映射

[析] 下图依据官方机制重构，节点编号是本报告导航，不是产品状态码。

<!-- MAIN_FLOW -->

| 业务动作 | 功能承接 | 痛点 | 证据 |
|---|---|---|---|
| 约定合作政策 | Template Terms → Contract | 文档条款与系统执行脱节 | [官] I1 |
| 判断贡献归属 | Credit Groups | 不同伙伴参与同一旅程 | [官] I2 |
| 对不同事件定价 | Default Payout / Payout Groups | 统一佣金难覆盖差异贡献 | [官] I1/I3 |
| 审核退款和无效事件 | Pending期间Modify/Reverse | 过早支付造成争议 | [官] I4 |
| 确认应付时间 | Locking Date / Scheduled Clearing Date | 已批准与已付款混淆 | [官] I4 |
| 准备现金 | Funding Account与余额预测 | 已有应付但资金不足 | [官] I5 |
| 对账 | Partner Invoice / SOI | 多伙伴和多到期日难核对 | [官] I6 |

## 3 三级功能清单

清单覆盖本次已验证主线；完整商业版本与租户菜单未穷举。

| 一级 | 二级 | 三级功能/动作 | 证据 |
|---|---|---|---|
| 合作 | 条款 | 创建/复用Template Terms | [官] I1 |
| 合作 | 条款 | 名称、内部Labels、币种 | [官] I1 |
| 合作 | 条款 | 多Event Types | [官] I1 |
| 合作 | 条款 | 自定义条款及附件 | [官] I1 |
| 合作 | 签约 | 伙伴接受条款形成合同 | [官] I1 |
| 归因 | 优先级 | Preferred/Standard/Non-Preferred | [官] I2 |
| 归因 | 冲突 | Credit Group与Promo Code优先关系 | [官] I2 |
| 归因 | 检查 | 查看频道/伙伴Credit Group | [官] I2 |
| 奖励 | 基础 | 固定额/比例、订单或商品层级 | [官] I1 |
| 奖励 | 分组 | 条件命中一个Payout Group | [官] I3 |
| 奖励 | 分组 | 特定规则优先于一般规则 | [官] I3 |
| 奖励 | 调整 | 条件Payout Adjustments | [官] I1；完整叠加细节待验 |
| 奖励 | 数据 | 分组导入导出 | [官] I1 |
| 奖励 | 边界 | 按默认奖励层级应用分组 | [官] I3 |
| 转化 | 追踪 | 记录获伙伴贡献的Action | [官] I4 |
| 转化 | 审核 | Pending期间修改 | [官] I4 |
| 转化 | 审核 | Pending期间Reverse | [官] I4 |
| 转化 | 锁定 | 到Locking Date锁定 | [官] I4 |
| 转化 | 详情 | Action ID详情窗 | [官] I4 |
| 转化 | 补录 | EventDate决定规则/日期基准 | [官] I4 |
| 资金 | 概览 | Funding Account余额 | [官] I5 |
| 资金 | 概览 | Past Due/Pending Payments/Required Funding | [官] I5 |
| 资金 | 预测 | 45天余额预测 | [官] I5 |
| 资金 | 多账户 | 独立账户widget | [官] I5 |
| 资金 | 清算 | 清算日资金不足形成Overdue | [官] I4 |
| 单据 | 开票 | Partner Payments Invoice | [官] I6 |
| 单据 | 汇总 | Statement of Invoices | [官] I6 |
| 单据 | 查询 | Month/Billing Group筛选 | [官] I6 |
| 单据 | 下载 | PDF单据下载 | [官] I6 |
| 策略 | 注资 | Net30(PRF)/Net45(SOI)/Net45+(SOI) | [官] I8 |
| 系统 | 集成 | Brand/Partner/Agency API入口 | [官] I7 |
| 系统 | 权限 | 角色、字段、资金审批完整矩阵 | [待] 本次未完成 |
| 系统 | 可靠性 | 转化幂等、签名和重放策略 | [待] 本次未完成 |
| 系统 | 退款 | 锁定后特殊退款、追偿、税项调整 | [待] 不能据锁定前撤销推定 |

## 4 官方截图及交互分析

![impact.com官方帮助截图：Finance Overview资金账户概览](attachments/impact-finance-overview.png)

[官] 来源：[I5 Your Funding Account Overview Explained](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/finance/add-funds-to-your-funding-account/your-funding-account-overview-explained)。官方原始界面图，沿用2026-10-13本地附件；本次重新打开对应官方页面核对。截图日期不等于本次访问日期，非本次登录后台。

![impact.com官方帮助截图：45天余额预测](attachments/impact-balance-forecast.png)

[析] 概览把逾期、未来付款和需注资金额分开，帮助财务从“账户还有钱”转向“未来是否足够”。预测图应与下钻账单配合：预测下降不一定是伙伴佣金，可能还含平台费。图表内示例数据仅用于理解页面，不作为真实客户经营数据。

[官] I4说明Action ID可打开详情窗口，关键字段含Payout、Locking Date和Scheduled Clearing Date。[析] 将三个字段同屏呈现能解释金额何时确定、何时应付；完整异常操作截图和角色差异仍需租户演示。

## 5 对象、关系、状态、规则、异常、权限、资金与API

### 5.1 对象关系

[析] 下图为领域理解，不是内部数据库结构；Contract与Event Type共同形成Action适用政策。

<!-- OBJECT_FLOW -->

### 5.2 归因与计价分层

[官] 在官方描述的last-click情形，先按Credit Group层级决定候选，再看同层最后点击；Credit Groups还优先于Promo Code归因，但同为Preferred时Promo Code可优先。[I2](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/actions-and-payouts/credit-groups-explained)。[析] 因此“支持最后点击”不表示所有伙伴同一优先级，也不能照搬到高级归因配置。

[官] Payout Groups一次只适用一个；重叠条件时更具体的规则放上方，且应用于Default Payout相同的订单/商品层级。[I3](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/contracts-and-template-terms/template-terms/payout-adjustments/set-payout-rules-using-payout-groups)。[析] 看似商品条件也可能影响整单金额，验收必须同时测试条件层级和计算层级。

### 5.3 生命周期与异常

[官] Pending可修改/撤销；提前Approve不跳过锁定期；锁定后产生按清算日到期的义务。余额不足不取消Locked Action，而使未清算付款逾期。补录事件使用EventDate确定业务规则；若原锁定日期已过去，锁定/清算排期会基于提交时间调整。[I4](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/actions-and-payouts/understand-the-action-life-cycle-and-finance)。

<!-- STATE_FLOW -->

| 异常 | 已证实机制 | 待验 |
|---|---|---|
| 锁定前客户退货 | [官] Modify/Reverse（I4） | 商品行部分退款与舍入 |
| 提前批准后又退款 | [官] 锁定日前仍可修改（I4） | 审核日志和通知 |
| 到期资金不足 | [官] 应付保留，付款Overdue（I4） | 后续清算排序和币种 |
| 历史补录 | [官] 规则基准与排期基准区分（I4） | 重复订单/跨合同版本 |
| 条件涉及SKU但基础按订单 | [官] 分组仍在默认奖励层级应用（I3） | 复杂混合商品测试 |
| 锁定后特殊退款 | [待] 未完成全链核验 | 调整、追偿与财务单据 |

### 5.4 财务单据和资金责任

[官] 当前资金策略文档列三类：Net30(PRF)、Net45(SOI)、Net45+(SOI)，应与合同锁定/支付计划兼容。[I8](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/finance/add-funds-to-your-funding-account/guide-to-funding-strategies-for-brands)。这修正旧版仅概括两类的范围，不据此推导客户自动获授信用额度。

[官] 伙伴账单通常月度生成；一个伙伴可能因不同到期日有多张invoice；SOI是汇总、Partner Invoice是单伙伴单据。[I6](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/finance/finance-documents/partner-payments-invoices-explained-for-brands.md)。[析] “月度开票”不能被误读为所有Action同一天到期。

### 5.5 权限与API

[官] I7区分三类角色API门户。[待] 本版未完整读取资金、Action修改、事件上报的接口契约，API鉴权方式、限流、签名、幂等与员工角色不能凭惯例填入。企业内至少应验收条款修改、转化审核、注资、单据导出和密钥管理的职责分离。[析] 菜单可见不等于服务端操作权限，需拒绝用例验证。

## 6 产品经营与商业模式

[析] 合同规则、归因和财务让平台进入合作经营的持续流程，迁移成本来自历史合同、归因和对账连续性，而不只是伙伴名单。多产品线有扩展空间，但采购必须明确Performance与其他产品边界。

[待] 本次没有核验独立收入、客户平均ROI、留存及现行统一售价；不把官网客户案例提升率视为平均收益。评价应观察伙伴净增收、退款后佣金成本、归因争议率、逾期付款及财务人工投入。

## 7 产品经理可借鉴机制

| 机制 | 原因与价值 | 局限 |
|---|---|---|
| 合同成为执行参数 | [析] 政策和系统对齐，减少线下口头约定 | 条款复杂，需要版本与影响预览 |
| 归因、计价分层 | [析] 分别解释归谁与发多少 | 优先级组合易误配 |
| 锁定日、清算日分离 | [析] 金额确定和现金执行不在同一时点 | 不解释就会被认为拖款 |
| 资金预测而非只看余额 | [析] 支持提前安排现金 | 预测依赖未来义务完整性 |
| 同伙伴多到期日单据 | [析] 保持应付时间准确 | 单据数量和对账复杂 |

## 8 结论与待验证项

[析] impact.com适合研究合同到资金的长链路。其复杂度不是“按钮多”，而是规则、归因、确认和现金各有独立边界。

| 优先级 | 验证用例 | 取得证据 |
|---|---|---|
| P0 | Preferred点击与Standard Always Credit优惠码冲突 | 归因解释和合同配置 |
| P0 | 订单级奖励+SKU分组条件 | 逐行、整单计算结果 |
| P0 | 提前批准、锁定前后退款 | 状态、金额、历史记录 |
| P0 | 锁定但资金不足后充值 | Overdue、清算和资金流水 |
| P1 | 历史补录跨合同版本 | EventDate、版本和排期 |
| P1 | API重复Action、越权修改 | 唯一键、错误码、审计 |

### 官方来源

I1：[合同模板](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/contracts-and-template-terms/template-terms/create-template-terms)；I2：[Credit Groups](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/actions-and-payouts/credit-groups-explained)；I3：[Payout Groups](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/contracts-and-template-terms/template-terms/payout-adjustments/set-payout-rules-using-payout-groups)；I4：[Action生命周期](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/actions-and-payouts/understand-the-action-life-cycle-and-finance)；I5：[资金账户概览](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/finance/add-funds-to-your-funding-account/your-funding-account-overview-explained)；I6：[伙伴账单](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/finance/finance-documents/partner-payments-invoices-explained-for-brands.md)；I7：[API门户](https://integrations.impact.com/)；I8：[资金策略](https://help.impact.com/brand/what-would-you-like-to-learn-about/platform-features/finance/add-funds-to-your-funding-account/guide-to-funding-strategies-for-brands)。访问：2026-10-15。

