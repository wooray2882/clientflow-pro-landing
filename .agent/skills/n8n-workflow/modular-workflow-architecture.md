# Modular Workflow Architecture - Ray's Sub-Workflow Patterns

> **Philosophy:** Build systems with small, reusable components. Main workflows route to specialized sub-workflows that do ONE thing well.

---

## Core Principle

**Main Workflow → Sub-Workflows**

Instead of building one giant workflow, Ray prefers:
1. A **main workflow** that acts as a router/orchestrator
2. Multiple **sub-workflows** that handle specific actions
3. Each sub-workflow is a **reusable component** that can be used across projects

---

## Why This Architecture?

| Benefit | Description |
|---------|-------------|
| **Reusability** | Sub-workflows can be reused across multiple projects |
| **Maintainability** | Easier to debug and update individual components |
| **Single Responsibility** | Each workflow does ONE thing well |
| **Scalability** | Add new capabilities by adding new sub-workflows |
| **Testing** | Test each component independently |

---

## Standard Architecture Pattern

```
┌─────────────────────────────────────────────────────────────┐
│                      MAIN WORKFLOW                          │
│                     (Router/Orchestrator)                   │
│                                                             │
│  ┌─────────────┐     ┌─────────────┐                       │
│  │   Trigger   │────→│   Router    │                       │
│  │  (Webhook/  │     │  (Switch/   │                       │
│  │   Schedule) │     │   If node)  │                       │
│  └─────────────┘     └──────┬──────┘                       │
│                             │                               │
└─────────────────────────────┼───────────────────────────────┘
                              │
          ┌───────────────────┼───────────────────┐
          │                   │                   │
          ▼                   ▼                   ▼
┌─────────────────┐ ┌─────────────────┐ ┌─────────────────┐
│  Sub-Workflow 1 │ │  Sub-Workflow 2 │ │  Sub-Workflow 3 │
│  (Tool A)       │ │  (Tool B)       │ │  (Tool C)       │
│                 │ │                 │ │                 │
│ [Execute]       │ │ [Execute]       │ │ [Execute]       │
│     ↓           │ │     ↓           │ │     ↓           │
│ [Process]       │ │ [Process]       │ │ [Process]       │
│     ↓           │ │     ↓           │ │     ↓           │
│ [Return]        │ │ [Return]        │ │ [Return]        │
└─────────────────┘ └─────────────────┘ └─────────────────┘
```

---

## Main Workflow Pattern

### Trigger Options

The main workflow can be triggered by:
- **MCP Server Trigger** - For AI/LLM tool routing
- **Webhook** - For external API calls
- **Schedule** - For timed operations
- **Form Submission** - For user input

### Router Node

The router determines which sub-workflow to call:
- **Switch node** - Route based on action/tool name
- **If node** - Binary routing decisions
- **Code node** - Complex routing logic

### Example: MCP Server Pattern

```
┌─────────────────────────────────────────────────────────────┐
│  AI Tool Router                                             │
│  Routes AI requests to appropriate tool workflows           │
│                                                             │
│  ┌─────────────────┐     ┌─────────────────┐               │
│  │ MCP Server      │────→│ Switch          │               │
│  │ Trigger         │     │ (by tool name)  │               │
│  └─────────────────┘     └────────┬────────┘               │
│                                   │                         │
└───────────────────────────────────┼─────────────────────────┘
                                    │
        ┌──────────┬──────────┬─────┴────┬──────────┐
        ▼          ▼          ▼          ▼          ▼
   [Tool 1]   [Tool 2]   [Tool 3]   [Tool 4]   [Tool N]
```

---

## Sub-Workflow Pattern

### Required Trigger

Every sub-workflow MUST start with:

```
┌─────────────────────────────────────┐
│ When Executed by Another Workflow   │  ← REQUIRED trigger
│ (formerly "Execute Workflow Trigger")│
└─────────────────────────────────────┘
```

### Standard Sub-Workflow Structure

```
┌─────────────────────────────────────────────────────────────┐
│  [Tool Name]                                                │
│  [Brief description of what this tool does]                 │
│                                                             │
│  ┌─────────────────┐                                       │
│  │ When Executed   │  ← Receives data from main workflow   │
│  │ by Another      │                                       │
│  │ Workflow        │                                       │
│  └────────┬────────┘                                       │
│           │                                                 │
│           ▼                                                 │
│  ┌─────────────────┐                                       │
│  │ Process/Action  │  ← Do the ONE thing this tool does    │
│  │ (API call, DB,  │                                       │
│  │  transform)     │                                       │
│  └────────┬────────┘                                       │
│           │                                                 │
│           ▼                                                 │
│  ┌─────────────────┐                                       │
│  │ Return Data     │  ← Send result back to main workflow  │
│  │ (Edit Fields)   │                                       │
│  └─────────────────┘                                       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## Tool Documentation Format

Each sub-workflow/tool should be documented with:

### 1. Purpose
What this tool does (one sentence)

### 2. Inputs
What data it expects to receive:
```
- field_name (type): description
- field_name (type): description
```

### 3. Process
What steps it performs

### 4. Output
What data it returns:
```
- field_name (type): description
```

### Example Tool Documentation

```markdown
## Client Lookup Tool

**Purpose:** Retrieves client information from CRM by phone number or email.

**Inputs:**
- phone_number (string): Client's phone number
- email (string, optional): Client's email address

**Process:**
1. Search CRM for matching phone number
2. If not found, search by email
3. Return client record or "not found" status

**Output:**
- client_id (string): CRM record ID
- client_name (string): Full name
- found (boolean): Whether client was found
```

---

## Real-World Example: AI Receptionist System

Based on Ray's reference architecture:

### Main Workflow: MCP Server Router

**Purpose:** Routes incoming AI tool requests to appropriate sub-workflows

**Tools Available:**
1. Client Lookup
2. New Client CRM
3. Check Availability
4. Book Event
5. Lookup Appointment
6. Update Appointment
7. Delete Appointment

### Sub-Workflows

#### Tool 1: Client Lookup
- **Purpose:** Find existing client in CRM
- **Input:** Phone number
- **Output:** Client details or not found

#### Tool 2: New Client CRM
- **Purpose:** Create new client record
- **Input:** Name, phone, email
- **Output:** New client ID

#### Tool 3: Check Availability
- **Purpose:** Check calendar for open slots
- **Input:** Date range, service type
- **Output:** Available time slots

#### Tool 4: Book Event
- **Purpose:** Create new appointment
- **Input:** Client ID, date/time, service
- **Output:** Booking confirmation

#### Tool 5: Lookup Appointment
- **Purpose:** Find existing appointment
- **Input:** Client ID or confirmation number
- **Output:** Appointment details

#### Tool 6: Update Appointment
- **Purpose:** Modify existing appointment
- **Input:** Appointment ID, changes
- **Output:** Updated appointment

#### Tool 7: Delete Appointment
- **Purpose:** Cancel appointment
- **Input:** Appointment ID
- **Output:** Cancellation confirmation

---

## Visual Layout for Sub-Workflows

Apply the same sticky note standards from [n8n-design-standards.md](n8n-design-standards.md):

```
┌─────────────────────────────────────────────────────────────┐
│  [Tool Name]                                                │
│  [What this tool does - one line]                          │
│                                                             │
│  ┌─────────────┐   ┌─────────────┐   ┌─────────────┐       │
│  │ Execute     │──→│ Process     │──→│ Return      │       │
│  │ Trigger     │   │ (API/Logic) │   │ (Edit Fields)│       │
│  └─────────────┘   └─────────────┘   └─────────────┘       │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

---

## When to Create a New Sub-Workflow

Create a separate sub-workflow when:
- [ ] The action is reusable across multiple projects
- [ ] The action is distinct and self-contained
- [ ] The action has clear inputs and outputs
- [ ] The action could be triggered from different sources
- [ ] The logic is complex enough to warrant separation

Keep in main workflow when:
- [ ] The action is specific to this workflow only
- [ ] The action is simple (1-2 nodes)
- [ ] The action is tightly coupled to the routing logic

---

## Naming Conventions for Sub-Workflows

| Type | Format | Example |
|------|--------|---------|
| Tools | `[System] - [Action]` | `CRM - Client Lookup` |
| Utilities | `Util - [Function]` | `Util - Format Phone` |
| Integrations | `[Service] - [Action]` | `Google Cal - Book Event` |

---

## Anti-Patterns to AVOID

❌ **One giant workflow** - If your workflow has 20+ nodes, break it up

❌ **Duplicated logic** - If you copy-paste nodes, make a sub-workflow

❌ **Unclear boundaries** - Each sub-workflow should have ONE purpose

❌ **Missing documentation** - Always document inputs/outputs

❌ **Tight coupling** - Sub-workflows should be independent

❌ **No return data** - Always return meaningful data to the caller

---

## Checklist for Modular Workflows

### Main Workflow
- [ ] Has clear trigger (webhook, schedule, MCP, etc.)
- [ ] Router node determines which sub-workflow to call
- [ ] Handles sub-workflow responses appropriately
- [ ] Has error handling for failed sub-workflow calls

### Sub-Workflows
- [ ] Starts with "When Executed by Another Workflow" trigger
- [ ] Does ONE thing well
- [ ] Has documented inputs
- [ ] Returns meaningful output
- [ ] Can be tested independently
- [ ] Follows sticky note grouping standards

---

## Reference

See `examples/` folder for:
- `ai-receptionist-main-workflow.png` - MCP Server router example
- `sub-workflow-template.json` - Standard sub-workflow template

---

> **Note:** This architecture is especially powerful when building AI agent systems where an LLM needs to call various tools. The MCP Server pattern makes it easy to add new capabilities without modifying the main workflow.
