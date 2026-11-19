# GEO Implementation Checklist — 从0到1的完整实施方案

> 适用于第一次接手GEO项目的顾问/自由职业者  
> 每个阶段包含：目标、任务清单、验收标准、预计工时

---

## Phase 1: Discovery & Audit（发现与审计）— Week 1

### 1.1 Client Intake（客户入职）
- [ ] 完成Client Intake Form（12题需求调研问卷，来自client_acquisition.md）
- [ ] 收集客户网站URL、主要竞争对手列表、核心业务关键词
- [ ] 了解客户当前SEO/GEO现状和已尝试的方法
- [ ] 确认客户目标和预期时间线
- [ ] **验收标准**: 签署服务合同 + 获得网站访问权限

### 1.2 Technical Foundation Audit（技术基础审计）
- [ ] 运行Google Rich Results Test扫描首页+核心 landing pages（至少5个URL）
- [ ] 检查SSL证书有效性
- [ ] 运行PageSpeed Insights检测Core Web Vitals（目标：LCP<2.5s, INP<200ms, CLS<0.1）
- [ ] 检查移动端适配（Google Mobile-Friendly Test）
- [ ] 验证sitemap.xml存在且格式正确
- [ ] 检查robots.txt是否有屏蔽问题
- [ ] **验收标准**: 技术评分 ≥ 60/100，明确列出需修复的P0问题

### 1.3 Current GEO Baseline（GEO基线测量）
- [ ] 确定6-10个核心查询词（覆盖5类）
- [ ] 在5个AI平台上逐一执行手动测试（使用manual_testing_guide.md方法）
- [ ] 录入Geo Tracker（Sheet 1），计算初始基线指标
- [ ] 竞品同时测试（选择3个最强竞品做交叉对比）
- [ ] **验收标准**: 完成至少30条Raw Test Data记录，产出Base-line Score卡

---

## Phase 2: Quick Wins（快速见效）— Week 2

### 2.1 Schema Markup Implementation（Schema标记实施）
- [ ] 优先添加FAQPage Schema至FAQ页面（最高ROI标记类型）
- [ ] 为核心Product/Service页面添加Product Schema
- [ ] 添加Article Schema至博客文章（含Author + DatePublished）
- [ ] 添加HowTo Schema至教程/步骤型内容
- [ ] 使用JSON-LD格式，确保位于<head>内
- [ ] **验收标准**: Schema覆盖率 ≥ 80%，Rich Results Test全部通过

### 2.2 Content Direct Answer Optimization（内容直接回答优化）
- [ ] 为每个核心landing page重写首段（前50字必须直接回答问题）
- [ ] 在文章顶部添加TL;DR摘要框（2-3句话）
- [ ] 确保每篇文章包含至少1个FAQ section（匹配People Also Ask格式）
- [ ] 添加内部链接到新优化的FAQ/HowTo页面
- [ ] **验收标准**: 平均首段答案相关度提升（主观评估 → 客观测试验证）

### 2.3 Entity Connection Strengthening（实体关联强化）
- [ ] 创建About页面完善Organization schema（含sameAs社交链接）
- [ ] 创建Expert Author bios页面（Person schema + credentials展示）
- [ ] 在核心文章中引用权威来源（学术机构、行业报告、知名媒体）
- [ ] 添加Google Knowledge Graph提及请求（如有资格）
- [ ] **验收标准**: Organization实体在AI回答中的关联强度提升

---

## Phase 3: Content Strategy（内容战略）— Week 3-4

### 3.1 Pillar Content Creation（支柱内容创作）
- [ ] 确定1个Pillar Topic（品牌最核心的主题领域）
- [ ] 创作3,000+字的Comprehensive Guide文章
- [ ] 内嵌Article + FAQ + HowTo多种Schema
- [ ] 创建2-3篇Supporting Cluster Articles（链接回Pillar）
- [ ] **验收标准**: Pillar page在目标查询中出现于前3名推荐

### 3.2 Authority Building（权威性建设）
- [ ] 提交3篇Guest Post至DA50+行业媒体
- [ ] 设置HARO订阅，每周响应≥5次专家咨询
- [ ] 创建1个原创研究报告/Data Asset（可被引用的高质量数据）
- [ ] 在Reddit/Hacker News/知乎进行专业回答（建立个人品牌）
- [ ] **验收标准**: 每月新增外部引用链接≥5个

### 3.3 Multi-Platform Consistency（多平台一致性）
- [ ] 统一各平台品牌名称、描述、logo（保持一致性信号）
- [ ] 在LinkedIn/Twitter发布品牌相关内容增加实体关联
- [ ] 监控DeepSeek中文市场覆盖缺口并针对性补充
- [ ] **验收标准**: 在所有5平台达到一致的Citation Rate ≥ 20%

---

## Phase 4: Measurement & Iteration（测量与迭代）— Ongoing

### 4.1 Weekly Testing Cadence（每周测试节奏）
- [ ] 周一：执行6个核心查询的快速测试（每平台1次）
- [ ] 周三：对弱势查询类型进行补充测试
- [ ] 周五：更新Geo Tracker，生成周报
- [ ] **验收标准**: 每周新增测试记录 ≥ 35条

### 4.2 Monthly Deep Analysis（每月深度分析）
- [ ] 完成Sheet 2-6全部数据分析
- [ ] 生成月度GEO Report PDF
- [ ] 与上月数据对比，计算Δ值
- [ ] 制定下月优化策略（Top 3行动项）
- [ ] **验收标准**: 每月GEO Health Score提升 ≥ 5分

### 4.3 Quarterly Strategy Review（每季度策略复盘）
- [ ] 回顾12个月学习路线图进度
- [ ] 重新评估竞争格局变化
- [ ] 调整Query词库（移除失效词，添加新兴热词）
- [ ] 向客户汇报季度成果和价值证明
- [ ] **验收标准**: 季度Citation Rate提升 ≥ 10pp，或GEO Score升级 ≥ 1个等级

---

## 关键里程碑检查点

```
Milestone 1 (Week 1 end):   Baseline score卡完成 → 知道现在在哪
Milestone 2 (Week 2 end):   Schema覆盖率 ≥ 80% → 技术障碍清除
Milestone 3 (Week 4 end):   First content deployed → 第一波优化生效
Milestone 4 (Month 2 end):  Citation Rate ≥ 20% → 进入可见区间
Milestone 5 (Month 3 end):  GEO Score ≥ 70 (B级) → 达到行业合格线
Milestone 6 (Month 6 end):  Citation Rate ≥ 35%, GEO Score ≥ 80 (B+) → 超越平均水平
```

---

## Risk Mitigation（风险缓解）

| 风险 | 概率 | 影响 | 缓解措施 |
|-----|------|------|---------|
| AI平台算法突变 | 中 | 高 | 保持多平台分散策略；月度策略review |
| 内容发布延期 | 低 | 中 | Buffer时间预留；提前储备3篇备用内容 |
| 竞品加速跟进 | 中 | 中 | 持续监测SOV-AI；差异化定位坚持 |
| 预算超支 | 低 | 中 | 阶段验收+按需追加预算 |
| API工具配额不足 | 高* | 低 | 依赖手动测试手册作为主要手段 |

*注：本计划设计以零付费API为前提，即使工具受限也能执行核心工作。

---

## Deliverables Checklist（最终交付清单）

项目结束时确保以下文件完整归档：

- [ ] GEO Audit Report (HTML/PDF)
- [ ] Schema Markup Implementation Log
- [ ] Geo Tracker Full Dataset (≥90天记录)
- [ ] Monthly Reports × N
- [ ] Final Impact Assessment Report
- [ ] Client Handoff Document (操作手册 + 维护指南)
