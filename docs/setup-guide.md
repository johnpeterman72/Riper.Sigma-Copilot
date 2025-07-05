# CursorRIPER Σ GitHub Copilot Setup Guide

## 📋 Prerequisites

### Required Software
- **VS Code**: Latest stable version
- **GitHub Copilot Extension**: Installed and activated
- **GitHub Copilot Subscription**: Pro, Pro+, Business, or Enterprise
- **Node.js**: v16 or higher (for MCP servers)
- **Git**: For version control operations

### Required Accounts & Access
- **GitHub Account**: With Copilot subscription
- **GitHub Personal Access Token**: For MCP GitHub server (optional)
- **Workspace Permissions**: Trusted workspace in VS Code

## 🚀 Installation Steps

### Step 1: Enable MCP Support in VS Code
1. Open VS Code Settings (Ctrl/Cmd + ,)
2. Search for "mcp"
3. Enable: `"chat.mcp.enabled": true`
4. Restart VS Code if required

### Step 2: Install MCP Servers
```bash
# Required: Filesystem operations
npm install -g @modelcontextprotocol/server-filesystem

# Optional: GitHub operations
npm install -g @modelcontextprotocol/server-github
```

### Step 3: Download CursorRIPER Σ GitHub Copilot Edition
1. Clone or download the RiperCoPilot directory
2. Place in your preferred projects location
3. Open the directory in VS Code
4. Trust the workspace when prompted

### Step 4: Configure MCP Servers
The `.vscode/mcp.json` file is pre-configured. Verify the configuration:

```json
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-filesystem"],
      "config": {
        "directories": [
          "./.memory-bank/",
          "./docs/",
          "./"
        ]
      }
    },
    "github": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_TOKEN": "${GITHUB_TOKEN}"
      }
    }
  }
}
```

### Step 5: Set Environment Variables (Optional)
For GitHub MCP server functionality:
```bash
# Windows
set GITHUB_TOKEN=your_github_token_here

# macOS/Linux
export GITHUB_TOKEN=your_github_token_here
```

### Step 6: Activate Custom Chat Mode
1. Open GitHub Copilot Chat in VS Code
2. Click the mode dropdown (should show "ask", "edit", "agent")
3. Look for "riper" in the custom modes list
4. Select "riper" mode

## ✅ Verification Steps

### Test 1: Memory Bank Access
1. In Copilot Chat, type: `!memory_status()`
2. Should show list of memory bank files
3. Type: `#file: .memory-bank/activeContext.md`
4. Should reference the active context file

### Test 2: Mode Transitions
1. Type: `/r` or `/research`
2. Response should start with `[MODE: RESEARCH]`
3. Test other modes: `/i`, `/p`, `/e`, `/rev`

### Test 3: MCP Integration
1. Try: `!read_context()`
2. Should read activeContext.md via MCP
3. Try: `!update_context("Test update")`
4. Should update the file

### Test 4: Context References
1. Type: `#file: ripersigma-copilot-v105.md`
2. Should reference the main framework file
3. Type: `#codebase`
4. Should provide codebase context

## 🔧 Configuration Options

### Custom Chat Mode Customization
Edit `.github/chatmodes/riper.chatmode.md` to:
- Modify mode behavior descriptions
- Add project-specific instructions
- Customize memory commands
- Adjust tool availability

### MCP Server Customization
Modify `.vscode/mcp.json` to:
- Add additional MCP servers
- Change directory permissions
- Configure server-specific options
- Set custom environment variables

### Repository Instructions
Edit `.github/copilot-instructions.md` to:
- Add project-specific guidance
- Customize coding standards
- Set team preferences
- Define project conventions

## 🚨 Troubleshooting Common Issues

### Issue: Custom Chat Mode Not Appearing
**Symptoms**: "riper" mode not in dropdown
**Solutions**:
1. Verify `.github/chatmodes/riper.chatmode.md` exists
2. Restart VS Code
3. Check workspace is trusted
4. Verify GitHub Copilot extension is latest version

### Issue: Memory Commands Not Working
**Symptoms**: `!update_*` commands have no effect
**Solutions**:
1. Check MCP filesystem server is installed: `npm list -g | grep filesystem`
2. Verify `.vscode/mcp.json` configuration
3. Ensure workspace is trusted
4. Restart VS Code after MCP changes

### Issue: Context References Failing
**Symptoms**: `#file:` references not working
**Solutions**:
1. Use correct syntax: `#file: filename.md`
2. Verify file exists in workspace
3. Check file permissions
4. Try relative paths: `#file: ./memory-bank/activeContext.md`

### Issue: Rate Limiting
**Symptoms**: "Rate limited" errors
**Solutions**:
1. Switch from Claude 4 to GPT models
2. Use shorter, more focused prompts
3. Space out requests over time
4. Consider upgrading Copilot plan

### Issue: MCP Servers Not Starting
**Symptoms**: MCP tools not available in Agent mode
**Solutions**:
1. Check Node.js installation: `node --version`
2. Verify MCP servers installed: `npm list -g`
3. Check environment variables are set
4. Review VS Code Developer Console for errors

## 📊 Performance Optimization

### Memory Management
- Use `!backup_memory()` before major changes
- Regular `!memory_status()` checks
- Clean up old backups periodically
- Monitor memory bank file sizes

### Rate Limit Management
- Use appropriate mode for task complexity
- Agent mode only for multi-file operations
- Switch to GPT models for heavy usage
- Break large tasks into smaller chunks

### Context Efficiency
- Reference specific files vs. entire codebase
- Use pinned context for frequently accessed files
- Clear context when switching focus areas
- Monitor context attachment sizes

## 🎯 Best Practices

### Framework Usage
1. **Always declare mode** with `[MODE: MODE_NAME]`
2. **Use explicit memory commands** for persistence
3. **Follow mode restrictions** for safety
4. **Regular backups** before major changes
5. **Validate implementations** in Review mode

### GitHub Copilot Integration
1. **Use appropriate mode** for each task type
2. **Monitor usage** to avoid rate limits
3. **Leverage MCP tools** for enhanced functionality
4. **Keep documentation current** for team collaboration
5. **Test changes** before committing

### Workflow Optimization
1. **Start with Research** to understand requirements
2. **Innovate** to explore solution approaches
3. **Plan** comprehensively before implementation
4. **Execute** with Agent mode for complex changes
5. **Review** to ensure quality and compliance

## 📚 Additional Resources

- **Framework Documentation**: `ripersigma-copilot-v105.md`
- **Memory Commands**: `memory-commands.md`
- **Migration Guide**: `docs/migration-guide.md`
- **Troubleshooting**: `docs/troubleshooting.md`
- **GitHub Copilot Docs**: [docs.github.com/copilot](https://docs.github.com/copilot)
- **MCP Documentation**: [modelcontextprotocol.io](https://modelcontextprotocol.io)

## 🆘 Getting Help

### Self-Help Resources
1. Check this setup guide thoroughly
2. Review troubleshooting documentation
3. Verify all prerequisites are met
4. Test with minimal configuration first

### Community Support
- **GitHub Issues**: Report bugs and feature requests
- **GitHub Discussions**: Community questions and tips
- **Documentation Updates**: Contribute improvements
- **Best Practices**: Share successful configurations

**Setup Status**: Follow this guide step-by-step for optimal results. The framework is designed to be self-contained once properly configured.