# Context Usage Monitor

A Claude Code plugin that displays context window usage after tool calls, helping you track token consumption during your coding sessions.

## Features

- Displays current context usage as a percentage and token count
- Configurable display frequency (every N tool calls)
- Optional warning when context exceeds a threshold
- Lightweight bash-based implementation with minimal dependencies

## Installation

```bash
/plugin install github:lllangWV/context-usage-monitor
```

## Usage

Once installed, the plugin automatically injects context usage information after tool calls:

```
[Context: 15% | 30000/200000 tokens | Tool call #10]
```

## Configuration

Edit `hooks/monitor_tokens.conf.json` to customize behavior:

```json
{
  "print_every_n": 5,
  "max_context_percent": 75,
  "context_window": 200000,
  "block_at_threshold": false
}
```

| Option | Type | Default | Description |
|--------|------|---------|-------------|
| `print_every_n` | number | 5 | Display context info every N tool calls |
| `max_context_percent` | number | 75 | Threshold percentage for warnings |
| `context_window` | number | 200000 | Total context window size in tokens |
| `block_at_threshold` | boolean | false | Show warning when threshold exceeded |

## Requirements

- Claude Code CLI
- `jq` command-line JSON processor
- Bash shell

## How It Works

The plugin registers a `PostToolUse` hook that:

1. Tracks tool call count per session
2. Reads the session transcript to get token usage data
3. Calculates context percentage from cache and input tokens
4. Outputs usage info as additional context visible to Claude

State files are stored in `~/.claude/context-usage-monitor-state/`.

## License

MIT License - see [LICENSE](LICENSE) for details.

## Contributing

Contributions are welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for guidelines.

## Changelog

See [CHANGELOG.md](CHANGELOG.md) for version history.
