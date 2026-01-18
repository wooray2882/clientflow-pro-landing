# Workflow Patterns - Ray's Process & Automation Style

> This file documents Ray's preferred workflow patterns and automation approaches.

---

## Task Management Flow

<!-- TODO: Add your task management process -->

### Capture → Process → Execute

```
<!-- TODO: Describe your workflow from idea to completion -->

Stage 1: CAPTURE
└── Where do new ideas/tasks come from?
    - [ ] <!-- e.g., Sticky notes -->
    - [ ] <!-- e.g., Voice memo -->
    - [ ] <!-- e.g., Slack message -->
    - [ ] <!-- e.g., Email -->

Stage 2: PROCESS
└── How do you organize/prioritize?
    - [ ] <!-- e.g., Daily review -->
    - [ ] <!-- e.g., Weekly planning -->
    - [ ] <!-- e.g., Priority matrix -->

Stage 3: EXECUTE
└── How do you work through tasks?
    - [ ] <!-- e.g., Time blocking -->
    - [ ] <!-- e.g., Pomodoro -->
    - [ ] <!-- e.g., Batch similar tasks -->

Stage 4: COMPLETE
└── What happens when done?
    - [ ] <!-- e.g., Archive -->
    - [ ] <!-- e.g., Document learnings -->
    - [ ] <!-- e.g., Celebrate -->
```

---

## n8n Workflow Patterns

<!-- TODO: Add your preferred n8n patterns -->

### Standard Webhook Workflow

```
<!-- TODO: Your typical webhook workflow structure -->

[Webhook Trigger]
    ↓
[Validate Input]
    ↓
[Process Data]
    ↓
[Store/Send]
    ↓
[Respond]
    ↓
[Error Handler] ← (catches failures)
```

### Standard Scheduled Workflow

```
<!-- TODO: Your typical scheduled workflow structure -->

[Schedule Trigger]
    ↓
[Fetch Data]
    ↓
[Process]
    ↓
[Action]
    ↓
[Notify on Error]
```

### Common Patterns You Use

| Pattern | When to Use | Template |
|---------|-------------|----------|
| <!-- e.g., Data sync --> | <!-- e.g., Keep systems in sync --> | <!-- reference --> |
| <!-- e.g., Alert system --> | <!-- e.g., Monitor conditions --> | <!-- reference --> |
| <!-- e.g., Form handler --> | <!-- e.g., Process submissions --> | <!-- reference --> |

---

## Automation Principles

<!-- TODO: Add your automation philosophy -->

### When to Automate

```
<!-- TODO: Your criteria for automating something -->

Automate if:
- [ ] <!-- e.g., Task is repetitive (>3 times) -->
- [ ] <!-- e.g., Task is error-prone manually -->
- [ ] <!-- e.g., Task needs to happen off-hours -->
- [ ] <!-- e.g., Task has clear inputs/outputs -->

Don't automate if:
- [ ] <!-- e.g., Requires human judgment -->
- [ ] <!-- e.g., Rarely happens -->
- [ ] <!-- e.g., Too complex to maintain -->
```

### Error Handling Philosophy

```
<!-- TODO: How you handle errors in automations -->

On failure:
1. <!-- e.g., Log the error with context -->
2. <!-- e.g., Retry X times -->
3. <!-- e.g., Notify via Slack -->
4. <!-- e.g., Fail gracefully -->

Notification preferences:
- Critical errors: <!-- e.g., Immediate Slack + SMS -->
- Warnings: <!-- e.g., Daily digest -->
- Info: <!-- e.g., Log only -->
```

---

## Daily Workflow

<!-- TODO: Add your typical daily workflow -->

### Morning Routine

```
<!-- TODO: Your morning process -->

1. <!-- e.g., Check overnight alerts -->
2. <!-- e.g., Review today's calendar -->
3. <!-- e.g., Process inbox -->
4. <!-- e.g., Set top 3 priorities -->
```

### Work Blocks

```
<!-- TODO: How you structure your work day -->

- Deep work: <!-- e.g., 9am-12pm, no meetings -->
- Meetings: <!-- e.g., 1pm-3pm clustered -->
- Admin: <!-- e.g., 4pm-5pm emails/slack -->
```

### End of Day

```
<!-- TODO: Your wrap-up process -->

1. <!-- e.g., Review completed tasks -->
2. <!-- e.g., Capture tomorrow's priorities -->
3. <!-- e.g., Clear inbox -->
```

---

## Project Workflow

<!-- TODO: Add your project management style -->

### Project Phases

```
Phase 1: PLAN
├── <!-- e.g., Define scope -->
├── <!-- e.g., Break into tasks -->
└── <!-- e.g., Set milestones -->

Phase 2: BUILD
├── <!-- e.g., Sprint cycles -->
├── <!-- e.g., Daily standups -->
└── <!-- e.g., Regular demos -->

Phase 3: LAUNCH
├── <!-- e.g., Testing checklist -->
├── <!-- e.g., Gradual rollout -->
└── <!-- e.g., Monitor closely -->

Phase 4: ITERATE
├── <!-- e.g., Collect feedback -->
├── <!-- e.g., Prioritize improvements -->
└── <!-- e.g., Ship updates -->
```

---

## Communication Patterns

<!-- TODO: Add your communication preferences -->

### Notification Preferences

| Event Type | Channel | Urgency |
|------------|---------|---------|
| <!-- e.g., System down --> | <!-- e.g., SMS + Slack --> | Immediate |
| <!-- e.g., Task completed --> | <!-- e.g., Slack --> | Normal |
| <!-- e.g., Weekly report --> | <!-- e.g., Email --> | Low |

### Status Updates

```
<!-- TODO: How you prefer to receive/give updates -->

Format: <!-- e.g., Bullet points, not paragraphs -->
Frequency: <!-- e.g., Daily standup, weekly summary -->
Channel: <!-- e.g., Slack thread, Notion page -->
```

---

## Example Workflows

<!-- TODO: Reference your actual workflow examples -->

See `examples/` folder:
- `example-workflow-1.json` - <!-- description -->
- `example-workflow-2.json` - <!-- description -->

---

## Anti-Patterns (Things to Avoid)

<!-- TODO: Workflow patterns you dislike -->

- [ ] <!-- e.g., Too many manual steps -->
- [ ] <!-- e.g., Silent failures -->
- [ ] <!-- e.g., Over-notification -->
- [ ] <!-- e.g., Complex approval chains -->
