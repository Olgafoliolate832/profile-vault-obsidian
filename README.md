# ProfileVault

A modular Obsidian vault template for managing your professional identity, career history, and applications. Use it as a personal knowledge base with Obsidian's UI, and optionally connect it to LLM-powered tools for intelligent CV generation, application strategy, and profile management.

## Who Is This For?

Researchers, engineers, consultants, and professionals who:

- Work across multiple domains (academic, technical, consulting)
- Need to generate tailored CVs, cover letters, and grant profiles
- Apply for jobs, grants, fellowships, PhDs, and conferences
- Want a structured, queryable knowledge base for their career data
- Want to optionally leverage AI assistants for application preparation

## Vault Structure

```
Profile/
├── Profile.md                    # Root overview — start here
├── Applications/                 # Track all applications
│   ├── Jobs/
│   ├── Grants/
│   ├── Fellowships/
│   ├── PhDs/
│   └── Conferences/
├── Experience/                   # Professional roles & positions
│   ├── Academic/
│   ├── Industry/
│   └── Freelance/
├── Education/                    # Degrees, certifications, courses
│   ├── Degrees/
│   ├── Certifications/
│   └── Courses/
├── Skills/                       # Categorized skill tracking
│   ├── Technical/
│   ├── Research/
│   ├── Consulting/
│   ├── Languages/
│   ├── Software-Tools/
│   └── Soft-Skills/
├── Publications/                 # All publication types
├── Projects/                     # Notable projects
├── Grants-Funding/               # Funded grant track record
├── Awards-Honors/                # Awards, prizes, scholarships
├── Talks-Workshops/              # Talks, presentations, panels
├── Professional-Service/         # Reviewing, mentoring, organizing
├── References/                   # Referee management
├── Identity/                     # Bios, statements, personal info
├── Archive/                      # Retired content
└── Templates/                    # Self-documenting templates for all of the above
```

## Key Features

### Self-Documenting Templates

Every folder has a corresponding template in `Templates/` with:

- Folder structure blueprints
- YAML frontmatter field guides
- Rules and naming conventions
- Dataview dashboard queries
- How-to instructions

### Application Workflow

Each application (job, grant, fellowship, PhD, conference) follows a structured workflow:

1. **Context/** — gather their information (description, requirements, research)
2. **Strategy/** — map your profile to their needs (mapping table, gaps, highlights)
3. **Outputs/** — generate tailored deliverables (CV, cover letter, etc.)

### Dataview-Powered Dashboards

Every folder overview file includes Dataview queries that automatically display:

- All entries sorted by date, status, or type
- Active/current items
- Filtered views (by domain, priority, etc.)

### Rich Frontmatter

Every entry uses structured YAML frontmatter for queryable, filterable data:

- Status tracking (`active`, `completed`, `draft`, etc.)
- Domain tagging (`academic`, `technical`, `consulting`)
- Cross-references via wikilinks
- Dates in ISO format

## Getting Started

### 1. Clone or Download

```bash
git clone https://github.com/nyinyinyanlin/profile-vault-obsidian.git
```

### 2. Open in Obsidian

1. Open Obsidian
2. Click "Open folder as vault"
3. Select the `Profile/` directory inside the cloned repo

### 3. Install Recommended Plugins

Go to Settings → Community Plugins → Browse and install:

| Plugin | Purpose |
|--------|---------|
| **Dataview** | Powers all dashboard queries |
| **Templater** | Advanced template insertion |
| **Tasks** | Task tracking across notes |
| **Calendar** | Calendar view for deadlines |
| **Obsidian Git** | Version control from within Obsidian |

### 4. Configure Obsidian Settings

- **Files & Links** → Set "New link format" to **"Shortest path when possible"**
- **Graph View** → Add filter `-path:Templates` to exclude templates from default view

### 5. Start Populating

1. Open `Profile.md` — this is your vault's home page
2. Start with `Identity/Personal-Info.md` — fill in your basic details
3. Add your experience, education, and skills
4. When ready to apply for something, copy the relevant template from `Templates/Applications/`

## Using with AI / LLM Tools

This vault's structured Markdown files, consistent frontmatter, and modular design make it well-suited for use with LLM-powered tools and agents. Any AI assistant that can read and write Markdown files can:

- Search your vault for relevant experience, skills, and publications
- Generate tailored CVs by pulling from your modular profile data
- Help strategize applications by mapping your profile to requirements
- Create cover letters, research statements, and grant profiles
- Maintain and organize your vault structure

### Connecting via MCP (Model Context Protocol)

MCP is an open protocol that lets AI assistants connect to external tools and data sources. Any MCP-compatible client can connect to this vault.

**Option 1: MCPVault (recommended — no plugins needed)**

```jsonc
{
  "mcpServers": {
    "profile-vault": {
      "command": "npx",
      "args": ["@bitbonsai/mcpvault@latest", "/path/to/ProfileVault/Profile"]
    }
  }
}
```

**Option 2: Filesystem MCP**

```jsonc
{
  "mcpServers": {
    "profile-vault": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-filesystem", "/path/to/ProfileVault/Profile"]
    }
  }
}
```

**Option 3: Obsidian MCP plugins**

Various community plugins expose Obsidian vaults as MCP servers. Check the Obsidian community plugins directory for options compatible with your preferred AI tool.

### Other Integration Methods

Since the vault is just a folder of Markdown files, any tool that can read/write files can integrate with it — CLI tools, scripts, IDE extensions, or any LLM agent with filesystem access.

## Conventions

| Convention | Rule |
|------------|------|
| **Folder overview files** | Named to match folder (e.g., `Skills/Skills.md`) |
| **Application entry points** | Always `Index.md` |
| **Dates** | ISO format (`YYYY-MM-DD`) |
| **Internal links** | Wikilinks (`[[Note Name]]`) |
| **Never delete** | Move to `Archive/` instead |
| **Templates** | Never edit directly — copy first |

## Naming Conventions

| Type | Pattern | Example |
|------|---------|---------|
| Job application | `YYYY-MM-Organization-Role` | `2026-03-Google-SeniorMLE` |
| Grant application | `YYYY-MM-Funder-Title` | `2026-04-FWF-AIMonitoring` |
| Fellowship | `YYYY-MM-Organization-Program` | `2026-05-Humboldt-Fellowship` |
| PhD application | `YYYY-MM-University-Topic` | `2026-06-ETH-MachineLearning` |
| Conference | `YYYY-MM-Conference-Topic` | `2026-06-NeurIPS-GraphOpt` |
| Experience | `Role-Organization-Title` | `Role-Google-SeniorEngineer` |
| Publication | `Pub-YYYY-Venue-Title` | `Pub-2024-NeurIPS-GraphOpt` |
| Project | `Proj-YYYY-ShortName` | `Proj-2024-SmartCityPlatform` |
| Grant record | `Grant-YYYY-Funder-Title` | `Grant-2024-FWF-AIMonitoring` |
| Award | `Award-YYYY-ShortName` | `Award-2024-BestPaper-NeurIPS` |
| Talk | `Talk-YYYY-Venue-Topic` | `Talk-2024-NeurIPS-GraphOpt` |
| Service | `Service-Type-Organization` | `Service-Reviewer-NeurIPS` |
| Reference | `Ref-FirstnameLastname` | `Ref-MariaSchmidt` |
| Skill | `Skill-Name` | `Skill-Python` |

## License

MIT License — feel free to use, modify, and share.

## Contributing

Contributions are welcome! If you have ideas for improving the vault structure, templates, or documentation:

1. Fork the repo
2. Create a feature branch
3. Submit a pull request
