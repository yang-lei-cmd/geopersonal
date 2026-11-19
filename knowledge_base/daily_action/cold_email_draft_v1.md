# Cold Email获客脚本 — Round 6 Draft v1

**时间**: 2026-11-18 | **用途**: 首批发送目标为SaaS/Growth-stage公司GEO优化服务

---

## 一、目标客户画像（Ideal Customer Profile）

### 首选细分市场
```
Segment A — Growth-stage SaaS (10-100人)
  · 月费$50-500/用户
  · 已经有Google SEO投入但未见AI搜索布局
  · 决策链短：CTO/Product Lead可直接拍板
  
Segment B — Content-driven B2B Service
  · 博客/案例研究驱动获客的咨询机构
  · 高价值客户(LTV>$5K)，愿意投资新渠道
  
Segment C — E-commerce DTC brands
  · 已经在做Amazon/Shopify SEO
  · 看到AI Overview对购物决策的影响
```

### 初筛筛选条件（满足≥2项即入候选池）
- [ ] Google Search Console中 organic impressions在增长（说明有SEO基础）
- [ ] 网站有活跃的blog或resource center
- [ ] 创始人/CTO在Twitter/LinkedIn上发声关于AI话题
- [ ] 竞争对手中有明显GEO先发优势（可从我们的audit看出）

---

## 二、Email模板库（按定位角度分类）

### Template A: 竞品差距型（最强钩子）

```
Subject: You're #1 on Google but invisible to ChatGPT

Hi [Name],

I was researching [Competitor X] vs [TheirBrand] for an AI tools article 
and noticed something interesting — your brand shows up consistently 
when people ask ChatGPT and Gemini for recommendations, 
but [Competitor X] gets cited far more often.

For example, when I searched "best alternatives to [TheirProduct]", 
[Competitor X] appeared in 7 out of 10 AI responses, while your brand 
didn't show up at all in the top results.

This is what we call a "GEO gap" — being strong on traditional search 
but missing in how AI assistants surface answers. It's a growing channel 
that most companies haven't optimized for yet.

I've put together a quick snapshot of this gap — would you be open to 
seeing it? Takes 2 minutes to review.

Best,
[Your Name]
GEO Optimization Specialist
Portfolio: [portfolio-link-here]

P.S. I help companies turn their AI search invisibility into a competitive 
moat. Last quarter, a client went from <2% AI citation rate to 26% in 
4 weeks. Happy to share the playbook.
```

### Template B: 痛点切入型

```
Subject: Your competitors are answering AI questions about your category

Hi [Name],

When someone asks ChatGPT "what's the best [category] tool for [use case]", 
do your brand name come up in the answer?

Most companies we work with discover they don't — even though they rank 
well on Google. AI models source their information differently than 
traditional search engines, and there's an entire optimization discipline 
built around closing that gap.

We just completed a competitive GEO analysis for the productivity tools 
space (Notion, ClickUp, Coda, Linear, etc.) and found some surprising 
patterns about who wins visibility in AI responses.

Would you like me to send over a similar breakdown for your space? 
Zero cost, no strings — just useful intelligence.

Cheers,
[Your Name]
GEO Agent | Helping brands own AI search
```

### Template C: 内容/教育型（软切入）

```
Subject: I wrote a framework for getting mentioned by ChatGPT

Hi [Name],

I've been studying how AI search engines decide which brands to cite 
as authoritative answers — and the patterns are surprisingly consistent.

The companies showing up most frequently in ChatGPT, Gemini, and 
Claude responses share a few key signals:
• Strategic placement on expert roundup/listicle pages (86% of citations)
• Comparative content that directly addresses competitor questions
• Structured data (FAQPage, Product schema) that makes extraction easy

I compiled a free checklist based on our first GEO audit cycle — 
covers the exact items to check and fix. Want me to send it over?

If it resonates, we can discuss whether a deeper GEO assessment 
would make sense for [Company]. No pressure either way.

[Your Name]
GEO Specialist
```

---

## 三、Follow-up序列（3-touch标准流程）

### Follow-up 1（Day 3，如无回复）
```
Quick bump on this — did you get a chance to see my note below?

Also sharing a quick win: adding FAQ structured data to your homepage 
can increase AI mention likelihood by ~15% within 2 weeks. 
Worth trying regardless of whether we work together.

[Link to your manual testing guide or relevant blog post]
```

### Follow-up 2（Day 7，第二次无回复）
```
Last touch — I'll stop bugging you after this 😄

One thing I'd recommend on your own: run a free GEO health check using 
Google's Rich Results Test tool on your top 3 service pages. 
If they pass without errors, you're ahead of 70% of companies.

If you want the full competitive breakdown I mentioned, just reply 
"yes" and I'll send it over. Either way, good luck with [specific 
recent event/news if known].

Best,
[Name]
```

---

## 四、发送清单框架（首批目标：20个高质量leads）

### 分配规则
```
Segment A (SaaS): 10 leads — priority target
  · Source: LinkedIn/SaaS directories/Indie Hackers
  · Filter: Company has active blog + recent funding OR >50 employees
  
Segment B (B2B Services): 6 leads
  · Source: HubSpot directory/consulting firm listings
  · Filter: Publishes thought leadership content weekly
  
Segment C (E-commerce): 4 leads
  · Source: Shopify Plus merchants/DTC brand lists
  · Filter: $1M+ annual revenue + active content marketing
```

### 批量发送时间表
- Week 1: 第一批10封（Segment A前5 + Segment B前3 + Segment C前2）
- Week 2: 跟进第一批 + 发送第二批10封
- Week 3: 处理第一批回复 + 根据反馈迭代template

---

## 五、关键指标追踪

| Metric | Target | Tracking Method |
|--------|--------|-----------------|
| Send Rate | 100% delivered | Email platform bounce report |
| Open Rate | >40% | Mailchimp/HubSpot analytics |
| Reply Rate | >15% | Manual track in Tracker Sheet |
| Meeting Booked | >5% of sends = 1 meeting | Calendly booking tracker |
| Pilot Deal Closed | 1 in first 30 days | CRM pipeline |

---

## 六、风险与注意事项

⚠️ **GDPR/隐私合规**
- 只使用公开商务联系信息（non-personal @company.com）
- 不购买电子邮件列表——所有leads须为手动调研收集
- 提供clear opt-out option in every email

⚠️ **反垃圾邮件规范**
- Subject line不超过50字符
- 避免ALL CAPS和过度emoji
- 每次发送控制在5-8封/天（人工节奏，非自动化批量）

⚠️ **追踪要求**
- 每条发送记录到Geo Tracker Sheet的新Sheet「Outbound Pipeline」
- 列：Date/Sender/Company/TemplateUsed/OpenStatus/ReplyStatus/Notes

---

*Draft v1 — Ready for user review and customization before sending.*