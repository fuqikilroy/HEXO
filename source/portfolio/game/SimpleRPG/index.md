---
title: SimpleRPG - Unity RPG游戏demo
date: 2026-06-22 10:00:00
type: game
comments: true
---

# 🎮 SimpleRPG - Unity RPG游戏demo

**Unity游戏开发** | 2025.8 - 2025.9

视频链接：https://www.bilibili.com/video/BV18DJ36iEUB?spm_id_from=333.788.videopod.sections&bvid=BV1TFYsedE6m&vd_source=5cba27176a6d9ddf724559a56fe84d2a
<div style="position: relative; width: 100%; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: 8px;">
  <iframe 
    src="//player.bilibili.com/player.html?isOutside=true&aid=116754223204188&bvid=BV18DJ36iEUB&cid=39140722511&p=1"
    scrolling="no" 
    border="0" 
    frameborder="no" 
    framespacing="0" 
    allowfullscreen="true"
    style="position: absolute; width: 100%; height: 100%; left: 0; top: 0; border: none;">
  </iframe>
</div>

## 项目背景

针对RPG类游戏中常见的角色控制、任务交互、战斗逻辑、UI状态同步等模块耦合度高、扩展性差的问题，设计并实现了一套基于Unity引擎的RPG游戏核心系统，采用数据驱动与事件驱动的混合架构。

## 项目功能

实现了基于鼠标点击的角色移动与交互、任务接取与进度追踪、多类型武器（近战/远程）攻击逻辑、敌人AI与刷新机制、背包与物品使用、多模块UI联动等核心功能。通过事件中心解耦各模块间的通信，保证系统在功能迭代时的稳定性和可维护性。

## 技术实现

### 玩家控制系统

基于NavMeshAgent实现鼠标点击移动，通过射线检测区分"地面"与"可交互对象"，触发移动或交互行为；集成攻击、拾取、属性管理等模块，完成玩家行为闭环。

### 交互与任务系统

定义交互抽象基类，派生实现NPC对话、物品拾取、任务NPC等具体交互类型；任务系统基于状态机管理任务进度，通过事件中心监听杀怪事件动态更新进度，支持对话分支触发任务接受与奖励发放。

### 多类型武器与战斗逻辑

设计武器基类及近战/远程派生类，近战通过动画事件触发碰撞检测，远程实现子弹生成、飞行与碰撞伤害判定；敌人响应受伤、死亡逻辑并掉落经验值。

### UI系统与数据驱动架构

采用单例模式管理对话、背包、消息提示、属性等UI模块；背包支持物品动态生成、详情展示、使用与销毁；使用ScriptableObject定义物品、任务等配置数据，提升策划可配置性。

### 敌人AI与生成管理

敌人具备战斗/移动/休息三种状态，支持随机寻路与计时器驱动切换；刷怪器基于计时器循环生成敌人，保持场景中战斗资源的动态平衡。

## 技术栈

`Unity` `C#` `NavMeshAgent` `射线检测` `ScriptableObject` `单例模式` `观察者模式` `数据驱动设计`

## 项目心得

RPG系统的复杂度在于各模块之间的联动——移动影响战斗、战斗影响任务、任务影响UI，环环相扣。通过事件中心解耦是我在这个项目中学到最重要的一课。另外，用ScriptableObject做数据驱动让设计师可以独立配置数值，真正实现了程序与内容的分离，为后续快速迭代创造了条件。

---

[项目地址](https://github.com/fuqikilroy/Simple-RPG.git)

<div style="text-align: right;">
  <a href="/HEXO/portfolio/" >🔗 返回作品集首页 →</a>
</div>