# GEO核心技术栈深度指南

## 一、结构化数据实施手册

### 1.1 JSON-LD 最佳实践

#### 核心原则
- **位置优先**：放在 `<head>` 或页面顶部，确保AI爬虫能第一时间解析
- **完整性检查**：使用 Google Rich Results Test 验证标记有效性
- **实体一致性**：同一实体的跨页面结构化数据必须保持一致

#### Article Schema 完整模板
```json
{
  "@context": "https://schema.org",
  "@type": "Article",
  "mainEntityOfPage": {
    "@type": "WebPage",
    "@id": "https://example.com/article-slug"
  },
  "headline": "文章主标题（包含核心关键词）",
  "description": "2-3句话摘要（AI提取的候选答案格式）",
  "image": ["https://example.com/featured-image.jpg"],
  "author": {
    "@type": "Person",
    "name": "作者姓名",
    "url": "https://example.com/author-profile",
    "sameAs": ["https://twitter.com/author", "https://linkedin.com/in/author"]
  },
  "publisher": {
    "@type": "Organization",
    "name": "品牌名称",
    "logo": {
      "@type": "ImageObject",
      "url": "https://example.com/logo.png"
    }
  },
  "datePublished": "2024-01-15T08:00:00+08:00",
  "dateModified": "2024-06-20T14:30:00+08:00",
  "wordCount": 2500,
  "inLanguage": "zh-CN",
  "keywords": ["关键词1", "关键词2", "关键词3"],
  "articleSection": "行业分类"
}
```

### 1.2 FAQ Schema 高阶技巧

#### AI问答友好结构
```json
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "什么是GEO优化？",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "GEO（Generative Engine Optimization）生成式引擎优化是一种针对AI搜索引擎的优化策略，通过结构化数据标记、可解释内容创作和权威性建设，让AI模型更准确、优先地引用品牌内容作为答案来源。"
      }
    },
    {
      "@type": "Question",
      "name": "GEO与SEO有什么区别？",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "传统SEO优化人类点击行为（CTR），GEO优化AI引用偏好。SEO关注排名前三，GEO关注被ChatGPT/Gemini等AI回答采纳；SEO看点击率，GEO看引用率和置信度分数。"
      }
    }
  ]
}
```

#### FAQ内容创作黄金法则
1. **问题简洁明确**：AI倾向提取简短直接的问题
2. **答案独立完整**：每个答案自成一体，避免依赖上下文
3. **长度控制在80-150字**：这是AI提取的理想范围
4. **使用列表和分步**：HowTo类型特别有效

### 1.3 Product Schema 电商应用

#### 产品信息结构化
```json
{
  "@context": "https://schema.org",
  "@type": "Product",
  "name": "产品名称",
  "description": "产品描述（2-3句话核心卖点）",
  "image": [
    "https://example.com/product-front.jpg",
    "https://example.com/product-side.jpg"
  ],
  "brand": {
    "@type": "Brand",
    "name": "品牌名"
  },
  "offers": {
    "@type": "Offer",
    "price": "99.99",
    "priceCurrency": "USD",
    "availability": "https://schema.org/InStock",
    "priceValidUntil": "2024-12-31",
    "seller": {
      "@type": "Organization",
      "name": "卖家名称"
    }
  },
  "aggregateRating": {
    "@type": "AggregateRating",
    "ratingValue": "4.7",
    "reviewCount": "1,250"
  },
  "review": [
    {
      "@type": "Review",
      "author": {"@type": "Person", "name": "Verified Buyer"},
      "reviewBody": "产品超出预期，质量很好",
      "reviewRating": {"@type": "Rating", "ratingValue": "5"}
    }
  ]
}
```

### 1.4 LocalBusiness 本地化应用

#### 本地商家结构
```json
{
  "@context": "https://schema.org",
  "@type": "LocalBusiness",
  "name": "企业名称",
  "image": "https://example.com/storefront.jpg",
  "@id": "https://example.com/#business",
  "url": "https://example.com",
  "telephone": "+1-555-123-4567",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "123 Main St",
    "addressLocality": "City Name",
    "addressRegion": "State",
    "postalCode": "12345",
    "addressCountry": "US"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": "40.7128",
    "longitude": "-74.0060"
  },
  "openingHoursSpecification": [
    {
      "@type": "OpeningHoursSpecification",
      "dayOfWeek": ["Monday", "Tuesday", "Wednesday", "Thursday", "Friday"],
      "opens": "09:00",
      "closes": "18:00"
    }
  ],
  "priceRange": "$$",
  "hasMap": "https://maps.google.com/?q=Business+Location",
  "servesCuisine": "Chinese",
  "paymentAccepted": "Cash, Credit Card",
  "foundingDate": "2020-01-01"
}
```

---

## 二、实体关系图谱构建

### 2.1 实体识别框架

#### E-E-A-T 信号强化
| 信号维度 | 实现方式 | 影响权重 |
|---------|---------|---------|
| Experience 经验 | 第一人称案例分享、用户生成内容 | 高 |
| Expertise 专业 | 作者资质展示、学术研究引用 | 极高 |
| Authoritativeness 权威 | 行业奖项、媒体报道、链接积累 | 极高 |
| Trustworthiness 可信 | SSL证书、隐私政策、明确的联系信息 | 高 |

### 2.2 Knowledge Graph 构建

#### 实体关系标注
```
[品牌] --is-brand-of--> [公司]
[品牌] --offers--> [产品类别A]
[品牌] --offers--> [产品类别B]
[产品A] --competes-with--> [竞品A]
[产品A] --features--> [功能特性1]
[产品A] --features--> [功能特性2]
[专家A] --writes-for--> [品牌]
[专家A] --cites-study--> [研究论文X]
[研究论文X] --published-in--> [学术期刊Y]
```

### 2.3 主题集群策略

#### Cluster Content 架构
```
Pillar Page（支柱页）："完整AI搜索优化指南"
├── Supporting Page 1："Schema标记技术详解"
│   ├── Sub-page 1a："JSON-LD语法规范"
│   └── Sub-page 1b："常见问题解答"
├── Supporting Page 2："内容可解释性优化"
│   ├── Sub-page 2a："FAQ结构设计"
│   └── Sub-page 2b："表格化呈现最佳实践"
└── Supporting Page 3："引用价值提升"
    ├── Sub-page 3a："数据来源透明度"
    └── Sub-page 3b："专家背书策略"
```

---

## 三、多模态内容优化

### 3.1 Image Optimization for AI Vision

#### 图像元数据增强
```json
{
  "@type": "ImageObject",
  "contentUrl": "https://example.com/chart-data.png",
  "description": "2024年AI搜索市场份额变化趋势图，显示ChatGPT占35%、Google AI Overview占28%",
  "caption": "全球主要AI搜索引擎市场份额对比",
  "representativeOfPage": true,
  "width": "1200px",
  "height": "800px"
}
```

#### 图像Alt Text 编写规则
1. **描述性而非关键词堆砌**：`"女性咖啡师正在制作拿铁艺术"` vs `"咖啡培训 咖啡课程 咖啡学校"`
2. **包含视觉细节**：颜色、动作、场景、情感
3. **上下文关联**：图片与周围文本的关系
4. **长度控制**：50-150字符最佳

### 3.2 Video Content Structuring

#### VideoObject Schema
```json
{
  "@context": "https://schema.org",
  "@type": "VideoObject",
  "name": "教程视频标题",
  "description": "视频详细描述（前30秒关键信息前置）",
  "thumbnailUrl": "https://example.com/thumbnail.jpg",
  "uploadDate": "2024-06-15T08:00:00Z",
  "contentUrl": "https://example.com/video.mp4",
  "embedUrl": "https://www.youtube.com/embed/VIDEO_ID",
  "duration": "PT15M30S",
  "interactionStatistic": {
    "@type": "InteractionCounter",
    "interactionType": {"@type": "WatchAction"},
    "userInteractionCount": 125000
  },
  "transcript": "视频完整文字稿...",
  "caption": [{"@type": "SpeechRecognition", "name": "自动字幕", "inLanguage": "zh"}]
}
```

---

## 四、权威性建设方法论

### 4.1 引用网络策略

#### 高引用率页面特征
| 特征 | 说明 | 目标值 |
|-----|------|--------|
| 引用密度 | 外部权威链接占比 | >15条/千字 |
| 信源多样性 | 不同来源机构数量 | ≥5种类型 |
| 时效性 | 近期文献占比 | >60%为近3年 |
| 数据可视化 | 图表/表格覆盖率 | >40%正文 |

### 4.2 学术级引用标注
```markdown
本研究结果得到以下支持：

1. Smith et al. (2023). *LLM Citation Patterns*. Nature Machine Intelligence.
   https://doi.org/10.xxxx/xxxxx
   
2. Johnson & Lee (2024). *Search Behavior in Generative Engines*. 
   Proceedings of WWW Conference.
   
3. World Economic Forum (2024). *Future of Search Report*.
   https://www.weforum.org/reports/future-search
```

### 4.3 Expert Signal Implementation

#### 作者权威性展示模板
```html
<div class="author-bio">
  <img src="/authors/john-doe.jpg" alt="John Doe, PhD" loading="lazy">
  <div class="credentials">
    <h3>John Doe, Ph.D.</h3>
    <p class="title">Senior Data Scientist at TechCorp</p>
    <ul class="achievements">
      <li>🎓 MIT Computer Science PhD (2015)</li>
      <li>📚 50+ peer-reviewed publications</li>
      <li>🏆 Webby Award for Data Visualization (2023)</li>
      <li>💼 Featured in Forbes 30 Under 30</li>
    </ul>
    <a href="/full-bio" class="more-link">Read Full Biography →</a>
  </div>
</div>
```

---

## 五、性能指标监控体系

### 5.1 AI可见度追踪仪表板

#### 核心监测维度
| 维度 | KPI | 测量方法 |
|-----|-----|---------|
| 引用率 | Brand Mentions/Query | 每日API调用统计 |
| 置信度 | Model Confidence Score | 模拟AI提问测试 |
| 排名位置 | Answer Position | 人工抽样验证 |
| 竞争差距 | Share of Voice | 竞品对比分析 |

### 5.2 A/B测试框架

#### 变量设置矩阵
```
Test Group A (Control):
- Current page structure
- Existing schema markup
- Baseline citation rate

Test Group B (Treatment):
- Enhanced FAQ section
- Added HowTo steps
- Expanded references

Metrics to Track:
- CTA extraction frequency
- Quote attribution accuracy  
- Time spent reading
- Scroll depth percentage
```

---

## 六、前沿技术预测

### 6.1 2025年技术趋势

| 趋势 | 说明 | 准备建议 |
|-----|------|---------|
| Multimodal RAG | 跨文本/图像/视频的检索增强生成 | 丰富多媒体内容资产 |
| Agent-based Search | 自主Agent完成复杂任务 | 提供可执行的API接口 |
| Personalized Ranking | 基于用户画像的个性化排序 | 建立用户分层数据模型 |
| Real-time Grounding | 实时事实核查机制 | 增强数据来源透明度 |

### 6.2 风险预警指标

#### 负面信号清单
- [ ] 引用准确率下降 >15%
- [ ] 模型置信度持续走低
- [ ] 竞争性引用反超对手
- [ ] 新鲜度评分降低

---

*本手册将持续更新，建议每周审查一次核心章节。*
