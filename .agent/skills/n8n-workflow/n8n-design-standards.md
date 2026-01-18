# n8n Design Standards - Ray's Workflow Layout Rules

> **MANDATORY**: Follow these standards when creating any n8n workflow for Ray.

---

## Sticky Note Grouping (REQUIRED)

### Core Principle

**Every logical operation gets its own sticky note.** Nodes that work together and depend on each other are grouped within the same sticky note.

### Sticky Note Format

```
┌─────────────────────────────────────┐
│  Title                              │  ← Bold, short name (2-3 words max)
│  Description text here              │  ← Small text explaining purpose
│                                     │
│    ┌─────┐    ┌─────┐    ┌─────┐   │
│    │Node1│───→│Node2│───→│Node3│   │  ← Related nodes inside
│    └─────┘    └─────┘    └─────┘   │
│                                     │
└─────────────────────────────────────┘
```

### When to Group Nodes Together

Group nodes in the SAME sticky note when:
- Multiple triggers feed into the same processing node
- Nodes depend on each other to pass data
- They represent ONE logical operation/stage

Create a NEW sticky note when:
- The workflow branches (routing/conditions)
- A new logical stage begins
- The purpose changes

---

## Standard Workflow Stages

### Stage 1: Entry Point / Trigger Group

**Sticky Note Title:** Descriptive name (e.g., "New Lead", "Incoming Order", "Webhook Request")

**Sticky Note Description:** What triggers this (e.g., "Lead fills in website form")

**Contains:**
- All trigger nodes (can be multiple)
- Initial data processing/formatting nodes (e.g., "Edit Fields")
- Nodes that prepare data for the next stage

**Example from Ray's workflow:**
```
┌─────────────────────────────────────┐
│  New Lead                           │
│  Lead fills in website form         │
│                                     │
│  [On form submission] ──┐           │
│                         ├──→ [Edit Fields]
│  [Fillout Trigger] ─────┘           │
│                                     │
└─────────────────────────────────────┘
```

### Stage 2: Routing / Decision Point

**Sticky Note Title:** "Routing" or descriptive decision name

**Sticky Note Description:** The criteria (e.g., "Based on opp size")

**Contains:**
- If/Switch/Router nodes
- Any pre-routing logic

**Example:**
```
┌─────────────────────────────────────┐
│  Routing                            │
│  Based on opp size                  │
│                                     │
│           [If]                      │
│                                     │
└─────────────────────────────────────┘
```

### Stage 3+: Action Branches

**Sticky Note Title:** Route identifier (e.g., "Route A", "Route B", or descriptive name)

**Sticky Note Description:** What this path does and why

**Contains:**
- All nodes for that specific path
- Related actions that happen together

**Example - High Value Path:**
```
┌─────────────────────────────────────┐
│  Route A                            │
│  Take specific actions for high     │
│  opportunity leads - quickly        │
│                                     │
│  [CRM] ──→ [SendNotification]       │
│  create record    send message      │
│                                     │
└─────────────────────────────────────┘
```

**Example - Low Value Path:**
```
┌─────────────────────────────────────┐
│  Route B                            │
│  Update CRM for low value leads     │
│                                     │
│         [UpdateCRM]                 │
│         create record               │
│                                     │
└─────────────────────────────────────┘
```

---

## Node Naming Conventions

### Trigger Nodes
- Use descriptive action names
- Format: `On [event]` or `[Source] Trigger`
- Examples:
  - `On form submission`
  - `Fillout Trigger`
  - `Webhook Received`
  - `Schedule Trigger`

### Action Nodes
- Name by what it DOES, not the service
- Use verb + context when helpful
- Examples:
  - `Edit Fields` (not "Set node")
  - `CRM` with subtitle `create record`
  - `UpdateCRM` with subtitle `create record`
  - `SendNotification` with subtitle `send message`

### Routing Nodes
- Simple: `If`, `Switch`, `Router`
- The sticky note description explains the logic

---

## Visual Layout Rules

### Flow Direction
- Left to right for main flow
- Top to bottom for branches when space is limited

### Spacing
- Sticky notes should have clear gaps between them
- Nodes inside sticky notes should be evenly spaced
- Leave room for connection lines to be visible

### Alignment
- Align sticky notes horizontally when they're sequential
- Stack branching paths vertically (Route A above Route B)

### Colors
- Use default n8n sticky note color (light beige/cream)
- Keep it clean and consistent

---

## Complete Workflow Structure Example

Based on Ray's lead routing workflow:

```
[ENTRY]              [DECISION]           [ACTIONS]

┌──────────────┐    ┌──────────────┐    ┌──────────────────┐
│ New Lead     │    │ Routing      │    │ Route A          │
│ Lead fills   │    │ Based on     │    │ High opp leads   │
│ website form │───→│ opp size     │───→│ [CRM]→[Notify]   │
│              │    │              │    └──────────────────┘
│ [Trigger1]─┐ │    │    [If]      │            │
│ [Trigger2]─┼─│    │              │    ┌──────────────────┐
│     ↓      │ │    └──────────────┘    │ Route B          │
│ [EditFields]│                    └───→│ Low value leads  │
└──────────────┘                        │ [UpdateCRM]      │
                                        └──────────────────┘
```

---

## Checklist Before Finishing a Workflow

- [ ] Every logical stage has its own sticky note
- [ ] Each sticky note has a clear Title
- [ ] Each sticky note has a descriptive subtitle/description
- [ ] Related nodes are grouped together
- [ ] Node names are descriptive (not default names)
- [ ] Flow reads left-to-right
- [ ] Branches are clearly separated with their own sticky notes
- [ ] Connection lines are visible and not overlapping

---

## Anti-Patterns to AVOID

❌ **No sticky notes** - Never leave nodes floating without context

❌ **One giant sticky note** - Don't put entire workflow in one sticky note

❌ **Default node names** - Never leave "Set", "IF", "HTTP Request" as names

❌ **Unclear grouping** - If nodes don't depend on each other, separate them

❌ **Missing descriptions** - Always explain WHY in the sticky note description

❌ **Cramped layout** - Give nodes and sticky notes room to breathe

---

## Reference Image

See `examples/lead-routing-workflow.png` for Ray's actual workflow example showing:
- Multi-trigger entry point grouped in "New Lead"
- Clean routing stage
- Separate sticky notes for each route branch
- Proper node naming with subtitles
