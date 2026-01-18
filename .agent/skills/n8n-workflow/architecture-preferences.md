# Architecture Preferences - Ray's System Structure

> This file documents Ray's preferred system architecture and structure patterns.

---

## Project Structure

<!-- TODO: Add your preferred folder organization -->

### Standard Project Layout

```
<!-- TODO: Fill in your preferred structure -->

project-name/
├── src/                    # Source code
│   ├── components/         #
│   ├── utils/              #
│   └── ...
├── docs/                   # Documentation
├── tests/                  # Test files
├── config/                 # Configuration
└── ...
```

### n8n Workflow Organization

```
<!-- TODO: How do you organize n8n workflows? -->

workflows/
├── automations/            # Automated triggers
│   ├── daily/              #
│   ├── webhooks/           #
│   └── ...
├── integrations/           # Third-party connections
├── internal/               # Internal processes
└── templates/              # Reusable patterns
```

---

## Naming Conventions

<!-- TODO: Add your preferred naming styles -->

### Files & Folders

| Type | Convention | Example |
|------|------------|---------|
| Folders | <!-- e.g., kebab-case --> | <!-- e.g., user-management --> |
| Files | <!-- e.g., kebab-case --> | <!-- e.g., get-user-data.js --> |
| Config files | <!-- e.g., dot prefix --> | <!-- e.g., .env, .config --> |

### n8n Workflows

| Type | Naming Pattern | Example |
|------|----------------|---------|
| Automations | <!-- e.g., [trigger]-[action] --> | <!-- e.g., webhook-create-user --> |
| Scheduled | <!-- e.g., [schedule]-[task] --> | <!-- e.g., daily-backup-db --> |
| Manual | <!-- e.g., manual-[task] --> | <!-- e.g., manual-export-data --> |

### Variables & Functions

| Type | Convention | Example |
|------|------------|---------|
| Variables | <!-- e.g., camelCase --> | <!-- e.g., userData --> |
| Constants | <!-- e.g., SCREAMING_SNAKE --> | <!-- e.g., MAX_RETRIES --> |
| Functions | <!-- e.g., verb + noun --> | <!-- e.g., getUserById --> |

---

## System Design Patterns

<!-- TODO: Add your preferred architectural patterns -->

### Data Flow

```
<!-- TODO: Describe how you prefer data to flow -->

Example patterns:
- Request → Validate → Process → Store → Respond
- Event → Queue → Handler → Notify
- Input → Transform → Output

Your preferred pattern:
<!-- Describe here -->
```

### Error Handling

```
<!-- TODO: How do you prefer to handle errors? -->

- Retry strategy: <!-- e.g., 3 retries with exponential backoff -->
- Notification: <!-- e.g., Slack alert, email -->
- Logging: <!-- e.g., structured JSON, error tracking service -->
- Fallback: <!-- e.g., default value, graceful degradation -->
```

### Integration Patterns

```
<!-- TODO: How do you connect systems? -->

Preferred patterns:
- [ ] Webhooks (real-time push)
- [ ] Polling (scheduled pull)
- [ ] Message queues (async)
- [ ] Direct API calls (sync)

Your preference: <!-- describe -->
```

---

## Framework Preferences

<!-- TODO: Add your preferred frameworks/templates -->

### n8n Workflow Templates

**Standard automation template:**
```
<!-- TODO: Describe your standard workflow structure -->

1. Trigger node (webhook/schedule/manual)
2.
3.
4.
5. Success/Error handling
```

**Integration template:**
```
<!-- TODO: Your integration workflow pattern -->

1.
2.
3.
```

### Code Architecture

**API structure:**
```
<!-- TODO: Preferred API organization -->

/api
├── v1/
│   ├── users/
│   ├── ...
│   └── ...
└── ...
```

---

## Documentation Standards

<!-- TODO: How do you like things documented? -->

### README Format

```markdown
<!-- TODO: Your preferred README structure -->

# Project Name

## Overview
<!-- Brief description -->

## Setup
<!-- Installation steps -->

## Usage
<!-- How to use -->

## Architecture
<!-- System overview -->
```

### Inline Documentation

- Comment style: <!-- e.g., JSDoc, simple comments, none -->
- When to comment: <!-- e.g., complex logic only, all functions -->
- Diagram preference: <!-- e.g., Mermaid, ASCII, images -->

---

## Example Diagrams

<!-- TODO: Add or reference architecture diagrams you like -->

See `examples/` folder:
- `example-system-diagram.png` - <!-- description -->
- `example-flow-chart.png` - <!-- description -->
- `example-folder-structure.png` - <!-- description -->

---

## Anti-Patterns (Things to Avoid)

<!-- TODO: Add architectural patterns you dislike -->

- [ ] <!-- e.g., Deeply nested folders -->
- [ ] <!-- e.g., God objects/files -->
- [ ] <!-- e.g., Inconsistent naming -->
- [ ] <!-- e.g., Lack of error handling -->
