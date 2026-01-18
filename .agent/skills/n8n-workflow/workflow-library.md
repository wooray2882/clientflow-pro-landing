# Workflow Template Library

> **Purpose:** A curated collection of 300+ proven n8n workflow templates organized by use case. Reference these BEFORE building new workflows to save time and leverage battle-tested patterns.

---

## How to Use This Library

### Before Building Any Workflow:

1. **Search the library** for similar workflows
2. **Check the template URL** to download the JSON
3. **Watch the video tutorial** for implementation guidance
4. **Adapt the template** using Ray's design standards

### CSV Location

```
data/workflow-templates.csv
```

### CSV Structure

| Column | Description |
|--------|-------------|
| `name` | Workflow name (searchable) |
| `title` | Original video title |
| `description` | Detailed explanation of what the workflow does |
| `creator` | Who built it (trusted sources) |
| `youtube_url` | Tutorial video link |
| `template_url` | Google Drive link to download JSON |
| `date_posted` | Publication date |
| `resource_url` | Additional resources (Skool, Gumroad, GitHub) |

---

## Workflow Categories

### 🎯 Lead Generation & Sales
- Cold email automation
- LinkedIn outreach
- Lead qualification (AI phone agents)
- CRM integration
- Meeting no-show prevention
- Proposal generation

**Search terms:** `lead`, `cold email`, `outreach`, `sales`, `CRM`, `proposal`

### 📱 Voice AI & Phone Agents
- AI receptionists (Vapi)
- SMS agents
- Call handling
- Appointment booking
- Lead qualification calls

**Search terms:** `voice`, `vapi`, `phone`, `SMS`, `call`, `receptionist`

### 🎬 Content Creation
- YouTube video ideas
- TikTok/Reels automation
- LinkedIn posts
- Podcast clip generation
- Faceless video creation
- Viral shorts

**Search terms:** `youtube`, `tiktok`, `linkedin`, `content`, `video`, `podcast`

### 🤖 Multi-Agent Systems
- Agent orchestrators
- Research agents
- Agent team builders
- Browser agents
- Personal assistants

**Search terms:** `multi-agent`, `agent`, `orchestrator`, `research`, `assistant`

### 📚 RAG & Knowledge Systems
- Vector database setup
- Document retrieval
- Contextual RAG
- Knowledge graphs
- File chat agents

**Search terms:** `RAG`, `vector`, `knowledge`, `document`, `supabase`, `pinecone`

### 👥 Client Onboarding
- Folder creation (Google Drive)
- Task setup (ClickUp)
- Slack channel creation
- Welcome emails
- CRM entry

**Search terms:** `onboarding`, `client`, `setup`, `welcome`

### 🔍 Scraping & Data
- Web scraping (Apify)
- Google Maps leads
- LinkedIn data
- Data enrichment
- Website analysis

**Search terms:** `scrape`, `apify`, `data`, `google maps`, `enrichment`

### 📧 Email Automation
- Inbox management
- Email classification
- Auto-replies
- Email drafting
- Gmail integration

**Search terms:** `email`, `gmail`, `inbox`, `reply`

---

## Top Creators (Trusted Sources)

| Creator | Specialty | Community |
|---------|-----------|-----------|
| Nate Herk | AI Agents, RAG, Personal Assistants | Skool |
| Nick Saraev | Cold Email, Lead Gen, Content | Gumroad (Maker School) |
| Rory Ridgers | Multi-Agent Research, Voice AI | Commonous |
| Cole Medin | Local AI, RAG, Agent Blueprints | GitHub |
| Jono Catliff | Scraping, Voice AI, Google Suite | Gumroad |
| Nolan Harper | Client Onboarding, Sales | AI Automation Vault |
| Mark Kashef | AI Builder, Meeting Prep | Gumroad |
| Ben AI | MCP, Omnichannel Sales | Skool |
| MagicOps AI | CRM, Voice Receptionists | Gumroad |
| Oleg Melnikov | Content Creation, Viral Videos | Skool |

---

## How to Search the Library

### Using Grep (Recommended)

```bash
# Search by keyword
grep -i "lead" data/workflow-templates.csv

# Search by creator
grep -i "Nate Herk" data/workflow-templates.csv

# Search for voice AI workflows
grep -i "vapi\|voice\|phone" data/workflow-templates.csv
```

### Example Searches

| Looking for... | Search command |
|----------------|----------------|
| Lead qualification | `grep -i "lead qualif" data/workflow-templates.csv` |
| Multi-agent systems | `grep -i "multi-agent" data/workflow-templates.csv` |
| RAG workflows | `grep -i "RAG" data/workflow-templates.csv` |
| Voice receptionist | `grep -i "receptionist\|vapi" data/workflow-templates.csv` |
| Content automation | `grep -i "youtube\|tiktok\|linkedin" data/workflow-templates.csv` |

---

## Workflow Selection Checklist

Before choosing a template:

- [ ] Does it match the core use case?
- [ ] Is the creator reputable? (see list above)
- [ ] Is there a video tutorial available?
- [ ] Does the template URL work?
- [ ] How recent is the template? (newer = more compatible)

---

## Integration with Ray's Standards

After downloading a template:

1. **Apply sticky note grouping** per [n8n-design-standards.md](n8n-design-standards.md)
2. **Rename default nodes** with descriptive names
3. **Add descriptions** to each sticky note stage
4. **Break into sub-workflows** if needed per [modular-workflow-architecture.md](modular-workflow-architecture.md)

---

## Adding New Templates

To add new templates to the library:

1. Add a row to `data/workflow-templates.csv`
2. Include all columns (name, title, description, creator, urls)
3. Verify the template URL works
4. Optionally download the JSON to `examples/` folder

---

## Quick Reference Examples

### Lead Generation Workflow
```
Name: Lead Qualifier System
Creator: Rory Ridgers
Use: Form → Website scrape → LinkedIn lookup → CRM → AI phone call
Template: Available via Commonous
```

### Voice AI Receptionist
```
Name: AI Voice Receptionist
Creator: Nate Herk
Use: Vapi agent → MCP Server → Sub-workflows (CRM, booking, etc.)
Template: Available via Skool community
```

### Multi-Agent Research
```
Name: Multi-Agent Research
Creator: Rory Ridgers
Use: Orchestrator → Market agent + Social agent + Company agent
Template: Available via Commonous
```

---

> **Remember:** Don't reinvent the wheel. Search the library first, adapt existing templates, and apply Ray's design standards.
