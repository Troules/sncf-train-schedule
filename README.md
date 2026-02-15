# Troules Marketplace — Claude Code Plugins

A marketplace of Claude Code plugins by [Troules](https://github.com/Troules).

## Available Plugins

| Plugin | Description |
|--------|-------------|
| [sncf-train-schedule](#sncf-train-schedule) | Check French train schedules, departures, arrivals, and plan journeys using the SNCF/Navitia API |

---

## Installation

### Add the marketplace

```bash
/plugin marketplace add Troules/troules-marketplace
```

### Install a plugin

```bash
/plugin install sncf-train-schedule
```

### Manual install

```bash
git clone https://github.com/Troules/troules-marketplace
claude --plugin-dir ./troules-marketplace/sncf-train-schedule
```

---

## sncf-train-schedule

A Claude Code plugin for checking French train schedules, departures, arrivals, and planning journeys using the SNCF/Navitia API.

### Prerequisites

1. **API Token**: Register at https://numerique.sncf.com/startup/api/token-developpeur/ for a free token
2. Set the token as an environment variable:
   ```bash
   export NAVITIA_API_TOKEN="your-token-here"
   ```
   Or create a `.env` file in the plugin directory:
   ```bash
   echo 'NAVITIA_API_TOKEN=your-token-here' > .env
   ```

### Quick Start

Once installed, ask Claude about French trains:

- "What are the next trains from Paris Gare de Lyon?"
- "Plan a journey from Paris to Marseille tomorrow at 3pm"
- "Show me arrivals at Lyon Part-Dieu"
- "When is the next train to Bordeaux?"

### Features

- Real-time departures and arrivals
- Journey planning with transfers and CO2 emissions
- Station search and autocomplete
- Delay and disruption information
- Platform and track details
- Saved search results (private, gitignored `results/` folder)

### Configuration

| Variable | Description | Required |
|----------|-------------|----------|
| `NAVITIA_API_TOKEN` | Navitia API token | Yes |

### Plugin Structure

```
sncf-train-schedule/
├── .claude-plugin/
│   └── plugin.json              # Plugin manifest
├── skills/
│   └── sncf-train-schedule/
│       ├── SKILL.md             # Core skill instructions
│       ├── references/
│       │   └── api-reference.md # Detailed API docs
│       ├── examples/
│       │   └── usage-examples.md
│       └── scripts/
│           ├── save-journey.sh  # Journey result saver
│           └── test-api.sh      # API test script
├── hooks/
│   ├── hooks.json               # Hook manifest
│   ├── check-token.sh           # Token validation (SessionStart)
│   └── validate-bash-security.sh # Security check (PreToolUse)
```

### Testing

```bash
# Structure tests (no token needed)
bash tests/test-plugin-structure.sh

# API tests (requires token)
export NAVITIA_API_TOKEN="your-token"
bash tests/test-api-integration.sh
```

---

## Resources

- [Navitia API Documentation](https://doc.navitia.io/)
- [SNCF Open Data](https://numerique.sncf.com/ressources/api/)

## Contributing

See [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## License

MIT License — see [LICENSE](LICENSE) for details.
