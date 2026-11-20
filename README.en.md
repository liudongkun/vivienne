<div align="center">

# Vivienne

### A personal AI steward, and a companion for everyday life.

<img src="assets/vivienne-banner.png" alt="Vivienne landscape cover: Your days, thoughtfully cared for. An attentive steward in a sunlit study, holding a planner and offering a cup of tea." width="100%">

<p><a href="README.md">简体中文</a> · <strong>English</strong></p>
<p><a href="#meet-vivienne">Meet Vivi</a> · <a href="#what-the-prototype-can-do">Capabilities</a> · <a href="#next">Next</a> · <a href="#origins">Origins</a></p>

<img alt="Personal prototype" src="https://img.shields.io/badge/status-personal_prototype-315747?style=flat-square">
<img alt="Showcase repository" src="https://img.shields.io/badge/repository-showcase-C2A56B?style=flat-square">

</div>

## Meet Vivienne

**Call her Vivi.**

Vivienne is a personal AI project about building a lasting working relationship: someone to talk things through with, and someone who can follow up on what you ask. Important mail, tomorrow's plans and changes in your accounts should have a place to go.

Her character is warm, capable and independent, with a little aristocratic confidence. The goal is for companionship to grow through remembered preferences, thoughtful reminders and work that gets done.

> “Welcome back. I remembered tomorrow's interview. The time and address are ready—shall we go through it together tonight?”

*This describes the intended experience. The poster is character concept art; the visual identity and conversational personality are being introduced gradually.*

## What the prototype can do

These capabilities are connected in a personal-use prototype and are still being refined.

| Area | Current scope |
|:---|:---|
| Mail | Read, search and summarize multiple QQ, NetEase 163 and Gmail accounts. Current mailbox connections are primarily read-only. |
| Calendar | Read Google Calendar events and availability. Writes require review and are restricted to OpenMuse-created events in a dedicated calendar, without attendee invitations. |
| Follow-through | Delegate work to persistent server tasks, save progress, and pause for input or approval. Reminders and mobile Web Push require device and browser permission. |
| Creator accounts | Collect basic metrics from Bilibili, Douyin and Xiaohongshu, with scheduled checks, history and configurable daily reports. Coverage is primarily follower counts; post-level details remain incomplete. |
| Across devices | Access one workspace from desktop and mobile browsers, with mobile layouts and PWA support. The current self-hosted setup needs its host computer online. |
| Personal context | Image input, explicitly saved preferences, and date/time-zone context support conversations and arrangements. |

### From a request to a recorded outcome

```text
Your request
    ↓
Read authorized information; answer or delegate a background task
    ↓
Use tools; pause for review when an action requires approval
    ↓
Record the result; remind you when follow-up is needed
```

Background tasks can continue after the browser closes. They cannot keep running when the host computer or service is off. Expired logins, network failures and platform changes can interrupt integrations; task status is the source of truth.

## Next

Planned, rather than released capabilities:

- [ ] Bring Vivienne's name, avatar and voice into the interface.
- [ ] Unify routines, next-run times, run history and failure handling.
- [ ] Improve personal preferences and long-term memory.
- [ ] Connect location-aware travel planning with routes and schedules.
- [ ] Add parent/child Agent coordination and result synthesis.
- [ ] Strengthen connection reliability, recovery and notifications.

## Under the hood

| Layer | Current prototype |
|:---|:---|
| Interface | TypeScript, React Native, Expo, React Native Web |
| Server | Node.js, Hono |
| Model/tool loop | TanStack AI; the current personal deployment uses DeepSeek |
| Agent/UI communication | CopilotKit, AG-UI, SSE |
| Storage | PGlite / PostgreSQL |
| Browser automation | Playwright |
| Runtime | Persistent tasks, workers, leases and heartbeats, approvals and checkpoints |

The chat Agent can delegate to a background execution Agent. Coordinating multiple child Agents is a future direction.

## Project status

**Personal prototype. This repository currently contains the product introduction and character artwork only. Application source code, installable releases and a public hosted service are not available here.**

The artwork communicates the character concept; it is not an application screenshot. The prototype is not a production reliability claim. Creator-account collection depends on platform pages, login state and connectivity.

Self-hosting keeps workspace data in your own deployment. Relevant task data may still be sent to external model providers and connected services when those services are used.

## Origins

The current prototype is a derivative of [OpenMuse Standalone](https://github.com/caspianchan31/openmuse-standalone), itself based on CopilotKit's OpenMuse ([upstream link](https://github.com/CopilotKit/openmuse), now redirecting to OpenFuse).

Work on this prototype focuses on multi-mailbox connections, reviewed calendar writes, mobile access and notifications, domestic creator-account monitoring, connector domain modeling and UI consistency. The foundational Agent loop and background runtime are inherited from upstream.

Thanks to [Caspian Chan](https://github.com/caspianchan31) and the upstream contributors. This showcase takes presentation inspiration from the author's character-led visuals, concise navigation and bilingual introductions. It does not include Yuki artwork or its additional implementation code.

See [CREDITS.md](CREDITS.md) for asset and provenance notes.

---

<div align="center">

**Vivienne · Vivi**  
Your days, thoughtfully cared for.

</div>
