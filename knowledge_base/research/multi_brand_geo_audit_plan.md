# 多品牌横向GEO审计计划 — Productivity工具竞争格局分析

**时间**: 2026-11-18 | **执行者**: GEO Agent | **目标**: 建立Productivity工具赛道AI搜索可见度全景图

---

## 一、选品逻辑与竞品矩阵

### 选定品牌（基于市场覆盖度和公开可测性）

| Brand | URL | Positioning | Why Chosen |
|-------|-----|-------------|------------|
| **Notion** | notion.so | All-in-one workspace | ✅已审计，作为基准(Baseline) |
| **Coda** | coda.io | Document-powered apps | Direct competitor, different positioning |
| **ClickUp** | clickup.com | Project management | Largest free tier, high SEO investment |
| **Linear** | linear.app | Issue tracking | Premium positioning, design-focused |
| **Anytype** | anytype.io | Local-first knowledge | Emerging challenger, different architecture |

### 统一查询词池（10个 × 5平台 = 50次/品牌 → 250次总测试）

```
Q1: "best note taking app"          [Recommendation]
Q2: "notion vs clickup vs coda"     [Comparison]  
Q3: "best project management tool" [Recommendation]
Q4: "how to use notion for team collaboration" [Tutorial]
Q5: "clickup pricing"               [Pricing]
Q6: "what is linear app used for"   [Definition/Scenario]
Q7: "alternatives to notion 2025"   [Alternative - P0 gap identified]
Q8: "switch from notion to clickup" [Migration/Decision]
Q9: "best ai powered workspace"    [AI Feature query]
Q10: "notion alternative for developers" [Niche vertical]
```

---

## 二、审计设计规格

### 平台选择（与Notion审计一致，保持数据可比性）
- ChatGPT (chatgpt.com) — Global leader
- Gemini (gemini.google.com) — Rising fast, 35% share in cold-start test
- Claude (claude.ai) — High-intent enterprise users
- Perplexity (perplexity.ai) — Research-focused, conversion surprise found
- DeepSeek (deepseek.com) — China market opportunity (Notion tested 80% SR)

### 评分标准（沿用Notion审计框架）
```
每平台×每查询打分维度：
- Mentioned? 是/否 → 1分
- Average position if mentioned → /5 (第1位=5分, 第2位=4分...)
- Positive sentiment → +2分, Neutral → +1分, Negative → 0分
- Schema hints detected → +1分
- Score range: 0-9 per test, Total max = 90 per brand
```

### 输出格式
每个品牌生成独立审计报告(.md)，最后生成横向对比汇总报告+竞争热力图(.html)

---

## 三、执行节奏与预计耗时

| Phase | 内容 | 预计耗时 |
|-------|------|---------|
| Phase A | Notion基准数据复核(快速验证) | 30分钟 |
| Phase B | Coda完整审计 | 45分钟 |
| Phase C | ClickUp完整审计 | 45分钟 |
| Phase D | Linear完整审计 | 45分钟 |
| Phase E | Anytype完整审计 | 45分钟 |
| Phase F | 横向汇总报告+热力图HTML | 60分钟 |
| **总计** | | **约5小时** |

### 分批执行建议
- Day 1: Phase A+B+C (Notion复核 + Coda + ClickUp) — 14:00~18:00
- Day 2: Phase D+E+F (Linear + Anytype + 汇总) — 10:00~14:00

---

## 四、预期产出物

1. `deliverables/coda_geo_audit_report.md` — Coda独立审计
2. `deliverables/clickup_geo_audit_report.md` — ClickUp独立审计
3. `deliverables/linear_geo_audit_report.md` — Linear独立审计
4. `deliverables/anytype_geo_audit_report.md` — Anytype独立审计
5. `deliverables/productivity_geo_competitive_landscape.html` — 交互式竞争全景图

### 竞争格局HTML报告包含
- 5品牌×10查询的citation rate热力图
- GEO Health Score排名排行榜
- 各平台share分布雷达图
- 各品牌的P0/P1差距类型对比矩阵
- "最佳差异化机会"推荐（空白查询词识别）

---

## 五、风险与缓解

| 风险 | 影响 | 缓解策略 |
|------|------|---------|
| 某些AI平台限流/fail | 部分查询无数据 | 记录空值，不重测；用已有数据估算 |
| Notion测试耗时过长(50条) | 挤压其他品牌时间 | 先完成新品牌4个，再做Notion复核 |
| 同一查询结果波动大 | 分数不稳定 | 取两轮平均值作为最终得分 |
| DeepSeek API配额不足 | 中国区数据缺失 | 跳过DeepSeek专项测试，用其他4平台推算 |

---

## 六、后续利用场景

1. **免费赠品**：将完整版竞争格局报告作为Lead Magnet放在Portfolio页面
2. **Cold Email钩子**："我们发现您在[特定查询]上的AI可见度比竞争对手低X%"
3. **定价依据**：基于竞品Gap量化客户改进空间，支撑$5K-$15K/季报价合理性
4. **内容素材**：每轮审计发现可转化为LinkedIn/Twitter内容点
