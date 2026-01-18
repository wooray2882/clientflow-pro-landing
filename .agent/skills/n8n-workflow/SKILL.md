---
name: n8n-workflow
description: Ray's n8n workflow design standards and preferences. REQUIRED when building any n8n workflow. Defines sticky note grouping, node naming, and visual layout rules.
allowed-tools: Read, Write, Edit, Glob, Grep, Bash
---

# N8N Workflow - Ray's Personal System Design

> **Philosophy:** Clean, organized workflows where every logical operation is visually grouped and labeled.
> **Core Principle:** Group related nodes with sticky notes. Every stage gets a title and description.

---

## Quick Reference

| File | Status | When to Read |
|------|--------|--------------|
| [n8n-design-standards.md](n8n-design-standards.md) | 🔴 **REQUIRED** | ALWAYS read when building n8n workflows! |
| [workflow-library.md](workflow-library.md) | 🟡 **IMPORTANT** | Search for existing templates BEFORE building |
| [modular-workflow-architecture.md](modular-workflow-architecture.md) | 🟡 **IMPORTANT** | When building systems with multiple workflows |
| [visual-patterns.md](visual-patterns.md) | Optional | UI/dashboard preferences |
| [architecture-preferences.md](architecture-preferences.md) | Optional | System design & structure |
| [tool-preferences.md](tool-preferences.md) | Optional | When selecting tools/tech |
| [workflow-patterns.md](workflow-patterns.md) | Optional | Task organization & flow |

> 🔴 **n8n-design-standards.md = ALWAYS READ when creating n8n workflows.**
> 🟡 **workflow-library.md = SEARCH for existing templates before building from scratch.**
> 🟡 **modular-workflow-architecture.md = READ when building multi-workflow systems.**

---

## Ray's Preferences Summary

### Visual Organization Style

<!-- TODO: Fill in after reviewing your examples -->

**Sticky Notes:**
- [ ] Uses sticky notes for: <!-- e.g., quick ideas, task tracking, reminders -->
- [ ] Preferred colors: <!-- e.g., yellow for ideas, pink for urgent -->
- [ ] Organization pattern: <!-- e.g., grouped by project, timeline, priority -->

**Dashboard Layout:**
- [ ] Preferred layout: <!-- e.g., kanban, calendar, list view -->
- [ ] Information density: <!-- minimal / moderate / dense -->
- [ ] Color scheme: <!-- dark mode / light mode / specific colors -->

### Architecture Preferences

<!-- TODO: Fill in your system structure preferences -->

**Folder Structure:**
```
<!-- TODO: Add your preferred project structure -->
project/
├── ...
└── ...
```

**Naming Conventions:**
- Files: <!-- e.g., kebab-case, camelCase -->
- Folders: <!-- e.g., lowercase, descriptive -->
- Variables: <!-- e.g., descriptive, prefixed -->

### Workflow Patterns

<!-- TODO: Describe how you like to work -->

**Task Flow:**
1. <!-- Step 1: e.g., Capture idea in sticky note -->
2. <!-- Step 2: e.g., Move to backlog -->
3. <!-- Step 3: e.g., Prioritize -->
4. <!-- Step 4: e.g., Execute -->
5. <!-- Step 5: e.g., Review -->

**Automation Preferences:**
- Trigger types preferred: <!-- e.g., webhook, schedule, manual -->
- Error handling style: <!-- e.g., retry, notify, fail fast -->
- Logging level: <!-- minimal / detailed / verbose -->

---

## When Building for Ray

### DO:
- [ ] <!-- TODO: Add things you want AI to always do -->
- [ ] <!-- TODO: Add more preferences -->
- [ ] <!-- TODO: Add more preferences -->

### DON'T:
- [ ] <!-- TODO: Add things you want AI to avoid -->
- [ ] <!-- TODO: Add more anti-patterns -->
- [ ] <!-- TODO: Add more anti-patterns -->

---

## Example References

See the `examples/` folder for visual references:

| Example | Description | Status |
|---------|-------------|--------|
| <!-- filename.png --> | <!-- description --> | Pending |
| <!-- filename.png --> | <!-- description --> | Pending |
| <!-- filename.png --> | <!-- description --> | Pending |

---

## Reference Files

- [n8n-design-standards.md](n8n-design-standards.md) - 🔴 Sticky note grouping, node naming, visual layout rules
- [workflow-library.md](workflow-library.md) - 🟡 300+ workflow templates library (search before building!)
- [modular-workflow-architecture.md](modular-workflow-architecture.md) - 🟡 Main workflow → sub-workflow patterns
- [visual-patterns.md](visual-patterns.md) - Sticky notes, layouts, UI preferences
- [architecture-preferences.md](architecture-preferences.md) - System structure, folder organization
- [tool-preferences.md](tool-preferences.md) - Preferred tools and technologies
- [workflow-patterns.md](workflow-patterns.md) - Task flow and automation patterns

## Data Files

- [data/workflow-templates.csv](data/workflow-templates.csv) - Searchable CSV of 300+ workflow templates with URLs

---

> **Note:** This skill is a living document. Update sections as you discover your preferences.
> Last updated: <!-- TODO: Update date when you make changes -->
