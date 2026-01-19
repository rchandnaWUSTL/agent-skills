# Terraform Agent Kit

A collection of Agent skills and Claude Code plugins for Terraform and infrastructure-as-code development.

## Installation

### Individual Skills 

Install Agent Skills in GitHub Copilot, Claude Code, Opencode, Cursor, and more. Skills can be installed to any of [these supported agents](https://github.com/vercel-labs/add-skill?tab=readme-ov-file#available-agents). Use -g, --global to install to the global path instead of project-level.

```bash
# List all skills
npx add-skill hashicorp/terraform-agent-kit

# Install a specific skill
npx add-skill hashicorp/terraform-agent-kit/skills/terraform-code-generation/skills/terraform-style-guide
```

### Claude Code Plugin

First, add the marketplace, then install plugins:

```bash
# Add the terraform-agent-kit marketplace
claude plugin marketplace add hashicorp/terraform-agent-kit

# Install plugins
claude plugin install terraform-code-generation@terraform-agent-kit
claude plugin install terraform-module-generation@terraform-agent-kit
claude plugin install terraform-provider-development@terraform-agent-kit
```

Or use the interactive interface:
```bash
/plugin
```
## Plugins

### terraform-code-generation

Skills for generating and validating Terraform HCL code.

| Skill | Description |
|-------|-------------|
| terraform-style-guide | Generate Terraform HCL code following HashiCorp style conventions and best practices |
| terraform-test | Writing and running `.tftest.hcl` test files |
| azure-verified-modules | Azure Verified Modules (AVM) requirements and certification |

### terraform-module-generation

Skills for creating and refactoring Terraform modules.

| Skill | Description |
|-------|-------------|
| refactor-module | Transform monolithic configs into reusable modules |
| terraform-stacks | Multi-region/environment orchestration with Terraform Stacks |

### terraform-provider-development

Skills for developing Terraform providers.

| Skill | Description |
|-------|-------------|
| new-terraform-provider | Scaffold a new Terraform provider |
| run-acceptance-tests | Run and debug provider acceptance tests |
| provider-actions | Implement provider actions (lifecycle operations) |
| provider-resources | Implement resources and data sources |

## Structure

```
terraform-agent-kit/
├── skills/
│   ├── terraform-code-generation/
│   │   ├── .claude-plugin/plugin.json
│   │   └── skills/
│   ├── terraform-module-generation/
│   │   ├── .claude-plugin/plugin.json
│   │   └── skills/
│   └── terraform-provider-development/
│       ├── .claude-plugin/plugin.json
│       └── skills/
├── .claude-plugin/marketplace.json
├── README.md
└── AGENTS.md
```

Each skill contains:
- `SKILL.md` - Agent instructions with YAML frontmatter
- Optional `assets/`, `references/` directories

## License

MPL-2.0
