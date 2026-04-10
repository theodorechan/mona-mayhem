# Recommended MCP Servers for Mona Mayhem

This guide describes useful Model Context Protocol (MCP) servers for working on this Astro project with GitHub Copilot (CLI, VS Code, or other supported clients).

## Recommended MCP Servers

### Playwright MCP
**For**: Web testing, automation, visual regression testing
- Enables Copilot to interact with the running Astro app
- Perfect for building and validating UI features
- Capture screenshots for design validation
- Run automated browser tests

### Node Tools MCP
**For**: Script execution, npm task management
- Run npm commands directly (build, dev, test)
- Execute custom Node.js scripts
- Useful for troubleshooting build issues

### Git Tools MCP
**For**: Version control operations
- View commit history
- Check branch status
- Review diffs
- Helpful for understanding code changes during workshops

### Filesystem MCP
**For**: File operations
- Read/write files across the project
- Browse directory structures
- Useful for scaffolding new pages and API routes

## Installation & Setup

### Copilot CLI Users

Add these to your `.copilot/mcp-servers.json` or configure via:
```bash
copilot mcp add playwright
copilot mcp add node-tools
copilot mcp add git-tools
copilot mcp add filesystem
```

Verify installation:
```bash
copilot mcp list
```

### VS Code Users

Install the [GitHub Copilot extension](https://marketplace.visualstudio.com/items?itemName=GitHub.copilot) and enable MCP server support in settings.

## Typical Workflows

**Building a Feature**
1. Use Git Tools to review existing code patterns
2. Use Copilot with Node Tools to run `npm run dev`
3. Use Playwright to test the feature in the running app
4. Use Filesystem tools for scaffolding new files

**Debugging**
1. Git Tools to check recent changes
2. Node Tools to run `npm run build` and see errors
3. Filesystem to inspect relevant files

**Design Validation**
1. Playwright to capture screenshots
2. Validate retro arcade aesthetic consistency

## Notes

- MCP servers run in your local environment (CLI) or VS Code—not on the cloud agent
- For cloud agent configuration, see `.github/workflows/copilot-setup-steps.yml`
- Playwright requires a running dev server (use `npm run dev` first)
