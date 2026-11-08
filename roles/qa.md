---
role: qa
title: 测试 / QA / 质量工程师
version: 1.2.0
---

# 测试工程师 Rubric v1.1.0

## 10 秒看什么
- 质量结果信号（逃逸、回归时间、发布信心）强于「写了多少用例」  
- 自动化是否连到 CI/关键路径  
- 通用成就化与 ATS（G-ACCOMPLISH / ATS-*）

## 必须证据

| ID | 必须证据 | 可观察检查 | 出处与证据等级 |
|----|----------|------------|----------------|
| QA-METRICS | 使用有意义的质量指标（如逃逸缺陷、周期时间），避免虚荣指标 | 是否出现 escape/回归时长/严重缺陷等 | Sauce Labs《QA Metrics That Matter…》https://saucelabs.com/resources/blog/the-qa-metrics-worth-tracking-and-the-ones-to-ignore｜TestRail《Top 20 QA Metrics…》https://www.testrail.com/blog/qa-metrics-matter/｜**一手（质量工程厂商/工具商）**——面向度量体系，非「简历写法」专文 |
| QA-AUTO | （综合）自动化与效率结果绑定 | 有无回归时长前后对比或 CI 闸门 | 将 QA-METRICS 落到简历的操作化｜**本 skill 综合** |
| QA-RISK | （综合）风险策略（测什么/不测什么） | 有无策略一句 | 综合｜**本 skill 综合** |
| SWE-BULLET | 成就型量化表述 | 同 TIH | https://www.techinterviewhandbook.org/resume/｜**一手** |
| G-HONEST | 覆盖率等数字可答辩 | 口径问题 | G-HONEST |

## 缺口声明
未找到大厂「QA 简历官方白皮书」；质量指标来自工程度量文献，简历检查项部分为综合。勿把厂商博客写成「招聘定律」。

## 常见差稿
- 只列 Selenium；「用例 1000+」无质量结果；虚荣覆盖率

## 打分锚点
- 5：质量结果+工程化落地  
- 3：有自动化无业务质量结果  
- 1：纯手工流水账

## 优先追问
- 逃逸如何定义？flaky 治理？
