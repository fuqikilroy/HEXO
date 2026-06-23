---
title: BrawlGame - 多人联机网络框架
date: 2026-06-22 10:00:00
type: game
comments: true
---

# ⚔️ BrawlGame - 多人联机网络框架

**Unity游戏开发** | 2025.9 - 2025.10

视频链接：https://www.bilibili.com/video/BV1GtJG63Ey7?spm_id_from=333.788.videopod.sections&bvid=BV1TFYsedE6m&vd_source=5cba27176a6d9ddf724559a56fe84d2a
<div style="position: relative; width: 100%; padding-bottom: 56.25%; height: 0; overflow: hidden; border-radius: 8px;">
  <iframe 
    src="//player.bilibili.com/player.html?isOutside=true&aid=116754088984956&bvid=BV1GtJG63Ey7&cid=39139740146&p=1"
    scrolling="no" 
    border="0" 
    frameborder="no" 
    framespacing="0" 
    allowfullscreen="true"
    style="position: absolute; width: 100%; height: 100%; left: 0; top: 0; border: none;">
  </iframe>
</div>

## 项目背景

针对多人实时对战场景下网络同步复杂、TCP粘包处理困难、多线程安全问题突出、模块耦合度高等痛点，设计并实现了一套基于TCP/IP协议栈的自研网络通信框架，从底层协议编解码到上层事件驱动分发，完整支撑多人游戏业务逻辑。

## 项目功能

以低延迟、高可靠和模块化为目标，集成自定义TCP应用层协议与事件驱动的消息分发模型，实现了用户注册登录、角色切换、实时移动同步、攻击动画同步、心跳保活等核心功能，保证多端游戏状态的一致性与流畅体验。

## 技术实现

### 用户认证与角色管理

实现注册、登录、角色切换等基础功能，通过单例模式维护全局玩家状态，为网络同步操作提供身份标识与数据基础。

### 自定义协议栈

遵循TCP流式传输规范，设计 `[包长度(2字节)] + [协议名(变长)] + [JSON体(变长)]` 的自定义应用层协议，通过动态缓冲区结合长度字段解析，彻底解决TCP粘包问题。

### 异步非阻塞网络核心

基于async/await和SocketAsync API在网络线程中异步处理数据收发；设计发送/接收双缓冲队列保证线程安全；发送队列采用同步事件实现阻塞唤醒，有效降低CPU占用并提升吞吐量。

### 实时游戏同步逻辑

采用状态同步思想，本地操作立即执行并生成对应消息发送至服务器；其他客户端通过观察者模式注册的消息回调解析并更新对应玩家对象的位置、朝向与动画，实现多端平滑同步。

### 心跳保活与连接管理

内置心跳保活机制，定时发送心跳包并检测回复，超时自动断开连接有效处理网络异常；支持连接优雅关闭，确保残留数据发送完毕后再释放资源。

## 技术栈

`Unity` `C#` `TCP/IP` `异步非阻塞IO` `多线程编程` `自定义协议设计` `观察者模式` `生产者-消费者模式`




## 项目心得

网络编程中，TCP的流式特性带来的粘包问题、多线程并发下的数据竞争、异步IO的回调地狱……每一个都是经典难题。通过设计自定义协议解决粘包、用双缓冲队列保证线程安全、用状态同步实现多端一致，我深刻理解了"没有银弹"——每个方案都是权衡与取舍。更重要的是，让我意识到了架构思想的通用性：这套框架的设计思路完全可以迁移到C++/epoll或Java/NIO等不同技术栈中。

---
[项目地址](https://github.com/fuqikilroy/BrawlGame.git)

<div style="text-align: right;">
  <a href="/HEXO/portfolio/" >🔗 返回作品集首页 →</a>
</div>