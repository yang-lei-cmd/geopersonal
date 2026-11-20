# Day 5: 首个真实品牌 GEO 审计实战

> 使用 Round 4 工具执行的第一份真实 GEO Audit  
> 目标：证明方法论可行 + 积累可展示的 Case Study

---

## 审计目标

- **品牌**: [填写你的目标品牌或自选案例]
- **测试日期**: 2025年11月18日
- **覆盖平台**: ChatGPT / Gemini / Claude / Perplexity / DeepSeek
- **查询数量**: 至少6个核心查询词 × 5平台 = 30次测试
- **竞品对比**: ≥2个直接竞品同时测试

---

## Step 1: 确定核心查询词（6+类型覆盖）

基于 [manual_testing_guide.md](../guides/manual_testing_guide.md) 的六类框架：

| # | 查询词示例 | 类型 | 预期出现位置 |
|---|-----------|------|------------|
| 1 | "best project management software 2025" | Recommendation | 前3名 |
| 2 | "[BrandA] vs [BrandB] comparison" | Comparison | 对比表 |
| 3 | "[BrandName] review" | Review/Eval | 前5名 |
| 4 | "how to manage remote team effectively" | Tutorial/HowTo | 引用原文段落 |
| 5 | "[BrandName] pricing plans" | Pricing | 包含价格信息 |
| 6 | "project mgmt tool for startups" | Scenario-based | 场景化推荐 |

*注：请替换[BrandName]为实际目标品牌的名称*

---

## Step 2: 执行测试并记录（使用 Geo Tracker Sheet 1 格式）

### 测试记录模板（每行一条记录）

```
Date: 2025-11-18
Brand: [目标品牌]
Query: "best project mgmt software"
Platform: ChatGPT | Mentioned: True | Position: 2 | Score: 41/55
--------------------------------------------------------------
Gemini    | False | null     | 0/55
Claude    | True  | 3        | 35/55 (被直接引用"Our UI is intuitive")
Perplexity| True  | 1        | 50/55 (引用了pricing page原文)
DeepSeek  | False | null     | 0/55
--------------------------------------------------------------
Key Claim Found: "AI-powered scheduling" (出现在回答第2段)
Schema Hints: FAQPage ✅, Article ✅, Product ❌
Confidence: High (有明确URL来源)
Notes: Claude和Perplexity表现最强；DeepSeek未覆盖英文市场
```

### 逐条填写指南

1. **Mentioned (True/False)**: AI是否提到了该品牌
2. **Position (1-10)**: 首次出现的位置序号（1=最佳）
3. **Total Brands**: 回答中提到的同类品牌总数
4. **Sentiment**: Positive / Neutral / Negative（根据上下文判断）
5. **Key Claim**: AI引用的具体卖点或描述
6. **Source URL**: 回答中引用的具体页面URL
7. **Confidence**: High（有直接证据）/ Medium（推断）/ Low（模糊提及）
8. **Schema Hints**: 检查引用页面是否有FAQ/Product/Article等Schema
9. **Score**: 按公式计算（满分55分，详见manual_testing_guide）
10. **Notes**: 额外观察、异常发现、改进机会

---

## Step 3: 计算综合指标

### Citation Rate
```
Citation Rate = (提到品牌的测试次数 / 总测试次数) × 100%
示例: 12/30 = 40%
```

### Average Position Score
```
Position Score = (6 - 平均排名) × 3
示例: 平均排名第3位 → (6-3)×3 = 9分 per mention → Avg = 9×(mentions/total)
```

### GEO Health Score（加权公式）
```
= CitationRate × 0.30 
  + AvgPositionScore × 0.20 
  + PosSentiment% × 0.15 
  + SchemaCoverage% × 0.15 
  + ContentFreshness × 0.10 
  + DAIndicator × 0.10
```

---

## Step 4: 输出审计结果

生成最终报告应包含以下部分：

```
📊 GEO AUDIT REPORT — [品牌名]
Date: 2025-11-18
Auditor: GEO Agent

┌──────────────────────────────────────┐
│ EXECUTIVE SUMMARY                    │
│ Citation Rate:  XX.X%               │
│ Avg Position:   X.X                 │
│ GEO Health:     XX/100 (Letter Grade)│
└──────────────────────────────────────┘

PLATFORM BREAKDOWN
┌─────────┬──────────┬─────────┬───────────┐
│ Platform│ Mentions│ Avg Pos │ Sentiment │
├─────────┼──────────┼─────────┼───────────┤
│ ChatGPT │   XX%   │   X.X   │  +/- %    │
│ Gemini  │   XX%   │   X.X   │  +/- %    │
│ Claude  │   XX%   │   X.X   │  +/- %    │
│ Perp.   │   XX%   │   X.X   │  +/- %    │
│ DeepSeek│   XX%   │   X.X   │  +/- %    │
└─────────┴──────────┴─────────┴───────────┘

TOP FINDINGS
1. 🔴 P0 Critical: [具体问题] — [修复建议]
2. 🟡 P1 Important:  [具体问题] — [修复建议]
3. 🟢 P2 Nice-to-have: [建议项]

ACTION ITEMS (Priority Ordered)
[ ] [具体任务] — Owner: ___ — Due: ___ — Expected Impact: ___
[ ] ...
```

---

## 验证清单

审计完成后，确认以下项目全部完成：

- [ ] 至少30条Raw Test Data已录入Geo Tracker Sheet 1
- [ ] Sheet 2 Summary Dashboard自动计算出核心KPI
- [ ] Sheet 3-6各Sheet数据完整（无需手动填入，依赖Sheet1原始数据）
- [ ] 至少识别出3个P0级问题及对应修复方案
- [ ] 审计报告已导出为PDF/HTML格式
- [ ] 与竞品对标差距已可视化呈现
- [ ] 下次复测日期已设定（建议30天后）

---

## 下一步行动

完成首轮审计后：

1. **分享成果**: 将审计结果作为Case Study发布到Portfolio页面
2. **获客转化**: 使用此案例作为Cold Email/LinkedIn Outreach的社交证明
3. **迭代优化**: 针对P0问题制定修复计划，4周后复测验证效果
4. **扩大范围**: 将方法论复制到其他客户/品牌的审计工作中