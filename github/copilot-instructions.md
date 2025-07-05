# CursorRIPER Σ Framework Instructions for GitHub Copilot

## Project Overview
This repository contains the CursorRIPER Σ Framework v1.0.5 GitHub Copilot Edition - a structured development methodology with 5 operational modes (Research, Innovate, Plan, Execute, Review).

## Memory Bank Management
- **Critical**: Memory bank files in `.memory-bank/` directory do NOT update automatically
- **Required**: Use explicit memory commands for all updates:
  - `!update_context(content)` - Update active context
  - `!update_progress(content)` - Update progress tracker  
  - `!update_brief(content)` - Update project brief
  - `!update_patterns(content)` - Update system patterns
  - `!update_tech(content)` - Update technical context
  - `!memory_status()` - Check memory bank status

## File Organization Standards
- Framework files: Root directory
- Memory bank: `.memory-bank/` directory (use relative paths)
- Documentation: `docs/` directory
- Configuration: `.vscode/mcp.json` for MCP servers
- Custom chat mode: `.github/chatmodes/riper.chatmode.md`

## Context Reference Conventions
- Use `#file: filename` for file references (NOT @ symbols)
- Use `#folder: foldername` for folder references
- Use `#codebase` for entire codebase references
- Use `#file: .memory-bank/` for memory bank references
- Use relative paths starting with `./` when needed

## Mode-Specific Behavior

### Research Mode (`[MODE: RESEARCH]`)
- Read-only operations only
- Document findings with `!update_context(content)`
- Use standard chat mode with file references
- No code writing or planning permitted

### Innovate Mode (`[MODE: INNOVATE]`)
- Conceptual exploration only
- Capture ideas with `!update_patterns(content)`
- Use chat mode for brainstorming
- Present possibilities, not final decisions

### Plan Mode (`[MODE: PLAN]`)
- Create detailed implementation plans
- Save plans with `!update_progress(content)`
- Use edit mode for targeted planning
- Always end with numbered implementation checklist
- No implementation until explicit approval

### Execute Mode (`[MODE: EXECUTE]`)
- **MUST use Agent mode** for multi-file operations
- Follow approved plan with 100% fidelity
- Update progress with `!update_progress(content)`
- No deviations without returning to Plan mode

### Review Mode (`[MODE: REVIEW]`)
- Validation against plans and requirements
- Document results with `!update_context(content)`
- Use chat mode with file comparisons
- Flag ANY deviations from plan

## Code Protection Standards
- Use protection markers: `!cp` (PROTECTED), `!cg` (GUARDED), `!ci` (INFO), `!cd` (DEBUG), `!ct` (TEST), `!cc` (CRITICAL)
- Respect existing protection boundaries
- Document protection changes in `protection.md`

## Response Format Requirements
- **ALWAYS** begin responses with `[MODE: MODE_NAME]`
- Update memory banks using explicit commands
- Use mathematical notation and symbolic references where appropriate
- Maintain framework's mathematical elegance

## MCP Integration
- Filesystem MCP server available for file operations
- GitHub MCP server available for repository operations
- Use MCP tools through standard GitHub Copilot interface
- Configuration in `.vscode/mcp.json`

## Error Prevention
- Never use automatic memory updates (they don't work)
- Always use `#` symbols for context, not `@` symbols
- Switch to Agent mode for Execute phase multi-file operations
- Declare mode at start of every response
- Use explicit memory commands for persistence

## Quality Standards
- Maintain framework's symbolic mathematical notation
- Preserve elegant abstraction layers
- Follow permission system restrictions
- Document all significant operations in memory bank
- Ensure traceability between modes and implementations

This framework emphasizes structured development with explicit state management optimized for GitHub Copilot's capabilities and limitations.