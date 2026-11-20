# GEO每日行动指南 - Day 3 实操启动

## 今日任务清单（预计4小时）

### 上午：技术配置阶段（2小时）

#### 9:00-9:30 | Google Search Console初始化
```
□ 访问 https://search.google.com/search-console
□ 添加网站属性（推荐URL前缀方式，与Analytics一致）
□ 完成域名验证（DNS TXT记录 或 HTML标签两种方式选其一）
□ 提交sitemap.xml（格式：<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9"><url><loc>https://yoursite.com</loc></url></urlset>）
□ 检查Coverage报告，确认无crawl errors
```

**诊断要点：**
- 重点关注"Coverage"标签页的错误和警告
- "Performance"数据需要至少24-48小时才能积累有效样本
- 手动请求爬虫索引新页面：Inspection工具 → Request Indexing

#### 9:30-10:00 | Google Analytics 4配置
```
□ 访问 https://analytics.google.com
□ 创建媒体资源（Media Resource），选择"网页"类型
□ 获取Measurement ID（G-XXXXXXXXXX格式）
□ 在网站<head>中插入全局站点代码(gtag.js)
□ 在Search Console中关联GA4账号
```

**关键事件设置：**
```javascript
// 自定义事件追踪示例
gtag('event', 'gei_signup', {
  method: 'email',
  engagement_time_msec: 45000  // 30秒+互动算深度阅读
});

gtag('event', 'schema_check', {
  page_section: 'faq',
  has_jsonld: true
});
```

#### 10:00-10:30 | Schema标记测试环境搭建
```
□ 选择一个现有页面作为测试目标（建议用FAQ或Article页面）
□ 复制页面HTML源码备份
□ 使用Google Structured Data Testing Tool验证当前状态
□ 添加第一个FAQPage schema标记
□ 重新验证并截图保存结果
```

**测试用Schema代码：**
```json
<script type="application/ld+json">
{
  "@context": "https://schema.org",
  "@type": "FAQPage",
  "mainEntity": [
    {
      "@type": "Question",
      "name": "什么是GEO优化？",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "GEO（生成式引擎优化）是优化内容使其被ChatGPT、Gemini等AI搜索引擎优先引用和展示的技术。核心包括结构化数据标记、权威性建立和内容可解释性优化。"
      }
    },
    {
      "@type": "Question",
      "name": "GEO和SEO有什么区别？",
      "acceptedAnswer": {
        "@type": "Answer",
        "text": "传统SEO优化人类点击行为，关注排名位置和CTR；GEO优化AI引用偏好，关注被AI回答采纳的概率和位置。两者有大量重叠但优化侧重点不同。"
      }
    }
  ]
}
</script>
```

---

### 下午：分析实践阶段（2小时）

#### 13:00-14:00 | AI搜索模拟测试
```
□ 使用以下查询模板测试自己的品牌：
  - "[你的品牌名] 是什么"
  - "best [你的行业] tools"
  - "[你的行业] vs competitor comparison"
  
□ 分别测试：ChatGPT、Gemini、Claude、DeepSeek
□ 记录：是否出现你的品牌？排名如何？引用了哪些页面？
□ 截图保存每个平台的搜索结果
```

**测试记录表：**
| 平台 | 品牌提及 | 引用页面 | 回答质量 | 竞争对比 |
|-----|---------|---------|---------|---------|
| ChatGPT | ☐有 ☐无 | ___ | ___/5 | vs ___ |
| Gemini | ☐有 ☐无 | ___ | ___/5 | vs ___ |
| Claude | ☐有 ☐无 | ___ | ___/5 | vs ___ |
| DeepSeek | ☐有 ☐无 | ___ | ___/5 | vs ___ |

#### 14:00-14:30 | 竞品GEO差距分析
```
□ 选择2-3个主要竞品
□ 对每个竞品执行同样的AI搜索测试
□ 填写竞品分析矩阵：
```

**竞品分析矩阵：**
| 评估维度 | 我方 | 竞品A | 竞品B | 差距分析 |
|---------|------|-------|-------|---------|
| FAQ覆盖度 | __% | __% | __% | ___ |
| Schema标记完整率 | __% | __% | __% | ___ |
| 权威外链数 | __ | __ | __ | ___ |
| 内容更新频率 | __次/周 | __次/周 | __次/周 | ___ |
| 视频资产数量 | __ | __ | __ | ___ |

#### 14:30-15:00 | 输出今日总结报告
```
□ 整理今天发现的问题清单
□ 按P0/P1/P2优先级排序
□ 制定下周改进计划
□ 将测试结果保存到知识库
```

---

## 今日产出物

### 必交作业
1. **Google Search Console截图** — 验证成功 + Sitemap提交成功
2. **Schema标记测试报告** — 通过Structured Data Testing Tool验证
3. **AI搜索测试记录表** — 5个平台各至少3个查询的测试结果
4. **竞品差距分析报告** — 至少2个维度的量化对比

### 可选进阶
- [ ] 录制一个5分钟屏幕录像，演示Schema添加过程
- [ ] 写一篇短文："我的第一个GEO实验经历了什么"
- [ ] 创建一个简单的GEO Checklist给未来的客户用

---

## 常见问题排查

### Q: Search Console验证失败怎么办？
**A:** 
1. 确认使用的是正确的域名（www vs non-www要区分）
2. DNS TXT验证需要等待5-10分钟传播
3. HTML标签验证需确保放置在`<head>`最顶部
4. Google Search Console帮助文档：https://support.google.com/webmasters/answer/9008080

### Q: Schema标记报错了怎么处理？
**A:**
1. 先运行Rich Results Test检查语法错误
2. 常见错误：缺少必填字段、类型不匹配、JSON格式问题
3. 使用JSONLint工具校验JSON格式
4. 参考Google开发者文档：https://developers.google.com/search/docs/appearance/structured-data

### Q: AI搜索测不到自己品牌正常吗？
**A:**
正常！对于新兴品牌/网站，这是普遍现象。重点观察：
- 是否有相关品类名称出现（哪怕不是精准品牌词）
- 竞品是否在AI回答中出现
- 这正好是你需要优化的方向

---

## 明日预告（Day 4）

明天将开始：
1. 学习使用Ahrefs/Semrush免费版进行关键词研究
2. 创建完整的GEO审计检查表
3. 实践一个真实的GEO项目诊断（可以用朋友的网站或公开案例）

---

*记住：理论只是地图，实操才是真正的旅行。今天的每一步都是在为明天的专业能力打底。*
