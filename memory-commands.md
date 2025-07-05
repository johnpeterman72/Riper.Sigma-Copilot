# Memory Commands for CursorRIPER Σ GitHub Copilot Edition

## 🚨 CRITICAL: Memory banks do NOT update automatically in GitHub Copilot
Unlike Cursor IDE, GitHub Copilot requires explicit commands to update memory bank files.

## 📝 Core Memory Update Commands

### Primary Memory Files
- `!update_brief(content)` - Update `.memory-bank/projectbrief.md`
- `!update_patterns(content)` - Update `.memory-bank/systemPatterns.md`
- `!update_tech(content)` - Update `.memory-bank/techContext.md`
- `!update_context(content)` - Update `.memory-bank/activeContext.md`
- `!update_progress(content)` - Update `.memory-bank/progress.md`
- `!update_protection(content)` - Update `.memory-bank/protection.md`

### Memory Read Commands
- `!read_brief()` - Read project brief
- `!read_patterns()` - Read system patterns
- `!read_tech()` - Read technical context
- `!read_context()` - Read active context
- `!read_progress()` - Read progress tracker
- `!read_protection()` - Read protection registry

### Memory Management Commands
- `!memory_status()` - List all memory bank files with modification dates
- `!backup_memory()` - Create timestamped backup of entire memory bank
- `!restore_memory(timestamp)` - Restore from backup (if needed)

## 🔄 Mode-Specific Update Workflows

### Research Mode Updates
```
!update_context("## Research Mode Active

### Current Research Focus:
[Research topic and scope]

### Key Findings:
- [Finding 1]
- [Finding 2] 
- [Finding 3]

### Technical Details Discovered:
[Relevant technical information]

### Next Research Steps:
1. [Step 1]
2. [Step 2]

Updated: " + timestamp())
```

### Innovate Mode Updates
```
!update_patterns("## Innovate Mode - Design Session

### Generated Ideas:
- [Idea 1]: [Description and rationale]
- [Idea 2]: [Description and rationale]
- [Idea 3]: [Description and rationale]

### Design Decisions:
- [Decision 1]: [Chosen approach and why]
- [Decision 2]: [Chosen approach and why]

### Architecture Considerations:
[Architectural implications]

Updated: " + timestamp())
```

### Plan Mode Updates  
```
!update_progress("## Planning Phase Complete

### Implementation Plan:
[Detailed technical plan]

### Milestones:
- [M1] [Milestone 1]: [Target date]
- [M2] [Milestone 2]: [Target date]
- [M3] [Milestone 3]: [Target date]

### Implementation Checklist:
1. [Atomic action 1]
2. [Atomic action 2]
3. [Atomic action 3]
...

### Success Criteria:
- [SC1] [Criteria 1]
- [SC2] [Criteria 2]

Status: Planning Complete - Ready for Execute Mode
Updated: " + timestamp())
```

### Execute Mode Updates
```
!update_progress("## Execute Mode - Implementation Progress

### Completed Tasks:
- [✅] [Task 1]: [Completion notes]
- [✅] [Task 2]: [Completion notes]

### In Progress:
- [⏳] [Current task]: [Status and progress]

### Upcoming:
- [🔜] [Next task]: [Planned approach]

### Issues Encountered:
- [Issue 1]: [Resolution or status]

### Files Modified:
- [File 1]: [Changes made]
- [File 2]: [Changes made]

Updated: " + timestamp())
```

### Review Mode Updates
```
!update_context("## Review Mode - Validation Results

### Implementation vs Plan Comparison:
[Detailed comparison results]

### Validation Results:
- [✅] [Requirement 1]: PASSED
- [⚠️] [Requirement 2]: DEVIATION DETECTED - [Description]
- [✅] [Requirement 3]: PASSED

### Code Quality Assessment:
[Quality observations]

### Recommendations:
1. [Recommendation 1]
2. [Recommendation 2]

### Final Verdict:
[✅ IMPLEMENTATION MATCHES PLAN | ⚠️ DEVIATIONS DETECTED]

Updated: " + timestamp())
```

## 🔧 MCP-Enhanced Memory Operations

When MCP filesystem server is available:
- `mcp_read_memory(file)` - Read memory file via MCP
- `mcp_write_memory(file, content)` - Write memory file via MCP
- `mcp_list_memory()` - List memory bank contents via MCP
- `mcp_backup_memory()` - Create backup via MCP

## 📊 Memory Bank Status Monitoring

### Check Memory Health
```
!memory_status()
```
Expected output format:
```
Memory Bank Status:
- projectbrief.md: Last modified [timestamp]
- systemPatterns.md: Last modified [timestamp]  
- techContext.md: Last modified [timestamp]
- activeContext.md: Last modified [timestamp]
- progress.md: Last modified [timestamp]
- protection.md: Last modified [timestamp]

Total files: 6
Backup count: [number]
Last backup: [timestamp]
```

## ⚠️ Common Mistakes to Avoid

1. **Forgetting to Use Commands**: Memory will NOT update without explicit commands
2. **Using @ Instead of #**: GitHub Copilot uses `#file:` not `@Files`
3. **Relative Path Issues**: Always use `./memory-bank/` or rely on MCP
4. **Mode-Specific Updates**: Each mode should update appropriate memory files
5. **Timestamp Omission**: Always include timestamps for change tracking

## 🎯 Best Practices

1. **Update After Each Mode**: Update relevant memory files when transitioning
2. **Descriptive Content**: Include context, reasoning, and next steps
3. **Regular Backups**: Use `!backup_memory()` before major operations
4. **Status Checks**: Use `!memory_status()` to verify persistence
5. **Consistent Format**: Follow mode-specific update templates

## 🔗 Integration with GitHub Copilot Modes

### Chat Mode (Research, Innovate, Review)
- Use memory commands in chat responses
- Reference memory files with `#file: .memory-bank/filename.md`
- Memory commands executed as part of conversation

### Edit Mode (Plan)
- Update progress files with planning details
- Create implementation checklists
- Document architectural decisions

### Agent Mode (Execute)
- Frequent progress updates during implementation
- Track file modifications and changes
- Document issues and resolutions in real-time

Remember: The key difference from Cursor IDE is that GitHub Copilot requires these explicit commands. The framework functionality remains the same, but persistence must be manually managed.