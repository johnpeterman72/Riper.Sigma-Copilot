# Troubleshooting CursorRIPER Σ on GitHub Copilot

## 🚨 Common Issues & Solutions

### 1. Memory Bank Not Updating

#### Symptoms
- Memory bank files show old content
- `!update_*` commands appear to work but files unchanged
- Context not persisting between sessions

#### Diagnostic Steps
```
1. Check memory status: !memory_status()
2. Verify file exists: #file: .memory-bank/activeContext.md
3. Test MCP server: Try file operations in Agent mode
4. Check workspace trust: Look for "Restricted Mode" in VS Code
```

#### Solutions
**Solution A: MCP Server Issue**
```bash
# Check if MCP filesystem server is installed
npm list -g | grep filesystem

# Reinstall if missing
npm install -g @modelcontextprotocol/server-filesystem

# Restart VS Code after installation
```

**Solution B: Workspace Trust**
```
1. Check VS Code status bar for lock/shield icon
2. Click "Trust Workspace" if prompted
3. Reload VS Code window (Ctrl/Cmd + Shift + P → "Reload Window")
```

**Solution C: MCP Configuration**
```json
// Verify .vscode/mcp.json contains:
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-filesystem"],
      "config": {
        "directories": ["./.memory-bank/", "./docs/", "./"]
      }
    }
  }
}
```

**Solution D: File Permissions**
```bash
# Windows - Run as administrator once, then return to normal
# macOS/Linux - Check directory permissions
chmod 755 .memory-bank/
chmod 644 .memory-bank/*.md
```

### 2. Custom Chat Mode Not Loading

#### Symptoms
- "riper" mode not appearing in chat mode dropdown
- Default chat modes only (ask, edit, agent)
- Custom instructions not being applied

#### Diagnostic Steps
```
1. Check file exists: .github/chatmodes/riper.chatmode.md
2. Verify GitHub Copilot extension is latest version
3. Check workspace structure and trust
4. Look for errors in VS Code Developer Console
```

#### Solutions
**Solution A: File Location**
```
Ensure exact path: .github/chatmodes/riper.chatmode.md
File must be in workspace root
File must have .chatmode.md extension
```

**Solution B: File Format**
```yaml
# Verify file starts with YAML frontmatter:
---
description: CursorRIPER Σ Framework for GitHub Copilot
tools: [filesystem, github]
---
```

**Solution C: Extension Update**
```
1. Open VS Code Extensions panel
2. Search for "GitHub Copilot"
3. Update if newer version available
4. Restart VS Code
```

**Solution D: Workspace Reload**
```
1. Close VS Code completely
2. Reopen workspace folder
3. Trust workspace when prompted
4. Wait for extensions to fully load
```

### 3. Context References Not Working

#### Symptoms
- `#file:` references not resolving
- "File not found" errors
- Context not being included in chat

#### Diagnostic Steps
```
1. Test basic reference: #file: README.md
2. Check file paths with: !memory_status()
3. Verify relative vs absolute paths
4. Test with different file types
```

#### Solutions
**Solution A: Correct Syntax**
```
✅ Correct: #file: .memory-bank/activeContext.md
✅ Correct: #file: docs/setup-guide.md
✅ Correct: #codebase
❌ Wrong: @Files activeContext.md
❌ Wrong: #file .memory-bank/activeContext.md (missing colon)
```

**Solution B: File Path Issues**
```
# Use relative paths from workspace root
#file: ./memory-bank/progress.md    # If no dot prefix
#file: .memory-bank/progress.md     # With dot prefix
#file: docs/troubleshooting.md      # Documentation files
```

**Solution C: File Existence**
```
1. Verify file exists in workspace
2. Check exact filename and extension
3. Ensure no typos in path
4. Use VS Code file explorer to confirm path
```

### 4. Rate Limiting Issues

#### Symptoms
- "Rate limited" or "Too many requests" errors
- Claude 4 responses being blocked
- Frequent service unavailable messages

#### Diagnostic Steps
```
1. Check current model in use (Claude 4 vs GPT)
2. Monitor frequency of requests
3. Check GitHub Copilot plan limits
4. Verify usage patterns
```

#### Solutions
**Solution A: Switch Models**
```
1. In GitHub Copilot Chat, click model dropdown
2. Switch from Claude 4 to GPT-4 or GPT-3.5
3. Use Claude 4 only for complex tasks
4. Monitor usage and switch back when limits reset
```

**Solution B: Optimize Usage**
```
# Use appropriate mode for task complexity
- Simple questions: Chat mode with GPT
- Complex planning: Edit mode
- Multi-file work: Agent mode (sparingly)
- Reviews: Chat mode with specific file references
```

**Solution C: Request Spacing**
```
# Space out major operations
1. Complete one mode fully before switching
2. Allow time between large requests
3. Use shorter, focused prompts
4. Break large tasks into smaller chunks
```

### 5. MCP Servers Not Starting

#### Symptoms
- MCP tools not available in Agent mode
- "No tools available" messages
- Filesystem operations failing

#### Diagnostic Steps
```
1. Check Node.js version: node --version
2. Verify MCP server installation: npm list -g
3. Test MCP configuration syntax
4. Check VS Code Developer Console for errors
```

#### Solutions
**Solution A: Node.js Issues**
```bash
# Update Node.js to v16 or higher
# Windows: Download from nodejs.org
# macOS: brew install node
# Linux: Use package manager

# Verify version
node --version  # Should be v16+
npm --version   # Should be v8+
```

**Solution B: MCP Server Installation**
```bash
# Clean installation
npm uninstall -g @modelcontextprotocol/server-filesystem
npm install -g @modelcontextprotocol/server-filesystem

# Verify installation
npx @modelcontextprotocol/server-filesystem --help
```

**Solution C: Configuration Issues**
```json
// Check .vscode/mcp.json syntax
{
  "mcpServers": {
    "filesystem": {
      "command": "npx",
      "args": ["@modelcontextprotocol/server-filesystem"],
      "config": {
        "directories": ["./.memory-bank/", "./"]
      }
    }
  }
}
```

**Solution D: Environment Variables**
```bash
# For GitHub MCP server
# Windows
set GITHUB_TOKEN=your_token_here

# macOS/Linux
export GITHUB_TOKEN=your_token_here

# Verify
echo $GITHUB_TOKEN  # Should show your token
```

### 6. Mode Transitions Not Working

#### Symptoms
- `/r`, `/i`, `/p` commands not changing mode
- Mode declarations missing from responses
- Framework not following mode restrictions

#### Diagnostic Steps
```
1. Test basic mode transition: /r
2. Check for [MODE: X] in responses
3. Verify custom chat mode is selected
4. Test with fresh chat session
```

#### Solutions
**Solution A: Custom Chat Mode**
```
1. In GitHub Copilot Chat, check mode dropdown
2. Ensure "riper" is selected (not "ask", "edit", or "agent")
3. If not visible, check .github/chatmodes/riper.chatmode.md
4. Restart VS Code if needed
```

**Solution B: Command Format**
```
✅ Correct: /r
✅ Correct: /research
✅ Correct: /innovate
❌ Wrong: \r
❌ Wrong: /research mode
❌ Wrong: /R (case sensitive)
```

**Solution C: Fresh Session**
```
1. Start new chat session
2. Ensure custom chat mode selected
3. Test mode transition
4. Clear chat history if needed
```

## 🔧 Advanced Troubleshooting

### Debug Mode Setup
1. **Enable VS Code Developer Tools**:
   - Help → Toggle Developer Tools
   - Check Console for errors
   - Look for GitHub Copilot related messages

2. **MCP Server Debugging**:
   ```bash
   # Test MCP server directly
   npx @modelcontextprotocol/server-filesystem
   
   # Check for error messages
   # Verify directory permissions
   ```

3. **Network Connectivity**:
   ```bash
   # Test GitHub connectivity
   curl -H "Authorization: token YOUR_TOKEN" https://api.github.com/user
   
   # Test MCP server endpoints
   ```

### Performance Diagnostics
1. **Memory Usage**:
   - Monitor VS Code memory usage
   - Check for large file operations
   - Clear workspace cache if needed

2. **File System Performance**:
   - Test file read/write speeds
   - Check disk space availability
   - Verify antivirus not blocking operations

3. **Network Performance**:
   - Test internet connectivity
   - Check proxy settings
   - Verify firewall not blocking

### Configuration Validation
```bash
# Validate JSON files
node -e "console.log(JSON.parse(require('fs').readFileSync('.vscode/mcp.json', 'utf8')))"

# Check file permissions
ls -la .memory-bank/
ls -la .github/chatmodes/

# Verify Node.js modules
npm list -g | grep modelcontextprotocol
```

## 📊 Diagnostic Checklist

### Before Reporting Issues
- [ ] VS Code and GitHub Copilot extension updated
- [ ] Workspace trusted in VS Code
- [ ] MCP servers installed and configured
- [ ] Custom chat mode file exists and correct
- [ ] Memory bank directory structure correct
- [ ] No firewall/antivirus blocking operations
- [ ] GitHub Copilot subscription active
- [ ] Environment variables set if needed

### Information to Collect
- VS Code version and GitHub Copilot extension version
- Operating system and Node.js version
- Error messages from Developer Console
- MCP server installation status
- Workspace configuration details
- Steps to reproduce the issue

## 🆘 Getting Additional Help

### Self-Service Resources
1. **Framework Documentation**: `ripersigma-copilot-v105.md`
2. **Setup Guide**: `docs/setup-guide.md`
3. **Migration Guide**: `docs/migration-guide.md`
4. **Memory Commands**: `memory-commands.md`

### Community Support
- **GitHub Issues**: Report bugs with detailed information
- **GitHub Discussions**: Ask questions and share solutions
- **Documentation Updates**: Contribute troubleshooting improvements

### Escalation Path
1. **Check Known Issues**: Review documentation for similar problems
2. **Search Community**: Look for existing solutions
3. **Create Detailed Report**: Include all diagnostic information
4. **Follow Up**: Monitor issue status and provide updates

**Remember**: Most issues are configuration-related. Follow the setup guide carefully and verify each step before seeking additional help.