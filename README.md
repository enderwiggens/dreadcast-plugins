# Dreadcast plugins

Assistant plugins for [Dreadcast: Radar & Weather](https://dreadcast.app), the
macOS weather and radar app.

## Claude Code

The `dreadcast` plugin connects Claude Code to the Dreadcast app on your Mac. It
adds Dreadcast's MCP server, a skill with Dreadcast's honesty rules (quote
official alert text, never turn missing data into reassurance) and a
`/dreadcast:weather` command.

```text
/plugin marketplace add enderwiggens/dreadcast-plugins
/plugin install dreadcast@dreadcast
```

It needs Dreadcast installed in `/Applications`, with assistant access allowed
in Dreadcast → Settings → Assistants. If you keep Dreadcast elsewhere, edit the
plugin's `.mcp.json`.

The plugin only starts `dreadcast-mcp`, the helper bundled inside the app. It
contains no weather code and sends nothing anywhere itself; read tools never
change anything, map changes show an Undo button, and location or notification
changes always ask you in Dreadcast.

## Layout

```text
.claude-plugin/marketplace.json   the marketplace Claude Code reads
plugins/dreadcast/                the Claude Code plugin
```

## License

MIT. Dreadcast itself is a separate app with its own terms.
