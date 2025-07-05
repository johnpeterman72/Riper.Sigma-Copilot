# σ₃: Technical Context
*v1.0 | Created: 2025-07-05 | Updated: 2025-07-05*
*Π: DEVELOPMENT | Ω: EXECUTE*

## 🛠️ Technology Stack

### 🖥️ Frontend/Interface
- **GitHub Copilot**: Primary AI interface (Chat, Edit, Agent modes)
- **VS Code**: Development environment with Copilot integration
- **Custom Chat Mode**: `.chatmode.md` configuration files
- **Markdown**: Documentation and framework definition format

### ⚙️ Backend/Processing
- **Model Context Protocol (MCP)**: Tool integration standard
- **Node.js**: Runtime for MCP servers
- **NPX**: Package execution for MCP servers
- **JSON**: Configuration and data exchange format

### 🗄️ Data Storage
- **File System**: Local markdown files for memory bank
- **Git**: Version control and change tracking
- **Relative Paths**: Cross-platform compatibility
- **Timestamped Backups**: Data protection strategy

### 🚀 Integration/Services
- **MCP Filesystem Server**: `@modelcontextprotocol/server-filesystem`
- **MCP GitHub Server**: `@modelcontextprotocol/server-github`
- **GitHub Repository**: Source control and collaboration
- **Environment Variables**: API key management

## 🌍 Environment Setup

### Development Environment
- **VS Code Version**: Latest stable with GitHub Copilot extension
- **GitHub Copilot Plan**: Pro/Pro+ (required for Claude 4 access)
- **Node.js**: v16+ for MCP server support
- **Git**: For version control and repository operations
- **MCP Setting**: `"chat.mcp.enabled": true` in VS Code

### Configuration Files
- `.vscode/mcp.json`: MCP server configuration
- `.github/chatmodes/riper.chatmode.md`: Custom chat mode
- `.github/copilot-instructions.md`: Repository instructions
- `.memory-bank/`: Memory bank directory structure

### Required Environment Variables
- `GITHUB_TOKEN`: Personal access token for GitHub MCP server
- Optional: Additional API keys for extended MCP services

## 📦 Dependencies

### Core Dependencies
- **GitHub Copilot Extension**: VS Code extension for AI assistance
- **MCP Filesystem Server**: Local file operations
- **Node.js Runtime**: MCP server execution environment

### Development Dependencies
- **MCP GitHub Server**: Repository operations (optional)
- **Git CLI**: Command line operations
- **Markdown Tools**: Documentation editing and preview

### Optional Dependencies
- **Additional MCP Servers**: Web search, Docker, Puppeteer
- **VS Code Extensions**: Markdown preview, Git integration
- **Documentation Tools**: For extended documentation generation

## 🔧 Platform Considerations

### GitHub Copilot Limitations
- **No Automatic Memory**: Requires explicit command usage
- **Rate Limiting**: Claude 4 models have usage restrictions
- **Context Format**: Must use # symbols not @ symbols
- **Mode Restrictions**: Different capabilities per mode (Chat/Edit/Agent)

### MCP Integration Requirements
- **Server Installation**: NPM packages must be globally installed
- **Configuration**: Proper .vscode/mcp.json setup required
- **Permissions**: Workspace trust needed for full functionality
- **Network Access**: Some servers require internet connectivity

### Cross-Platform Compatibility
- **Relative Paths**: All paths use ./ prefix for portability
- **Path Separators**: Forward slashes for cross-platform support
- **Environment Variables**: Standard ${VAR} syntax
- **File Encoding**: UTF-8 for all text files

## 🚨 Known Issues & Workarounds

### Memory Persistence Issue
- **Issue**: Automatic memory updates don't work in GitHub Copilot
- **Workaround**: Use explicit !update_* commands
- **Status**: By design - requires manual management

### Rate Limiting
- **Issue**: Claude 4 models hit rate limits quickly
- **Workaround**: Switch to GPT models for heavy usage
- **Status**: Platform limitation - monitor usage

### Context Symbol Compatibility
- **Issue**: Original @ symbols don't work in GitHub Copilot
- **Workaround**: Updated all references to # symbols
- **Status**: Resolved - breaking change from original

### MCP Server Dependencies
- **Issue**: Additional setup required for full functionality
- **Workaround**: Clear installation and configuration guide
- **Status**: Documented - user responsibility

---
*Use !update_tech(content) to update this file*