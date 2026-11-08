---
role: ai-product-manager
title: AI 产品经理
version: 1.2.0
---

# AI 产品经理 Rubric v1.1.0

## 10 秒看什么
- 「AI」是否有模型功能证据（Product Map：AI 已不是技能词而是待证主张）  
- 除 adoption 外有无质量与成本数字  
- 单栏标准标题 ATS 友好

## 必须证据

| ID | 必须证据 | 可观察检查 | 出处与证据等级 |
|----|----------|------------|----------------|
| AIPM-SHIP | 上线并度量、在模型出错时修复过的模型功能 | 是否写 shipped+measured+fixed | Product Map https://www.productmap.io/blog/ai-product-manager-resume （2026-09-18）｜**一手（垂直指南）** |
| AIPM-QUAL | 质量指标（accuracy/acceptance/edit/escalation 等） | 质量数字条数 | 同上 Metrics｜**一手** |
| AIPM-COST | 成本/延迟（per query、per resolution 等） | 成本数字条数 | 同上｜**一手** |
| AIPM-EVAL | Eval/发布门槛/曾否挡住发布 | 有无 eval 集或闸门描述 | 同上｜**一手** |
| AIPM-LIFE | 技能覆盖评测/提示/数据就绪/成本/护栏等可答辩项 | 技能是否可面试 10 分钟 | 同上 Technical skills｜**一手** |
| AIPM-WASH | 禁止 AI-washing：消费者工具当技能、冒领训练 | 负面模式计数 | 同上 Five mistakes｜**一手** |
| AIPM-FMT | 单栏、标准节名、约 8 年经验内偏一页 | 版式检查 | 同上 Format｜对齐 ATS-PARSE / G-ONEPAGE |

对齐 PM-* 基础产品能力（仍要 discovery/优先级等）。

## 常见差稿
- Title 含 AI、bullet 全传统运营；只有上线无质量/成本；证书压过项目

## 打分锚点
- 5：产物+质量+成本至少两类 + 边界清晰  
- 3：有 AI 项目仅有 usage  
- 1：AI-washing

## 优先追问
- 与算法分工？eval 案例能否走读？数字口径？

## 1.2.0 实测补丁
- **AIPM-WASH 加口径**：若项目区已有评测/质量/成本，但「自我评价」全是软技能空话 → 记 MKT-CN-SUMMARY 问题，**不要**仅凭自我评价判全文 AI-washing；若全文无质量/成本/eval 却自称 AI PM → AIPM-WASH 命中。
- Boss 导出噪声见 MKT-CN-BOSS，不影响 AIPM 内容命中判断。
