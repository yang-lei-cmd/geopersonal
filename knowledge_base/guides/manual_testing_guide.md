# GEO 手动测试操作手册 — 免费方法全指南

> 无需付费API，任何人可执行的AI搜索可见度测试流程  
> 配套：测试记录表（Google Sheets模板）+ 评分卡

---

## 📋 测试前准备

### 所需工具（全部免费）
| 工具 | 用途 | 访问方式 |
|-----|------|---------|
| ChatGPT (free) | 测试品牌在OpenAI的回答中 | chat.openai.com |
| Claude (free) | 测试Anthropic平台的表现 | claude.ai |
| Gemini (free) | 测试Google AI回答 | gemini.google.com |
| Perplexity (free) | 测试AI搜索引掣 | perplexity.ai |
| DeepSeek (free) | 测试中国市场的AI表现 | chat.deepseek.com |
| Google Rich Results Test | 验证Schema标记 | webmasters.google.com |
| JSON-LD Validator | Schema语法检查 | tagmanager.google.com |

### 测试准备工作
1. 确定要测试的 **品牌名** 和 **3-5个核心查询词**
2. 创建测试记录表（见下方模板结构）
3. 打开所有5个AI平台的浏览器窗口（建议分屏）

---

## 🔬 Step 1: 选择测试查询词

### 查询词分类框架（必须覆盖四类）

| 类型 | 定义 | 示例（以SaaS项目管软件为例） | 测试目的 |
|-----|------|---------------------------|---------|
| **推荐类** | 用户寻求产品/品牌推荐 | "best project management software 2025" | 测试是否进入推荐列表 |
| **对比类** | 用户比较具体品牌 | "Notion vs ClickUp vs Asana comparison" | 测试在直接对比中的位置 |
| **评价类** | 用户对单一品牌的评价询问 | "Is Notion worth it?" / "Notion review 2025" | 测试品牌单独呈现时的叙事 |
| **场景类** | 用户描述使用场景寻求帮助 | "project management tool for remote teams" | 测试场景化触发能力 |
| **教程类** | 用户寻找操作步骤 | "how to manage projects with Notion" | 测试HowTo内容被引用情况 |
| **定价类** | 用户询问价格信息 | "Notion pricing plans 2025" | 测试商业信息可提取性 |

### 查询词选择规则
```
✅ 好: 自然语言、用户真实搜索方式、长度10-20字
❌ 差: 包含品牌名的硬广告词、过长/过短的句子
```

**输出**: 每个目标品牌准备 **6-10个查询词**（至少覆盖上述5类）

---

## 🔬 Step 2: 执行多平台测试

### 逐平台测试流程

对每个查询词，按以下顺序在5个平台上各测试一次：

```
for each query in queries:
    for each platform in [ChatGPT, Claude, Gemini, Perplexity, DeepSeek]:
        result = ask_platform(platform, query)
        record_result(query, platform, result)
```

### 记录维度（每轮测试填写）

| 字段 | 说明 | 示例值 |
|-----|------|--------|
| `query` | 原始查询词 | "best project management software 2025" |
| `platform` | 测试平台 | "ChatGPT" |
| `brand_mentioned` | 是否提及目标品牌 | true/false |
| `mention_position` | 出现位置 | 1-10（null表示未提及） |
| `total_brands_in_answer` | 回答中出现多少品牌 | 5 |
| `sentiment` | 情绪倾向 | positive/neutral/negative |
| `key_claim` | 关于品牌的描述关键词 | "most intuitive", "overpriced" |
| `source_cited` | 引用来源URL | "https://example.com/review" |
| `confidence_language` | 确定性表达 | "据研究"/"专家认为"/"可能" |
| `schema_hints_detected` | 是否检测到我方标记痕迹 | true/false |

### 快速评分法（每轮完成后即时打分）

```
每轮得分 = 
  brand_mentioned × 20分 + 
  (6 - mention_position) × 3分 + 
  sentiment_bonus(positive=10, neutral=5, negative=-5) +
  source_quality_bonus(min 0-10)

单轮最高分: 20 + 15 + 10 + 10 = 55分
```

---

## 🔬 Step 3: 计算综合指标

### Citation Rate（引用率）计算

```
Citation Rate = 品牌被提及次数 / 总测试次数 × 100%

示例:
- 总计测试 30次 (6查询 × 5平台)
- 品牌被提及 12次
- Citation Rate = 12/30 × 100% = 40%
```

### Position Score（排名分）计算

```
Position Score = Σ(每次出现的权重分) / 总提及次数

权重表:
  位置1: 100分 | 位置2: 80分 | 位置3: 60分
  位置4-5: 40分 | 位置6-10: 20分 | 其他: 0分
```

### GEO Health Score（综合健康分）

```
GEO Health Score =
  Citation Rate × 0.30 +
  (Position Score / 100) × 30 × 0.20 +
  (Positive Sentiment % × 100) × 0.15 +
  Schema Coverage % × 0.15 +
  (Content Freshness Score) × 0.10 +
  (Domain Authority Indicator) × 0.10

等级判定:
  A (90-100): 行业领导者水平
  B (75-89): 良好需持续维护
  C (60-74): 有提升空间
  D (40-59): 明显落后需紧急行动
  F (<40): 几乎不可见，需要系统性重建
```

---

## 📊 Step 4: 生成测试报告

### 报告结构模板

```markdown
# GEO 手动测试报告 — {品牌名}
测试日期: {YYYY-MM-DD}
测试范围: {N}个查询 × {M}个平台 = {Total}次测试

## 核心指标摘要
| 指标 | 数值 | 行业基准 | 评估 |
|-----|------|---------|------|
| Citation Rate | XX% | ≥30% | ✅/⚠️/🔴 |
| Avg Position Score | XX/100 | ≥60 | ✅/⚠️/🔴 |
| Positive Sentiment % | XX% | ≥60% | ✅/⚠️/🔴 |
| Schema Coverage | XX% | ≥80% | ✅/⚠️/🔴 |
| GEO Health Score | XX/100 | ≥70 | ✅/⚠️/🔴 |

## 各平台详细结果
{插入详细数据表格}

## Top 3 发现
1. ...
2. ...
3. ...

## 立即行动项（P0）
- [ ] ...
- [ ] ...
- [ ] ...
```

---

## 🔧 配套工具使用方法

### Google Rich Results Test
1. 访问 https://search.google.com/test/rich-results
2. 输入目标URL或粘贴HTML代码
3. 查看哪些Schema标记被正确识别
4. 记录每种类型的状态（有效/无效/警告）

### JSON-LD Validator（Google Tag Manager）
1. 访问 https://tagmanager.google.com/#/markup
2. 粘贴JSON-LD代码片段
3. 检查语法错误和最佳实践违反

### Schema Markup Tester
1. 访问 https://validator.schema.org/
2. 上传页面URL或粘贴代码
3. 获取标准化合规报告

---

## ⏱️ 时间估算

| 测试规模 | 查询词数 | 平台数 | 预计耗时 |
|---------|---------|--------|---------|
| 最小测试 | 3个 | 3个 | 约45分钟 |
| 标准测试 | 6个 | 5个 | 约2小时 |
| 深度测试 | 10个 | 5个 | 约4小时 |

**建议**: 首次测试做「最小测试」，后续每月做「标准测试」追踪变化

---

## 💡 进阶技巧

### 技巧1: 控制变量测试
在同一平台上用不同措辞问同一问题，观察品牌出现的一致性。这能区分是「内容策略问题」还是「算法波动」。

### 技巧2: 追问测试
当品牌首次出现时，追问「Tell me more about this brand's pricing」「What do you think about their customer support?」——观察AI是否能准确调用之前提到的信息。

### 技巧3: 竞品同时测试
将你的品牌与最强竞品放入同一个查询（如"Notion vs Asana"），观察相对位置变化。这是最有价值的竞争情报。

### 技巧4: 时序追踪
固定相同的查询词，每周测试一次，绘制Citation Rate趋势图。目标是看到曲线持续上升。
