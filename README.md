# Instagram Android Engagement Automation Bot

An Android-based Instagram automation bot that runs directly on real devices using ADB-driven control and UI automation. It removes repetitive manual engagement work by automating common Instagram actions while keeping execution stable through rate limits, cooldowns, and device-level safety controls.

<p align="center">
  <a href="https://Appilot.app" target="_blank"><img src="https://github.com/Instagram-Automations/Footer-test/blob/main/appilot-baner.png" alt="Appilot Banner" width="100%"></a>
</p>
<p align="center">
  <a href="https://t.me/devpilot1" target="_blank"><img src="https://img.shields.io/badge/Chat%20on-Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white" alt="Telegram"></a>
  <a href="mailto:support@appilot.app" target="_blank"><img src="https://img.shields.io/badge/Email-support@appilot.app-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Gmail"></a>
  <a href="https://Appilot.app" target="_blank"><img src="https://img.shields.io/badge/Visit-Website-007BFF?style=for-the-badge&logo=google-chrome&logoColor=white" alt="Website"></a>
  <a href="https://discord.gg/3YrZJZ6hA2" target="_blank"><img src="https://img.shields.io/badge/Join-Appilot_Community-5865F2?style=for-the-badge&logo=discord&logoColor=white" alt="Appilot Discord"></a>
</p>


<p align="center">
Created by Appilot, built to showcase our approach to Automation! <br>
If you are looking for custom <strong> Instagram Android Engagement Automation Bot </strong>, you've just found your team — Let’s Chat.&#128070; &#128070;
</p>

## Introduction

Instagram engagement routines are time-consuming when done manually across multiple accounts and devices.  
This project automates daily engagement workflows on Android devices using ADB + UI automation, reducing operator workload and improving consistency.  
It’s built to run as a reliable device worker with configurable behavior, logging, and safeguards to keep sessions stable.

### Social Media Engagement Operations

- Automate engagement loops consistently across scheduled windows
- Reduce manual tapping and account switching overhead on Android devices
- Standardize workflows for teams managing multiple accounts
- Improve operational reliability with retries, cooldowns, and health checks

---

## Core Features

| Feature | Description |
|----------|-------------|
| Device-Based Execution | Runs on Android devices via ADB with device discovery and session management |
| Feed Engagement | Like, pause/scroll, and interact with feed posts using configurable rules |
| Story Engagement | View stories and optionally react based on settings and rate limits |
| Profile Actions | Visit profiles, follow/unfollow with filters and cooldown windows |
| Comment Automation | Optional commenting with templated text pools and anti-spam pacing |
| DM Outreach | Optional DM sending with queueing, deduplication, and safety throttles |
| Account Switcher | Supports switching between logged-in accounts on the same device |
| Action Scheduler | Time windows, daily caps, per-action quotas, and randomized delays |
| Targeting Modes | Engage by hashtags, locations, explore, or seed profiles |
| Humanization Controls | Variable scroll depth, dwell time, randomized taps, and back navigation patterns |
| Resilience & Recovery | Auto-retries, app relaunch, soft resets, and stuck-screen detection |
| Observability | Structured logs, run reports, screenshots on failure, and device health telemetry |
| Compliance Safeguards | Rate limiting, cooldown intervals, action caps, and configurable “safe mode” |
| Multi-Device Scaling | Run multiple workers in parallel across connected Android devices |
| Exportable Reports | Daily summaries, per-account stats, and action-level audit trails |

---

## How It Works

| Step | Description |
|------|-------------|
| **Input or Trigger** | A run starts via CLI command or scheduler with a chosen account list, targets, and daily limits. |
| **Core Logic** | The worker connects to the Android device, opens Instagram, navigates UI states, and executes actions with randomized pacing. |
| **Output or Action** | Performs engagement actions on-device and emits structured logs, metrics, and reports. |
| **Other Functionalities** | Includes retries, app relaunch on failures, screenshot capture, and queue-based task execution. |
| **Safety Controls** | Rate limiting, action caps, cooldown windows, randomized timing, and “safe mode” to reduce risky patterns. |

## Tech Stack

| Component | Description |
|------------|-------------|
| **Language** | Python |
| **Frameworks** | uiautomator2 |
| **Tools** | ADB, OpenCV (optional visual checks), Pydantic |
| **Infrastructure** | Docker (runner image), GitHub Actions (lint/tests), Local worker orchestration |

---

## Directory Structure Tree

    instagram-android-engagement-automation-bot/
    ├── src/
    │   ├── main.py
    │   ├── cli/
    │   │   ├── run_worker.py
    │   │   └── validate_config.py
    │   ├── core/
    │   │   ├── worker.py
    │   │   ├── scheduler.py
    │   │   ├── task_queue.py
    │   │   └── state_machine.py
    │   ├── device/
    │   │   ├── adb_client.py
    │   │   ├── device_manager.py
    │   │   └── health_checks.py
    │   ├── instagram/
    │   │   ├── app_controller.py
    │   │   ├── navigation.py
    │   │   ├── selectors.py
    │   │   ├── flows/
    │   │   │   ├── feed_like.py
    │   │   │   ├── story_view.py
    │   │   │   ├── follow_unfollow.py
    │   │   │   ├── comment.py
    │   │   │   └── dm_sender.py
    │   │   └── guards/
    │   │       ├── rate_limiter.py
    │   │       ├── cooldowns.py
    │   │       └── risk_filters.py
    │   ├── targeting/
    │   │   ├── hashtags.py
    │   │   ├── locations.py
    │   │   ├── seed_profiles.py
    │   │   └── explore.py
    │   ├── storage/
    │   │   ├── run_store.py
    │   │   ├── dedupe_store.py
    │   │   └── report_writer.py
    │   ├── observability/
    │   │   ├── logger.py
    │   │   ├── metrics.py
    │   │   └── screenshotter.py
    │   └── utils/
    │       ├── config_loader.py
    │       ├── timers.py
    │       └── text_pool.py
    ├── config/
    │   ├── settings.yaml
    │   ├── accounts.yaml
    │   ├── targets.yaml
    │   └── limits.yaml
    ├── logs/
    │   ├── activity.log
    │   └── runs/
    │       ├── 2025-12-23_run.jsonl
    │       └── 2025-12-23_summary.json
    ├── output/
    │   ├── reports/
    │   │   ├── daily_summary.csv
    │   │   └── action_audit.jsonl
    │   └── screenshots/
    │       └── failures/
    ├── tests/
    │   ├── test_rate_limiter.py
    │   ├── test_state_machine.py
    │   └── test_config_validation.py
    ├── scripts/
    │   ├── adb_setup.sh
    │   └── device_smoke_test.py
    ├── .github/
    │   └── workflows/
    │       ├── ci.yml
    │       └── lint.yml
    ├── requirements.txt
    └── README.md

---
## Use Cases

- **Social media operators** use it to run daily engagement loops on Android devices, so they can maintain consistent activity without manual tapping.  
- **Teams managing multiple accounts** use it to schedule actions with caps and cooldowns, so they can standardize workflows across accounts.  
- **Growth analysts** use it to test different targeting modes, so they can compare engagement outcomes across hashtags, locations, and seed profiles.  
- **Automation engineers** use it to generate structured run reports, so they can monitor reliability and quickly debug failures.  

---

## FAQs

**What kind of Android setup is required?**  
A physical Android device (or a dedicated Android environment) with developer options enabled, USB debugging on, and ADB access from the worker machine. The worker uses device discovery to select the correct device and then drives Instagram through UI automation.

**How does the bot avoid getting stuck on popups or unexpected screens?**  
It uses a navigation state machine with guard checks, recovery steps, and stuck-screen detection. When a failure is detected, it can back out, relaunch the app, capture a screenshot, and retry the task within configured limits.

**Can it run multiple devices at the same time?**  
Yes. Each connected device can run as an independent worker process with its own configuration, limits, and logs. A supervisor can distribute account/target queues across devices for parallel execution.

**How is targeting handled for engagement actions?**  
Targeting modules support engaging via hashtags, locations, explore browsing, or seed profiles. Each module feeds a task queue that deduplicates targets and applies filters before executing actions.

---

## Performance & Reliability Benchmarks

**Execution Speed:** Typically 120–260 mobile actions per hour per device (mix of navigation + engagement) depending on configured delays and UI load time.  

**Success Rate:** Approximately 92–94% across long-running device sessions with retries and automatic app recovery enabled.  

**Scalability:** Scales to 10–50+ Android devices by running one worker per device with centralized task distribution and per-device concurrency controls.  

**Resource Efficiency:** Per device worker typically uses 0.3–0.8 CPU core and 400–900MB RAM, with optional screenshot capture increasing disk usage.  

**Error Handling:** Automatic retries with backoff, popup handling, app relaunch, stuck-screen detection, screenshot-on-failure, and structured JSON Logs for debugging and audit trails.

<p align="center">
<a href="https://cal.com/app-pilot-m8i8oo/30min" target="_blank">
 <img src="https://img.shields.io/badge/Book%20a%20Call%20with%20Us-34A853?style=for-the-badge&logo=googlecalendar&logoColor=white" alt="Book a Call">
</a>
 <a href="https://www.youtube.com/@Appilot-app/videos" target="_blank">
  <img src="https://img.shields.io/badge/ð¥%20Watch%20demos%20-FF0000?style=for-the-badge&logo=youtube&logoColor=white" alt="Watch on YouTube">
 </a>
</p>
