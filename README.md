<div align="center">

# Vivienne

### 你的私人 AI 管家，也是日常里的伙伴。

<img src="assets/vivienne-banner.png" alt="Vivienne 横版封面：Your days, thoughtfully cared for. 薇薇安在阳光下的书房里，拿着日程本，向你递来一杯茶。" width="100%">

<p><strong>简体中文</strong> · <a href="README.en.md">English</a></p>
<p><a href="#认识-vivienne">认识 Vivi</a> · <a href="#她现在能帮你做什么">现有能力</a> · <a href="#接下来">接下来</a> · <a href="#项目来源">项目来源</a></p>

<img alt="项目阶段：个人原型" src="https://img.shields.io/badge/status-personal_prototype-315747?style=flat-square">
<img alt="仓库内容：产品介绍" src="https://img.shields.io/badge/repository-showcase-C2A56B?style=flat-square">

</div>

## 认识 Vivienne

**你可以叫她 Vivi。**

我想做一个可以长期相处的个人 AI：能聊聊生活，也能接住交代给她的事情。重要邮件、明天的安排、账号里的新变化，都有地方安放，也有人帮忙跟进。

Vivienne 的角色设定是一位聪明、有主见的私人管家。做事利落，说话温和，偶尔有一点大小姐的小傲气。她的陪伴感，要从记住偏好、及时提醒和把事情办妥中慢慢建立。

> 「回来啦。明天的面试我记着呢，时间和地址都整理好了。今晚要不要一起过一遍？」

*这是希望逐步实现的相处方式。海报是角色概念设计，角色形象与语气尚在逐步融入产品。*

## 她现在能帮你做什么

下列能力已在个人使用原型中接入，仍在持续打磨。

<table>
<tr>
<td width="50%" valign="top">

### 一起整理收件箱

连接 QQ 邮箱、网易 163 和 Gmail，多账户读取、搜索与摘要。把重要消息和需要处理的事情找出来，当前邮箱接入以只读为主。

</td>
<td width="50%" valign="top">

### 把安排落到日历

读取 Google Calendar，查看日程与空闲时间。写入先提交审核；修改范围限制在专用日历内由 OpenMuse 创建的日程，不发送参会邀请。

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 交代之后，继续跟进

聊天可以把工作委派给服务端后台任务，保存状态，并在需要补充信息或审批时暂停。提醒与手机 Web Push 已接入，需要设备和浏览器授权。

</td>
<td width="50%" valign="top">

### 留意自己的账号

接入 B 站、抖音、小红书的基础账号指标采集，支持定时检查、历史记录和可配置日报。目前以粉丝数等基础指标为主，作品明细尚未完整接入。

</td>
</tr>
<tr>
<td width="50%" valign="top">

### 在电脑与手机之间

使用电脑和手机浏览器访问同一个工作区，支持移动端界面与 PWA 使用方式。当前是个人自托管方案，需要运行服务的电脑保持在线。

</td>
<td width="50%" valign="top">

### 让信息有上下文

支持图片输入、明确保存的个人偏好，以及日期与时区上下文。逐步把零散信息变成可确认的安排和后续行动。

</td>
</tr>
</table>

### 从一句交代，到一个有结果的任务

```text
你提出需求
    ↓
Vivi 读取已授权的信息，回答问题或委派后台任务
    ↓
执行工具；遇到日历写入等动作时，先请你审核
    ↓
保存执行结果，需要时提醒你继续处理
```

服务端任务可以在前端关闭后继续运行；电脑关机或服务停止时，无法持续执行。平台登录失效、网络变化也可能影响连接与采集，执行结果以任务状态为准。

## 接下来

这些是计划方向，尚未作为现有能力发布：

- [ ] 把 Vivienne 的头像、名字与角色语气融入产品。
- [ ] 统一例行任务中心：看见下次运行、历史结果和失败原因。
- [ ] 增强偏好与长期记忆，让陪伴感来自持续理解。
- [ ] 加入位置感知与旅行规划，串联路线和日程。
- [ ] 支持主 Agent 拆分任务、子 Agent 协作与结果汇总。
- [ ] 提高连接、失败恢复与消息通知的可靠性。

## 技术一览

| 层次 | 当前原型 |
|:---|:---|
| 界面 | TypeScript、React Native、Expo、React Native Web |
| 服务端 | Node.js、Hono |
| 模型与工具循环 | TanStack AI；当前个人部署使用 DeepSeek |
| Agent 与界面通信 | CopilotKit、AG-UI、SSE |
| 数据存储 | PGlite / PostgreSQL |
| 浏览器自动化 | Playwright |
| 运行机制 | 持久化任务、Worker、租约与心跳、审批与检查点 |

当前已有聊天 Agent 向后台执行 Agent 委派任务的机制；多子 Agent 的拆分、协作和汇总仍在规划中。

## 项目状态

**Vivienne 处于个人使用原型阶段。这个仓库目前只发布产品介绍与角色展示素材，暂未发布应用源码、安装包或公开在线服务。**

海报展示角色气质，不是应用界面截图。已有功能的说明来自个人原型，不构成生产环境可靠性承诺。自媒体采集受平台页面、登录状态和网络影响。

自托管让工作区数据保存在自己的部署中；使用外部模型或连接器时，完成任务所需的相关数据仍可能发送给对应服务。

## 项目来源

Vivienne 的现有原型基于 [OpenMuse Standalone](https://github.com/caspianchan31/openmuse-standalone) 二次开发；Standalone 源自 CopilotKit 的 OpenMuse 项目（[上游地址](https://github.com/CopilotKit/openmuse)，目前跳转至 OpenFuse）。

现有工作围绕多邮箱接入、Google 日历审批写入、手机访问与通知、国内自媒体监测，以及连接器领域建模和界面一致性展开。基础 Agent Loop 与后台运行机制继承自上游，并非全部从零实现。

感谢 [Caspian Chan](https://github.com/caspianchan31) 与上游贡献者。介绍页参考其人物主视觉、简洁导航和双语介绍的呈现方式，未采用 Yuki 的角色素材或新增实现代码。

素材与来源说明见 [CREDITS.md](CREDITS.md)。

---

<div align="center">

**Vivienne · 薇薇安**  
把你交代的事放在心上。

</div>
