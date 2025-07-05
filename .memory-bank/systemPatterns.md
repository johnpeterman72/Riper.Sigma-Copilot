# σ₂: System Patterns
*v1.0 | Created: 2025-07-05 | Updated: 2025-07-05*
*Π: DEVELOPMENT | Ω: EXECUTE*

## 🏛️ Architecture Overview
The CursorRIPER Σ GitHub Copilot Edition maintains the original framework's mathematical elegance while adapting to GitHub Copilot's operational model. Key architectural changes include explicit memory management, MCP integration, and custom chat mode implementation.

## 🧩 Components

### Core Framework Components
- **Framework Engine**: `ripersigma-copilot-v105.md` - Main framework definitions
- **Custom Chat Mode**: `.github/chatmodes/riper.chatmode.md` - GitHub Copilot integration
- **Memory Bank**: `.memory-bank/` directory - Persistent state storage
- **MCP Configuration**: `.vscode/mcp.json` - Model Context Protocol servers
- **Documentation**: `docs/` directory - Setup and usage guides

### Memory Management System
- **Explicit Commands**: Manual update commands replacing automatic updates
- **MCP Bridge**: Filesystem operations via Model Context Protocol
- **Backup System**: Timestamped backups for safety
- **Status Monitoring**: Memory bank health checking

### Mode System Adaptations
- **Research Mode**: Chat mode with file references
- **Innovate Mode**: Chat mode for conceptual work
- **Plan Mode**: Edit mode for targeted planning
- **Execute Mode**: Agent mode for multi-file operations
- **Review Mode**: Chat mode with validation focus

## 🔗 Integration Patterns

### GitHub Copilot Integration
- **Context References**: `#file:`, `#folder:`, `#codebase` syntax
- **Mode Switching**: Custom chat mode with mode transitions
- **Memory Persistence**: Explicit command-based updates
- **Tool Integration**: MCP servers for extended functionality

### MCP Integration Pattern
- **Filesystem Server**: Local file operations
- **GitHub Server**: Repository operations
- **Tool Discovery**: Dynamic capability detection
- **Error Handling**: Graceful degradation when MCP unavailable

## 📐 Design Decisions

### Memory Management Decision
- **Problem**: GitHub Copilot doesn't support automatic memory updates
- **Solution**: Explicit command system with manual updates
- **Trade-off**: More user interaction for guaranteed persistence
- **Rationale**: Reliability over automation

### Context Reference Decision
- **Problem**: GitHub Copilot uses # symbols not @ symbols
- **Solution**: Updated all context references to # format
- **Trade-off**: Breaking change from original framework
- **Rationale**: Platform compatibility requirement

### Reference Map Simplification
- **Problem**: Expanded ℜ in v1.0.5 causing parsing errors
- **Solution**: Simplified to core protection system only
- **Trade-off**: MCP services handled separately
- **Rationale**: Stability over feature integration

### Custom Chat Mode Approach
- **Problem**: Need structured framework guidance in GitHub Copilot
- **Solution**: Comprehensive .chatmode.md file with embedded instructions
- **Trade-off**: Longer configuration vs. built-in guidance
- **Rationale**: Self-contained operation

---
*Use !update_patterns(content) to update this file*
