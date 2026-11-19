# GEO Execution Tracker — 项目执行追踪表

> 配套 Google Sheets / Excel 模板结构说明  
> 使用方法：复制下方列定义，填入实际测试数据即可自动计算KPI

---

## Sheet 1: Raw Test Data（原始测试数据）

| A列 | B列 | C列 | D列 | E列 | F列 | G列 | H列 | I列 | J列 | K列 | L列 | M列 | N列 |
|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|-----|
| Date | Brand | Query | Platform | Mentioned | Position | Total Brands | Sentiment | Key Claim | Source URL | Confidence | Schema Hints | Score | Notes |
| 2025-11-18 | TechFlow | best project mgmt software | ChatGPT | True | 3 | 5 | Positive | "most intuitive UI" | notion.so | High | FAQPage ✅ | 35 | 出现第3位推荐 |
| 2025-11-18 | TechFlow | best project mgmt software | Gemini | False | null | 6 | neutral | — | — | Medium | FAQ ❌ | 0 | 未出现在前5 |
| 2025-11-18 | TechFlow | Notion vs ClickUp comparison | Claude | True | 2 | 4 | Positive | "better collaboration features" | techflow.io/blog | High | Article ✅ | 47 | 被直接引用原文段落 |

### 列说明
- **Score计算**: `=IF(B2="",0, (IF(E2="True",20,0) + (6-F2)*3) + IF(G2="Positive",10,IF(G2="Neutral",5,-5)) + IF(J2<>"",10,0))`
- Position范围1-10；null或空表示未提及
- Sentiment: Positive / Neutral / Negative
- Confidence: High / Medium / Low

---

## Sheet 2: Summary Dashboard（汇总看板）

| Metric | Formula | Value | Target | Status |
|--------|---------|-------|--------|--------|
| Citation Rate % | `COUNTIF(Raw!E:E,"True")/COUNTA(Raw!D:D)*100` | #N/A | ≥30% | ⚪ |
| Avg Position Score | `AVERAGE(IF(Raw!E:E="True",(6-Raw!F:F)*3,0))` | #N/A | ≥60 | ⚪ |
| Positive Sentiment % | `COUNTIFS(Raw!H:H,"Positive")/COUNTIF(Raw!E:E,"True")*100` | #N/A | ≥60% | ⚪ |
| Schema Coverage % | `COUNTIFS(Raw!L:L,"*✅*")/COUNTA(Raw!L:L)*100` | #N/A | ≥80% | ⚪ |
| GEO Health Score | 综合公式见下 | #N/A | ≥70 | ⚪ |

### GEO Health Score 公式
```
= (CitationRate/100*0.30) + (AvgPositionScore/100*0.20) + (PosSentiment/100*0.15) 
  + (SchemaCoverage/100*0.15) + (ContentFreshnessScore*0.10) + (DAIndicator*0.10)
```

等级判定：≥90=A | ≥75=B | ≥60=C | ≥40=D | <40=F

---

## Sheet 3: Platform Comparison（分平台对比）

| Platform | Tests | Mentions | Citation % | Avg Position | Avg Sentiment | Avg Score | Trend |
|----------|-------|----------|-----------|-------------|---------------|-----------|-------|
| ChatGPT | =COUNTIFS(Raw!D:D,A2) | =COUNTIFS(Raw!D:D,A2,Raw!E:E,"True") | =B2/C2*100 | =AVERAGEIFS(...) | =AVERAGEIFS(...) | =AVERAGEIFS(...) | → |
| Gemini | ... | ... | ... | ... | ... | ... | → |
| Claude | ... | ... | ... | ... | ... | ... | → |
| Perplexity | ... | ... | ... | ... | ... | ... | → |
| DeepSeek | ... | ... | ... | ... | ... | ... | → |

---

## Sheet 4: Monthly Trend（月度趋势追踪）

| Month | Citation Rate | Pos Score | Sentiment % | GEO Score | Δ Last Month |
|-------|--------------|-----------|-------------|-----------|-------------|
| 2025-M10 | 12% | 42 | 55% | 58 (C) | — |
| 2025-M11 | 18% | 55 | 62% | 68 (C+) | ↑ +10 |
| 2025-M12 | #待填 | #待填 | #待填 | #待填 | #待填 |

**Trend Rule**: 连续3个月上升 = ✅ Strategy working | 连续下降 = 🔴 Pivot needed

---

## Sheet 5: Query Type Analysis（查询类型分析）

| Query Type | Count | Mention Rate | Avg Position | Best Platform | Action Needed |
|-----------|-------|-------------|-------------|--------------|---------------|
| Recommendation | # | ##% | #.# | ### | [Action] |
| Comparison | # | ##% | #.# | ### | [Action] |
| Review/Eval | # | ##% | #.# | ### | [Action] |
| Scenario-based | # | ##% | #.# | ### | [Action] |
| Tutorial/HowTo | # | ##% | #.# | ### | [Action] |
| Pricing | # | ##% | #.# | ### | [Action] |

---

## Sheet 6: Competitor Benchmark（竞品对标）

| Brand | Citation Rate | Avg Position | Geo Score | Top Platforms | Gap vs Us |
|-------|--------------|-------------|-----------|--------------|-----------|
| OurBrand | 12% | 3.4 | B+ | Claude/ChatGPT | — |
| CompetitorA | 28% | 1.8 | A | All 5 | ↑ +16pp |
| CompetitorB | 22% | 2.2 | A- | ChatGPT/Claude | ↑ +10pp |
| CompetitorC | 8% | 4.1 | C | Gemini only | ↓ -4pp |

**Gap Analysis**: 每个竞品差距 >5pp → P1行动项 | 差距 ≤5pp → P2持续监测

---

## 使用流程（每月一次完整周期）

```
Week 1: 完成Sheet 1 Raw Test Data录入（至少30条记录）
         ├─ 6个查询 × 5个平台 = 30次测试
         └─ 每轮测试后即时填写评分和备注

Week 2: Sheet 2-4 自动生成 + 团队review会议
         ├─ 计算本月各项KPI指标
         ├─ 与上月数据对比看趋势
         └─ 识别Top 3优先级改进项

Week 3: Sheet 5-6 深度分析
         ├─ 按查询类型拆解表现
         ├─ 竞品差距可视化
         └─ 制定下月优化策略

Week 4: 输出月度GEO报告（PDF/HTML）
         ├─ 执行摘要（2页）
         ├─ 详细数据附录
         └─ 行动计划与资源需求
```

---

## 数据质量检查清单

录入前确认：
- [ ] 所有URL可访问且为最新内容
- [ ] 情绪判断有原文依据（标注具体引述）
- [ ] Position记录精确到首次出现位置
- [ ] Schema检测基于Rich Results Test官方工具结果
- [ ] 同一查询在同一平台不重复记录（除非故意测试变化）