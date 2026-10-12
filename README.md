# Voice Assistant for Multimedia Controls (VAMC)

> **Course**: UE24CS341A – Software Engineering  
> **Institution**: Department of Computer Science and Engineering, PES University  
> **Repository**: [se-grp-lab/team1](https://github.com/se-grp-lab/team1)  
> **Document Reference**: [Software Requirements Specification (SRS) v1.0](../../SRS_Voice_Assistant_Multimedia_Controls.md)

---

## 👥 Team Information (Team 1)

| S.No | Student Name | SRN / Roll Number | Project Role | GitHub Handle |
| :---: | :--- | :--- | :--- | :--- |
| 1 | **Soubhagya** | `PES2UG25CS827` | Federated Learning & Security Lead | [@Soubhagya981999](https://github.com/Soubhagya981999) |
| 2 | **Aakash Sharma** | `PES2UG24CS010` | UI/UX & Silent Feedback Designer | Team Contributor |
| 3 | **Aadya Arvind** | `PES2UG24CS008` | Media Integration & Controls Lead | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| 4 | **Andey Hemanth** | `PES2UG24CS061` | Lead Architect / NLU Specialist | [@Andy34G7](https://github.com/Andy34G7) |

---

## 📖 Project Overview

The **Voice Assistant for Multimedia Controls (VAMC)** is an intelligent, privacy-first desktop background service and overlay assistant engineered to deliver touchless control over multimedia playback across multiple environments:
- **Operating System Media**: Global system master volume, mute, and native OS media session keys (Windows SMTC, Linux MPRIS/DBus, macOS MediaRemote).
- **Local Desktop Media Players**: Desktop players including VLC Media Player and MPV via IPC/Telnet APIs.
- **Online & Streaming Platforms**: Streaming services including Spotify (via Spotify Connect / Web API) and YouTube.
- **Core Architecture Constraints**:
  - **Zero Audio Pollution**: 0 dB audio feedback emission during active playback (speech synthesis, beeps, and chimes are strictly prohibited to avoid interrupting listening).
  - **Edge Speech Recognition**: Entirely offline transcription and natural language intent understanding (ASR + NLU).
  - **Silent Heads-Up Display (HUD)**: A translucent, auto-dismissing visual overlay providing instant feedback without stealing window focus.
  - **Differential Privacy**: Edge model fine-tuning with DP-SGD ($\epsilon \le 2.0$) for secure parameter synchronization without raw voice transmission.

---

## 📋 Product Backlog & Traceability Matrix

All 26 backlog items are created as GitHub issues linked with labels, story points (Fibonacci scale), assignees, and sprint milestones.

### 🏃 Sprint 1: Core Audio Pipeline & Foundations (Oct 12 – Oct 16, 2026)
*Total Story Points Committed: **44 Points***  
*Milestone: [Sprint 1 (Oct 12 - Oct 16)](https://github.com/se-grp-lab/team1/milestone/1)*

| Issue | Req ID | User Story Summary | Epic / Category | Priority | Story Points | Assignee |
| :---: | :---: | :--- | :--- | :---: | :---: | :--- |
| [#1](https://github.com/se-grp-lab/team1/issues/1) | `VAMC-F-001` | Offline Wake Word Monitoring and Acoustic Detection | Audio Ingestion | High | **5** | [@Andy34G7](https://github.com/Andy34G7) |
| [#2](https://github.com/se-grp-lab/team1/issues/2) | `VAMC-F-002` | Global Push-To-Talk (PTT) Hotkey Activation | Audio Ingestion | High | **3** | [@Andy34G7](https://github.com/Andy34G7) |
| [#3](https://github.com/se-grp-lab/team1/issues/3) | `VAMC-F-003` | Voice Activity Detection (VAD) & Trailing Silence Clipping | Audio Ingestion | High | **3** | [@Andy34G7](https://github.com/Andy34G7) |
| [#4](https://github.com/se-grp-lab/team1/issues/4) | `VAMC-F-004` | Embedded Lightweight Offline Automatic Speech Recognition (ASR) | Speech & NLU | High | **5** | [@Andy34G7](https://github.com/Andy34G7) |
| [#5](https://github.com/se-grp-lab/team1/issues/5) | `VAMC-F-005` | Natural Language Intent Parsing & Entity Parameter Extraction | Speech & NLU | High | **5** | [@Andy34G7](https://github.com/Andy34G7) |
| [#6](https://github.com/se-grp-lab/team1/issues/6) | `VAMC-F-006` | Configurable Custom Voice Alias Mapping | Speech & NLU | Medium | **3** | [@Andy34G7](https://github.com/Andy34G7) |
| [#7](https://github.com/se-grp-lab/team1/issues/7) | `VAMC-F-007` | Core Playback State Control (Play, Pause, Resume, Stop) | Playback Controls | High | **3** | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| [#8](https://github.com/se-grp-lab/team1/issues/8) | `VAMC-F-008` | Relative Media Scrubbing & Timestamp Seeking | Playback Controls | High | **5** | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| [#9](https://github.com/se-grp-lab/team1/issues/9) | `VAMC-F-009` | Track Navigation & Playback Mode Toggling | Playback Controls | High | **3** | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| [#10](https://github.com/se-grp-lab/team1/issues/10) | `VAMC-F-010` | Relative Incremental Volume Adjustment | Volume Management | High | **2** | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| [#11](https://github.com/se-grp-lab/team1/issues/11) | `VAMC-F-011` | Absolute Exact Percentage Volume Control | Volume Management | High | **3** | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| [#12](https://github.com/se-grp-lab/team1/issues/12) | `VAMC-F-012` | Instant Audio Mute and Unmute Toggle | Volume Management | High | **2** | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| [#13](https://github.com/se-grp-lab/team1/issues/13) | `VAMC-NF-001` | End-to-End Command Execution Latency ($\le 400\text{ ms}$) | Performance | High | **5** | [@Andy34G7](https://github.com/Andy34G7) |
| [#14](https://github.com/se-grp-lab/team1/issues/14) | `VAMC-NF-005` | Zero Audio Pollution Guarantee (0 dB Feedback) | Quality / Audio | High | **2** | [@Soubhagya981999](https://github.com/Soubhagya981999) |

---

### 🏃 Sprint 2: Player Integrations, Silent HUD & Privacy (Oct 19 – Oct 23, 2026)
*Total Story Points Committed: **41 Points***  
*Milestone: [Sprint 2 (Oct 19 - Oct 23)](https://github.com/se-grp-lab/team1/milestone/2)*

| Issue | Req ID | User Story Summary | Epic / Category | Priority | Story Points | Assignee |
| :---: | :---: | :--- | :--- | :---: | :---: | :--- |
| [#15](https://github.com/se-grp-lab/team1/issues/15) | `VAMC-F-013` | Local Media Player Integration (VLC & MPV IPC) | Player Integrations | High | **5** | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| [#16](https://github.com/se-grp-lab/team1/issues/16) | `VAMC-F-014` | Cloud Streaming Integration (Spotify Web API & Connect) | Player Integrations | High | **5** | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| [#17](https://github.com/se-grp-lab/team1/issues/17) | `VAMC-F-015` | Active Media Player Auto-Detection & Routing | Player Integrations | Medium | **3** | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| [#18](https://github.com/se-grp-lab/team1/issues/18) | `VAMC-F-016` | Video Display Mode & Fullscreen Controls | Display & Subtitles | Medium | **2** | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| [#19](https://github.com/se-grp-lab/team1/issues/19) | `VAMC-F-017` | Voice-Activated Subtitle Toggle & Track Selection | Display & Subtitles | Medium | **3** | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| [#20](https://github.com/se-grp-lab/team1/issues/20) | `VAMC-F-018` | Variable-Speed Playback Rate Adjustment ($0.5\times - 2.0\times$) | Display & Subtitles | Medium | **2** | [@AadyaArvind19](https://github.com/AadyaArvind19) |
| [#21](https://github.com/se-grp-lab/team1/issues/21) | `VAMC-F-019` | Silent Translucent Floating HUD Overlay Pill | Silent HUD UI | High | **5** | [@Soubhagya981999](https://github.com/Soubhagya981999) |
| [#22](https://github.com/se-grp-lab/team1/issues/22) | `VAMC-F-020` | Automatic HUD Auto-Dismiss & Focus Non-Stealing | Silent HUD UI | High | **3** | [@Soubhagya981999](https://github.com/Soubhagya981999) |
| [#23](https://github.com/se-grp-lab/team1/issues/23) | `VAMC-F-021` | Edge-Based Private Acoustic Adaptation (On-Device) | Federated Learning | Medium | **5** | [@Soubhagya981999](https://github.com/Soubhagya981999) |
| [#24](https://github.com/se-grp-lab/team1/issues/24) | `VAMC-F-022` | Differentially Private Federated Weight Synchronization | Federated Learning | Low | **5** | [@Soubhagya981999](https://github.com/Soubhagya981999) |
| [#25](https://github.com/se-grp-lab/team1/issues/25) | `PRJ-SR-001` | Volatile RAM Audio Zeroization & Memory Disposal | Security & Privacy | High | **3** | [@Soubhagya981999](https://github.com/Soubhagya981999) |
| [#26](https://github.com/se-grp-lab/team1/issues/26) | `PRJ-SR-002` | Encrypted Credential Storage via OS Native Keyrings | Security & Privacy | High | **3** | [@Soubhagya981999](https://github.com/Soubhagya981999) |

---

## 📊 Story Point Allocation by Assignee

| Team Member | Project Role | Sprint 1 Points | Sprint 2 Points | Total Points |
| :--- | :--- | :---: | :---: | :---: |
| **Andey Hemanth** (`@Andy34G7`) | Architecture / ASR & NLU Specialist | **24** | **0** | **24** |
| **Aadya Arvind** (`@AadyaArvind19`) | Media Integration & Controls Lead | **18** | **20** | **38** |
| **Soubhagya** (`@Soubhagya981999`) | Federated Learning & Security Lead | **2** | **21** | **23** |
| **Total Backlog** | — | **44** | **41** | **85 Points** |

---

## 🚀 How to Link with GitHub Projects

To display these backlog items on a GitHub Project Board:
1. Navigate to the organization projects page: [https://github.com/orgs/se-grp-lab/projects](https://github.com/orgs/se-grp-lab/projects) (or your user project page [https://github.com/users/Andy34G7/projects](https://github.com/users/Andy34G7/projects)).
2. Click **New project** $\rightarrow$ Select the **Board** or **Table** template.
3. Name the project **"Team 1 - Voice Assistant for Multimedia Controls"**.
4. Click **`+ Add item`** $\rightarrow$ Search or select repository `se-grp-lab/team1`.
5. Select all 26 issues (or add them via workflow automation) to automatically populate the Board.
6. Group by **Milestone** or **Status** to visualize **Sprint 1** and **Sprint 2** boards!
