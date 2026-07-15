# Claude Skills and Plugins

Organizational hub for Claude skills and Cowork plugins. Extend Claude's capabilities with custom workflows and integrations tailored to your team's needs.

## Overview

This repository contains reusable skills and plugins that integrate Claude with your tools and workflows. Install them in Cowork to automate common tasks across your team.

## Available Plugins

### slack-to-wrike
Convert Slack threads into Wrike tickets instantly. Capture action items from team conversations without manual data entry.

- **Skill:** `/slack-to-wrike-ticket`
- **Features:** Thread scanning, deduplication, Slack confirmation
- **Default Folder:** "a) New Form Submissions" (Wrike)
- **Status:** Production Ready

[View slack-to-wrike Plugin](./slack-to-wrike/)

### partner-intel
Quick partner account status from Wrike and optional Jira data. See campaigns, ownership, blockers, and recent activity at a glance.

- **Skill:** `/partner-intel`
- **Features:** Wrike integration, optional Jira lookup, concise summaries
- **Data Sources:** Wrike (primary), Jira (optional)
- **Status:** Production Ready

[View partner-intel Plugin](./partner-intel/)

## Installation

### Install a Plugin

1. Download the `.plugin` file from the plugin folder
2. Open Cowork on your desktop
3. Double-click the `.plugin` file to install
4. Authorize any required integrations (Slack, Wrike, Jira)

### Verify Installation

Once installed, ask Claude: "What plugins do I have?" or try a skill directly:
- "Create a Wrike ticket for this Slack thread"
- "Status for Nike"

## Setup & Configuration

### Required Connections

Before using plugins, ensure these are connected in Cowork:

**slack-to-wrike:**
- Slack workspace (read access to channels)
- Wrike account (task creation access)

**partner-intel:**
- Wrike account (primary)
- Jira account (optional, for technical issues)

### Authorize Integrations

1. Go to Cowork Settings > Capabilities
2. Find each connector (Slack, Wrike, Jira)
3. Authorize with your credentials
4. Confirm connection status

### Customize Settings

Some plugins support custom configurations:

**slack-to-wrike:**
- Custom Wrike folder destination
- Custom scan channels
- Custom approval workflows

Contact your admin to customize.

## How to Use

### slack-to-wrike Skill

**Create a ticket from a thread:**
```
"Create a Wrike ticket for this" 
[paste Slack thread link]
```

**Scan a channel:**
```
"Check #production_leads for threads to ticket"
```

### partner-intel Skill

**Get partner status:**
```
"Status for Nike"
"What's happening with GPUS"
"Catch me up on Backcountry, include Jira"
```

## Contributing

### Proposing a New Skill

Have an idea for a skill that would help your team? Here's how to propose it:

1. **Describe the need** - What problem does it solve?
2. **Document the workflow** - What steps should it automate?
3. **Identify integrations** - What tools does it need?
4. **Submit to admin** - Contact your Cowork administrator

### Building a New Plugin

If you're a developer, you can build and contribute plugins:

1. Follow the [Plugin Development Guide](#plugin-development-guide)
2. Test locally in Cowork
3. Get admin review
4. Submit PR to this repository

## Plugin Structure

Each plugin folder contains:

```
plugin-name/
├── .claude-plugin/
│   └── plugin.json          # Plugin manifest
├── skills/
│   └── skill-name/
│       ├── SKILL.md         # Skill documentation
│       └── references/      # Detailed guides (optional)
├── README.md                # Plugin overview
└── [other assets]
```

## Troubleshooting

### Connection Issues

**"Slack connection failed"**
- Verify your Slack workspace is authorized in Cowork Settings
- You may need to re-authorize with updated permissions

**"Wrike folder not found"**
- Contact your admin to verify the default folder path
- Specify a different folder ID if needed

### Plugin Not Appearing

- Restart Cowork after installation
- Check that all required connections are authorized
- Verify the .plugin file wasn't corrupted during download

### Can't Create Tickets / Get Data

- Ensure your account has access to the target Wrike/Jira projects
- Check that your user has appropriate permissions in those tools
- Ask your admin about team-level access restrictions

## Plugin Development Guide

### Creating a New Plugin

1. Create plugin directory structure
2. Write plugin.json manifest
3. Create skills in skills/*/SKILL.md format
4. Add comprehensive README.md
5. Test in Cowork
6. Submit for review

### Plugin Requirements

- Name: kebab-case, lowercase with hyphens
- Version: semver format (0.1.0 minimum)
- Author: Your name or team
- Documentation: README covering setup and usage
- Skills: SKILL.md with frontmatter and body

### Naming Conventions

- Plugin names: `kebab-case` (e.g., `slack-to-wrike`)
- Skill paths: `/kebab-case-action` (e.g., `/slack-to-wrike-ticket`)
- Files: snake_case for config, SKILL.md for skills

## Organization Standards

### Code Quality

- Skills should be self-contained
- Documentation must be clear and concise
- All integrations must be tested
- Error handling should be robust

### Security

- Never hardcode credentials
- Use environment variables for secrets
- Request minimal necessary permissions
- Document all data flows

### Support

- Include troubleshooting section in README
- Document common error scenarios
- Provide contact for support questions
- Keep documentation up to date

## Updates & Versioning

Plugins use semantic versioning:

- **MAJOR.MINOR.PATCH** (e.g., 0.1.0)
- MAJOR: Breaking changes
- MINOR: New features
- PATCH: Bug fixes

Check the plugin folder for release notes and version history.

## Team Resources

### Getting Help

- **Installation issues:** Contact Cowork Admin
- **Integration questions:** See plugin README
- **Feature requests:** Submit via issue in this repo
- **Bug reports:** Include plugin name and error details

### Related Documentation

- [Cowork Setup Guide](link-to-internal-docs)
- [Tool Integration Guides](link-to-internal-docs)
- [Plugin Marketplace](link-to-marketplace)

## Roadmap

Planned plugins and improvements:

- [ ] Additional Wrike automation skills
- [ ] Jira workflow automation
- [ ] Calendar and meeting integrations
- [ ] Advanced reporting dashboards
- [ ] Custom field mappings

Have a suggestion? Let your admin know.

## Support

Questions or issues with any plugin?

- Check the plugin's README for detailed setup
- Review the troubleshooting section
- Contact your Cowork administrator
- Submit feedback via your organization's process

## License

All plugins in this repository are maintained by the organization and available to team members with appropriate access.

---

**Last Updated:** July 16, 2026  
**Maintainer:** Aditya Anmol  
**Repository:** https://github.com/adityanmol/claudeSkillsandPlugins
