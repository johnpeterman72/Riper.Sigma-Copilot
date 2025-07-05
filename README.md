# CursorRIPER♦Σ GitHub Copilot Edition

> A mathematically elegant, structured development framework with 5 operational modes, now optimized for GitHub Copilot.

[![GitHub Copilot](https://img.shields.io/badge/GitHub%20Copilot-Compatible-blue)](https://github.com/features/copilot)
[![MCP Integration](https://img.shields.io/badge/MCP-Integrated-green)](https://modelcontextprotocol.io)
[![Version](https://img.shields.io/badge/Version-1.0.5-brightgreen)](./ripersigma-copilot-v105.md)

## 🎯 Overview

CursorRIPER Σ (Sigma) is a structured development methodology that provides mathematically precise operational modes for software development. This GitHub Copilot edition adapts the original Cursor IDE framework to work seamlessly with GitHub Copilot's capabilities while maintaining the mathematical elegance and symbolic notation.

### The 5 RIPER Modes

- **🔍 Research (Ω₁)**: Information gathering and analysis
- **💡 Innovate (Ω₂)**: Brainstorming and ideation  
- **📝 Plan (Ω₃)**: Detailed technical specification
- **⚙️ Execute (Ω₄)**: Implementation and development
- **🔎 Review (Ω₅)**: Validation and quality assurance

## ✨ Key Features

### 🧠 Intelligent Memory Management
- **Explicit Memory Commands**: Manual control over persistent state
- **Memory Bank**: 6 specialized files for different aspects of development
- **Backup System**: Automatic and manual backup capabilities
- **Status Monitoring**: Real-time memory bank health checks

### 🔧 GitHub Copilot Integration
- **Custom Chat Mode**: Tailored interface for framework operations
- **Mode-Specific Behavior**: Different GitHub Copilot modes for different tasks
- **Context Management**: Advanced file and codebase referencing
- **Permission System**: Mode-based operation restrictions

### 🔌 MCP (Model Context Protocol) Support
- **Filesystem Operations**: Enhanced file manipulation capabilities
- **GitHub Integration**: Repository operations and collaboration
- **Tool Extensibility**: Add custom tools and services
- **Graceful Degradation**: Works with or without MCP

### 🛡️ Code Protection System
- **6 Protection Levels**: From INFO to CRITICAL
- **Region Markers**: Precise code protection boundaries
- **Modification Tracking**: Complete audit trail
- **Permission Enforcement**: Mode-based access control

## 🚀 Quick Start

### Prerequisites
- VS Code with GitHub Copilot extension
- GitHub Copilot Pro/Pro+ subscription
- Node.js v16+ (for MCP servers)

### Installation
```bash
# 1. Clone or download the project
git clone <repository-url>
cd RiperCoPilot

# 2. Install MCP servers
npm install -g @modelcontextprotocol/server-filesystem

# 3. Configure VS Code
# Add to settings.json:
"chat.mcp.enabled": true

# 4. Open project in VS Code and trust workspace
code .
```

### First Use
1. **Select Custom Chat Mode**: Choose "riper" from the chat mode dropdown
2. **Test Memory System**: `!memory_status()`
3. **Start Research**: `/r` to enter Research mode
4. **Update Context**: `!update_context("Getting started with CursorRIPER Σ")`

## 📚 Documentation

| Document | Purpose |
|----------|---------|
| [Framework Core](./ripersigma-copilot-v105.md) | Complete framework specification |
| [Setup Guide](./docs/setup-guide.md) | Installation and configuration |
| [Migration Guide](./docs/migration-guide.md) | Cursor IDE to GitHub Copilot transition |
| [Memory Commands](./memory-commands.md) | Memory management reference |
| [Troubleshooting](./docs/troubleshooting.md) | Common issues and solutions |

## 💡 Usage Examples

### Research Mode
```
/r
#file: requirements.md
#file: existing-codebase.js

Analyze the current implementation and identify areas for improvement.

!update_context("Research findings: Current system uses outdated patterns...")
```

### Plan Mode
```
/p
Based on research findings, create a comprehensive refactoring plan.

!update_progress("Refactoring Plan:
1. Update authentication system
2. Modernize API endpoints  
3. Improve error handling
...")
```

### Execute Mode
```
/e
[Switch to Agent mode in GitHub Copilot]
Implement the approved refactoring plan.

!update_progress("Implementation status: Authentication system updated, API endpoints in progress...")
```

## 🔧 Configuration

### Project Structure
```
your-project/
├── .github/
│   ├── chatmodes/
│   │   └── riper.chatmode.md     # Custom chat mode
│   └── copilot-instructions.md   # Repository instructions
├── .vscode/
│   └── mcp.json                  # MCP server configuration
├── .memory-bank/                 # Memory persistence
│   ├── projectbrief.md
│   ├── systemPatterns.md
│   ├── techContext.md
│   ├── activeContext.md
│   ├── progress.md
│   └── protection.md
├── docs/                         # Documentation
├── ripersigma-copilot-v105.md   # Framework core
└── memory-commands.md           # Command reference
```

### MCP Configuration
```json
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

## 📊 Framework Benefits

### 🎯 Structured Development
- **Clear Phases**: Defined progression through development stages
- **Permission System**: Prevents unauthorized changes
- **Memory Persistence**: Maintains context across sessions
- **Quality Gates**: Built-in validation and review processes

### 🤖 AI-Optimized
- **Mode-Specific Instructions**: Tailored AI behavior for each phase
- **Context Management**: Efficient information flow to AI
- **Explicit State**: Clear memory management for AI systems
- **Tool Integration**: Enhanced capabilities through MCP

### 🔄 Workflow Integration
- **GitHub Copilot Native**: Designed specifically for GitHub Copilot
- **Team Collaboration**: Shared instructions and chat modes
- **Version Control**: Git-friendly file-based persistence
- **Scalable**: Works for individuals and teams

## ⚡ Key Differences from Cursor IDE

| Aspect | Cursor IDE | GitHub Copilot |
|--------|------------|----------------|
| Memory Updates | Automatic | Manual commands |
| Context References | @Files | #file: |
| Path System | Absolute | Relative |
| Mode Implementation | Built-in | Custom chat mode |
| File Operations | Direct | MCP servers |
| Multi-file Edits | Standard | Agent mode |

## 🚨 Critical Usage Notes

### Memory Persistence
- **No Automatic Updates**: Use explicit `!update_*` commands
- **Regular Status Checks**: Use `!memory_status()` to verify persistence
- **Backup Before Major Changes**: Use `!backup_memory()`

### GitHub Copilot Modes
- **Research/Review**: Use Chat mode
- **Planning**: Use Edit mode for focused changes
- **Implementation**: Use Agent mode for multi-file operations

### Context References
- **File References**: `#file: filename.md`
- **Folder References**: `#folder: dirname`
- **Codebase References**: `#codebase`

## 🔍 Troubleshooting

### Common Issues
1. **Memory not updating**: Check MCP server installation
2. **Custom mode missing**: Verify file location and format
3. **Context references failing**: Use correct # syntax
4. **Rate limiting**: Switch to GPT models

See [Troubleshooting Guide](./docs/troubleshooting.md) for detailed solutions.

## 🤝 Contributing

### Development Setup
1. Fork the repository
2. Create feature branch
3. Follow framework conventions
4. Test with multiple GitHub Copilot modes
5. Update documentation

### Contribution Areas
- **Documentation improvements**
- **Additional MCP server integrations**
- **Custom chat mode enhancements**
- **Troubleshooting guides**
- **Usage examples**

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- **Original CursorRIPER Framework**: Foundation for this adaptation
- **GitHub Copilot Team**: AI coding assistance platform
- **MCP Community**: Model Context Protocol standard
- **VS Code Team**: Development environment

## 📞 Support

- **Documentation**: Start with setup and troubleshooting guides
- **Issues**: Use GitHub Issues for bug reports
- **Discussions**: Use GitHub Discussions for questions
- **Feature Requests**: Use GitHub Issues with enhancement label

---

**Framework Status**: ✅ Production Ready  
**Compatibility**: GitHub Copilot Pro/Pro+  
**Version**: 1.0.5 GitHub Copilot Edition  
**Last Updated**: July 5, 2025

> "Bringing mathematical precision to AI-assisted development workflows"