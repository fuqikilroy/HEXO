---
title: 智能交通票务系统
date: 2026-06-22 10:00:00
type: programming
comments: true
---

# 🚄 智能交通票务系统

**全栈开发者** | 2025.10 - 2025.12

视频链接：https://www.bilibili.com/video/BV12fJ36cECi?spm_id_from=333.788.videopod.sections&bvid=BV1TFYsedE6m&vd_source=5cba27176a6d9ddf724559a56fe84d2a
<div style="position: relative; width: 100%; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: 8px;">
  <iframe 
    src="//player.bilibili.com/player.html?isOutside=true&aid=116754340710152&bvid=BV12fJ36cECi&cid=39141182173&p=1&high_quality=1" 
    scrolling="no" 
    border="0" 
    frameborder="no" 
    framespacing="0" 
    allowfullscreen="true"
    style="position: absolute; width: 100%; height: 100%; left: 0; top: 0; border: none;">
  </iframe>
</div>



## 项目背景

针对传统铁路票务系统操作繁琐、无障碍支持不足、智能化程度不高的问题，结合国家铁路服务质量提升和无障碍环境建设的需求，设计并实现基于SpringBoot框架融合大模型技术的智能交通票务系统。

## 项目功能

以智能化、个性化和无障碍为目标，集成SpringBoot后端架构与DeepSeek、阿里万相等多模态生成式AI能力，通过LangChain进行多轮对话交互和RAG检索增强，支持自然语言完成车票查询、预订、退改等全流程操作。

## 技术实现

### 用户管理模块

实现了用户注册、登录、信息修改、实名认证等基础功能，为票务操作提供身份验证基础。

### 票务业务模块

遵循铁路票务业务规范，通过精细化库存管理和严格业务规则引擎确保交易准确性。针对高并发场景使用乐观锁机制有效防止车票超售，实现车次查询、余票展示、车票预订、订单生成、一键退票等完整业务链条。

### 大模型集成模块

基于LangChain框架深度集成DeepSeek大语言模型，通过"工具调用"机制将模型生成的用户意图精准映射至后端票务接口。实现智能对话、工具调用、上下文记忆、流式响应、服务降级机制等核心功能。

### 文生图流水线

搭建涵盖模型管理、提示词工程、风格控制的完整文生图流水线，通过统一风格规范保证不同城市背景图兼具艺术性与一致性。

### 后台管理系统

为管理员提供全面的数据管理与业务监控能力，集成ECharts数据可视化组件辅助决策，通过精细化CRUD操作界面实现对用户、车次、订单、公告等核心数据的集中管理。

## 技术栈

`SpringBoot` `大语言模型` `LangChain` `RAG检索增强` `多模态生成式AI` `ECharts`

## 项目心得

将大模型与传统票务系统结合是一次很有价值的探索。LangChain的工具调用机制让大模型能够真正"做事"而不仅仅是"对话"，这为后续智能化应用提供了新思路。同时，在高并发票务场景下使用乐观锁应对超售问题，加深了我对并发控制策略在实际业务中应用的理解。

---

<div style="text-align: right;">
  <a href="/HEXO/portfolio/" >🔗 返回作品集首页 →</a>
</div>