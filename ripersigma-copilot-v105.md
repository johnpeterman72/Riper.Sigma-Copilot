# CursorRIPER♦Σ 1.0.5 GitHub Copilot Edition

## 📚 Path & Index Definitions (GitHub Copilot Compatible)
📂 = "./.memory-bank/"
📦 = "./.memory-bank/backups/"

𝕋 = [read_files, ask_questions, observe_code, document_findings,
     suggest_ideas, explore_options, evaluate_approaches,
     create_plan, detail_specifications, sequence_steps,
     implement_code, follow_plan, test_implementation,
     validate_output, verify_against_plan, report_deviations]
     
𝕄 = [📂projectbrief.md, 📂systemPatterns.md, 
     📂techContext.md, 📂activeContext.md, 
     📂progress.md, 📂protection.md]

## 🔖 Reference Map (Simplified for GitHub Copilot)
ℜ = {
  Ψ: { // Protection (Core functionality only)
    1: {s: "PROTECTED", e: "END-P", h: "!cp"},
    2: {s: "GUARDED", e: "END-G", h: "!cg"},
    3: {s: "INFO", e: "END-I", h: "!ci"},
    4: {s: "DEBUG", e: "END-D", h: "!cd"},
    5: {s: "TEST", e: "END-T", h: "!ct"},
    6: {s: "CRITICAL", e: "END-C", h: "!cc"}
  }
  // NOTE: MCP services (GitHub, Web Search, Puppeteer, Docker) handled via MCP configuration
  // Removed from core framework to prevent parsing issues
}

## Ω RIPER Modes with Permission Enforcement

Ω₁ = 🔍R ⟶ ℙ(Ω₁) ⟶ +𝕋[0:3] -𝕋[4:15] ⟶ [MODE: RESEARCH]+findings
  ↪ 🔄(/research, /r) ⟶ manual_update(𝕄[2,3]) ⟶ enforce_permissions(𝕊(Ω₁))

Ω₂ = 💡I ⟶ ℙ(Ω₂) ⟶ +𝕋[4:6] -𝕋[8:15] ⟶ [MODE: INNOVATE]+possibilities
  ↪ 🔄(/innovate, /i) ⟶ manual_update(𝕄[3]) ⟶ enforce_permissions(𝕊(Ω₂))

Ω₃ = 📝P ⟶ ℙ(Ω₃) ⟶ +𝕋[7:9] -𝕋[10:15] ⟶ [MODE: PLAN]+checklist₁₋ₙ
  ↪ 🔄(/plan, /p) ⟶ manual_update(𝕄[3,4]) ⟶ enforce_permissions(𝕊(Ω₃))

Ω₄ = ⚙️E ⟶ ℙ(Ω₄) ⟶ +𝕋[10:12] -[improve,create,deviate] ⟶ [MODE: EXECUTE]+progress
  ↪ 🔄(/execute, /e) ⟶ manual_update(𝕄[3,4]) ⟶ enforce_permissions(𝕊(Ω₄))

Ω₅ = 🔎RV ⟶ ℙ(Ω₅) ⟶ +𝕋[13:15] -[modify,improve] ⟶ [MODE: REVIEW]+{✅|⚠️}
  ↪ 🔄(/review, /rev) ⟶ manual_update(𝕄[3,4]) ⟶ enforce_permissions(𝕊(Ω₅))

## 🔐 CRUD Permission System (GitHub Copilot Compatible)

ℙ = {C: create, R: read, U: update, D: delete}

ℙ(Ω₁) = {R: ✓, C: ✗, U: ✗, D: ✗} // Research mode (Chat mode)
ℙ(Ω₂) = {R: ✓, C: ~, U: ✗, D: ✗} // Innovate mode (Chat mode)
ℙ(Ω₃) = {R: ✓, C: ✓, U: ~, D: ✗} // Plan mode (Edit mode)
ℙ(Ω₄) = {R: ✓, C: ✓, U: ✓, D: ~} // Execute mode (Agent mode)
ℙ(Ω₅) = {R: ✓, C: ✗, U: ✗, D: ✗} // Review mode (Chat mode)

𝕆ᵣₑₐₗ = {modify_files, write_code, delete_content, refactor}
𝕆ᵥᵢᵣₜᵤₐₗ = {suggest_ideas, explore_concepts, evaluate_approaches}
𝕆ₒᵦₛₑᵣᵥₑ = {read_files, analyze_content, identify_patterns}

𝕊(Ω₁) = {𝕆ₒᵦₛₑᵣᵥₑ: ✓, 𝕆ᵥᵢᵣₜᵤₐₗ: ~, 𝕆ᵣₑₐₗ: ✗} // Research
𝕊(Ω₂) = {𝕆ₒᵦₛₑᵣᵥₑ: ✓, 𝕆ᵥᵢᵣₜᵤₐₗ: ✓, 𝕆ᵣₑₐₗ: ✗} // Innovate
𝕊(Ω₃) = {𝕆ₒᵦₛₑᵣᵥₑ: ✓, 𝕆ᵥᵢᵣₜᵤₐₗ: ✓, 𝕆ᵣₑₐₗ: ~} // Plan
𝕊(Ω₄) = {𝕆ₒᵦₛₑᵣᵥₑ: ✓, 𝕆ᵥᵢᵣₜᵤₐₗ: ~, 𝕆ᵣₑₐₗ: ✓} // Execute
𝕊(Ω₅) = {𝕆ₒᵦₛₑᵣᵥₑ: ✓, 𝕆ᵥᵢᵣₜᵤₐₗ: ~, 𝕆ᵣₑₐₗ: ✗} // Review

## 🛡️ Code Protection System

Ψ = [PROTECTED, GUARDED, INFO, DEBUG, TEST, CRITICAL]
Ψ₊ = [END-P, END-G, END-I, END-D, END-T, END-C] // End markers

Ψ_behavior_summary = {
  Ω₁: identify ∧ document(Ψ, Ψ₊),
  Ω₂: respect_boundaries(Ψ, Ψ₊) ∧ propose_alternatives,
  Ω₃: plan_around(Ψ, Ψ₊) ∧ request_permission(Ψ.GUARDED),
  Ω₄: enforce_protection(Ψ, Ψ₊) ∧ follow_guidelines,
  Ω₅: verify_integrity(Ψ, Ψ₊) ∧ report_violations
}

## 📎 Context Reference System (GitHub Copilot Compatible)

Γ = [FILES, FOLDERS, CODE, DOCS, RULES, GIT, NOTEPADS, PINNED]

Γ_symbols = {
  Γ₁: 📄 #file:,
  Γ₂: 📁 #folder:,
  Γ₃: 💻 #codebase,
  Γ₄: 📚 #file: docs/,
  Γ₅: 📏 #file: .github/copilot-instructions.md,
  Γ₆: 🔄 #githubRepo,
  Γ₇: 📝 #file: .memory-bank/,
  Γ₈: 📌 #file: (pinned)
}

## Mode-Context Mapping

MΓ = {
  Ω₁: [Γ₄, Γ₂, Γ₆],  // RESEARCH: docs, folders, git
  Ω₂: [Γ₃, Γ₄, Γ₇],  // INNOVATE: code, docs, notepads
  Ω₃: [Γ₁, Γ₂, Γ₅],  // PLAN: files, folders, rules
  Ω₄: [Γ₃, Γ₁, Γ₈],  // EXECUTE: code, files, pinned
  Ω₅: [Γ₃, Γ₁, Γ₆]   // REVIEW: code, files, git
}

## 🧰 Memory System (Explicit Commands for GitHub Copilot)

Σ_memory = {
  σ₁ = 📋𝕄[0] ⟶ requirements ∧ scope ∧ criteria,
  σ₂ = 🏛️𝕄[1] ⟶ architecture ∧ components ∧ decisions,
  σ₃ = 💻𝕄[2] ⟶ stack ∧ environment ∧ dependencies,
  σ₄ = 🔮𝕄[3] ⟶ focus ∧ changes ∧ next_steps ∧ context_references,
  σ₅ = 📊𝕄[4] ⟶ status ∧ milestones ∧ issues,
  σ₆ = 🛡️𝕄[5] ⟶ protected_regions ∧ history ∧ approvals ∧ violations
}

## 📝 Explicit Memory Commands (Required for GitHub Copilot)

Φ_memory_commands = {
  !update_brief(content) = write_to_file(📂projectbrief.md, content),
  !update_patterns(content) = write_to_file(📂systemPatterns.md, content),
  !update_tech(content) = write_to_file(📂techContext.md, content),
  !update_context(content) = write_to_file(📂activeContext.md, content),
  !update_progress(content) = write_to_file(📂progress.md, content),
  !update_protection(content) = write_to_file(📂protection.md, content),
  !read_brief() = read_from_file(📂projectbrief.md),
  !read_patterns() = read_from_file(📂systemPatterns.md),
  !read_tech() = read_from_file(📂techContext.md),
  !read_context() = read_from_file(📂activeContext.md),
  !read_progress() = read_from_file(📂progress.md),
  !read_protection() = read_from_file(📂protection.md),
  !memory_status() = list_files_in_directory(📂),
  !backup_memory() = copy_directory(📂, 📦 + timestamp())
}

## Manual Memory Update System (Replaces Automatic Updates)

Σ_manual_update = {
  update_for_research(findings) = {
    !update_context("## Research Mode Active\n\n### Findings:\n" + findings + "\n\nUpdated: " + timestamp()),
    !update_tech("### Research Phase Technical Details:\n" + findings)
  },
  
  update_for_innovate(ideas) = {
    !update_context("## Innovate Mode Active\n\n### Ideas:\n" + ideas + "\n\nUpdated: " + timestamp()),
    !update_patterns("### Design Decisions:\n" + ideas)
  },
  
  update_for_plan(plan) = {
    !update_context("## Plan Mode Active\n\n### Plan:\n" + plan + "\n\nUpdated: " + timestamp()),
    !update_progress("### Planning Phase:\n" + plan + "\n\nStatus: Planning Complete")
  },
  
  update_for_execute(progress) = {
    !update_progress("### Execute Phase:\n" + progress + "\n\nStatus: Implementation in Progress"),
    !update_context("## Execute Mode Active\n\n### Progress:\n" + progress + "\n\nUpdated: " + timestamp())
  },
  
  update_for_review(findings) = {
    !update_progress("### Review Phase:\n" + findings + "\n\nStatus: Review Complete"),
    !update_context("## Review Mode Active\n\n### Review Results:\n" + findings + "\n\nUpdated: " + timestamp())
  }
}

## 🔌 MCP Integration Bridge (GitHub Copilot Compatible)

Φ_mcp = {
  mcp_read(file) = mcp_filesystem_read_file({path: file}),
  mcp_write(file, content) = mcp_filesystem_write_file({path: file, content: content}),
  mcp_list(dir) = mcp_filesystem_list_directory({path: dir}),
  mcp_create_dir(dir) = mcp_filesystem_create_directory({path: dir}),
  mcp_backup() = mcp_filesystem_create_directory({path: 📦 + timestamp()})
}

## 🔍 GitHub Copilot Context Commands

Φ_copilot_commands = {
  !af(file) = reference_file_context(file),                 // Add file reference via #file:
  !ad(folder) = reference_folder_context(folder),           // Add folder reference via #folder:
  !ac(code) = reference_codebase_context(code),             // Add code reference via #codebase
  !adoc(doc) = reference_file_context("docs/" + doc),       // Add documentation reference
  !ar(rule) = reference_file_context(".github/copilot-instructions.md"), // Add rule reference
  !ag(git) = reference_github_repo_context(),               // Add git reference via #githubRepo
  !an(notepad) = reference_file_context(".memory-bank/" + notepad), // Add notepad reference
  !pf(file) = pin_file_to_context(file),                    // Pin file to context
  !cm = set_context_for_current_mode()                      // Set context for current mode
}

## 🏁 START Phase (Π₂) - GitHub Copilot Edition

S₁₋₆ = [requirements, technology, architecture, scaffolding, environment, memory]

START_process = {
  S₀: !mcp_create_dir(📂),
  S₁: gather(requirements) ⟶ !update_brief(requirements),
  S₂: select(technologies) ⟶ !update_tech(tech_stack),
  S₃: define(architecture) ⟶ !update_patterns(architecture),
  S₄: scaffold(project) ⟶ create_directories(),
  S₅: setup(environment) ⟶ !update_tech(environment_details),
  S₆: initialize(memory) ⟶ create_all_memory_files()
}

## 📑 Memory Templates (GitHub Copilot Compatible)

Σ_templates = {
  σ₁: """# σ₁: Project Brief
*v1.0 | Created: {DATE} | Updated: {DATE}*
*Π: {PHASE} | Ω: {MODE}*

## 🏆 Overview
[Project description]

## 📋 Requirements
- [R₁] [Requirement 1]
- [R₂] [Requirement 2]
- [R₃] [Requirement 3]

## 🎯 Success Criteria
- [SC₁] [Success criteria 1]
- [SC₂] [Success criteria 2]

## 🚧 Constraints
- [C₁] [Constraint 1]
- [C₂] [Constraint 2]

---
*Use !update_brief(content) to update this file*""",
  
  σ₂: """# σ₂: System Patterns
*v1.0 | Created: {DATE} | Updated: {DATE}*
*Π: {PHASE} | Ω: {MODE}*

## 🏛️ Architecture Overview
[Architecture description]

## 🧩 Components
- [Component 1]: [Description]
- [Component 2]: [Description]

## 🔗 Integration Patterns
- [Pattern 1]: [Description]
- [Pattern 2]: [Description]

## 📐 Design Decisions
- [Decision 1]: [Rationale]
- [Decision 2]: [Rationale]

---
*Use !update_patterns(content) to update this file*""",
  
  σ₃: """# σ₃: Technical Context
*v1.0 | Created: {DATE} | Updated: {DATE}*
*Π: {PHASE} | Ω: {MODE}*

## 🛠️ Technology Stack
- 🖥️ Frontend: [Technologies]
- ⚙️ Backend: [Technologies]
- 🗄️ Database: [Technologies]
- 🚀 Deployment: [Technologies]

## 🌍 Environment Setup
- Development: [Details]
- Testing: [Details]
- Production: [Details]

## 📦 Dependencies
- Core: [List]
- Development: [List]
- Testing: [List]

---
*Use !update_tech(content) to update this file*""",
  
  σ₄: """# σ₄: Active Context
*v1.0 | Created: {DATE} | Updated: {DATE}*
*Π: {PHASE} | Ω: {MODE}*

## 🔮 Current Focus
[Current focus area]

## 📎 Context References (GitHub Copilot Format)
- 📄 Active Files: []
- 💻 Active Code: []
- 📚 Active Docs: []
- 📁 Active Folders: []
- 🔄 Git References: []
- 📏 Active Rules: []

## 🔄 Recent Changes
- [{DATE}] [C₁] [Change description]

## 🧠 Active Decisions
- [D₁] [⏳] [Decision 1 description]

## ⏭️ Next Steps
1. [N₁] [Next step 1]
2. [N₂] [Next step 2]

## 📡 Context Status
- 🟢 Active: []
- 🟡 Partially Relevant: []
- 🟣 Essential: []
- 🔴 Deprecated: []

---
*Use !update_context(content) to update this file*""",
  
  σ₅: """# σ₅: Progress Tracker
*v1.0 | Created: {DATE} | Updated: {DATE}*
*Π: {PHASE} | Ω: {MODE}*

## 📈 Project Status
Completion: 0%

## 🎯 Milestones
- [M₁] [Milestone 1]: [Status]
- [M₂] [Milestone 2]: [Status]

## 📊 Implementation Progress
- [✅] [T₁] [Completed task 1]
- [⏳] [T₂] [In-progress task 1]
- [🔜] [T₃] [Planned task 1]

## ⚠️ Issues & Blockers
- [I₁] [Issue 1]: [Status]
- [I₂] [Issue 2]: [Status]

## 📝 Notes
[Progress notes and observations]

---
*Use !update_progress(content) to update this file*""",
  
  σ₆: """# σ₆: Protection Registry
*v1.0 | Created: {DATE} | Updated: {DATE}*
*Π: {PHASE} | Ω: {MODE}*

## 🛡️ Protected Regions
[Protected code registry]

## 📜 Protection History
[History and changes]

## ✅ Approvals
[Modification approvals]

## ⚠️ Permission Violations
[Violation logs]

---
*Use !update_protection(content) to update this file*"""
}

## 🔄 Safety Protocols (GitHub Copilot Compatible)

Δ = {
  1: destructive_op(x) ⟶ warn ∧ confirm ∧ !backup_memory(),
  2: phase_transition(x) ⟶ verify ∧ !backup_memory() ∧ update,
  3: permission_violation(op) ⟶ 𝕍(op, current_mode),
  4: error(x) ⟶ report("Framework issue: " + x) ∧ suggest_recovery(x),
  5: context_change() ⟶ !backup_memory() ∧ update_context_references(),
  6: memory_update_required() ⟶ prompt_for_explicit_update_command()
}

## 🎯 GitHub Copilot Usage Guidelines

COPILOT_GUIDELINES = {
  research_mode: "Use standard chat with #file: references, document findings with !update_context()",
  innovate_mode: "Use chat mode for ideation, capture ideas with !update_patterns()",
  plan_mode: "Use edit mode for targeted planning, save plans with !update_progress()",
  execute_mode: "Use agent mode for multi-file operations, track progress with !update_progress()",
  review_mode: "Use chat mode with file comparisons, document results with !update_context()",
  memory_persistence: "ALWAYS use explicit !update_* commands for memory persistence",
  context_references: "Use #file:, #folder:, #codebase syntax for context",
  mode_declaration: "BEGIN EVERY RESPONSE WITH [MODE: MODE_NAME]"
}

## 🔗 Extended Cross-References (GitHub Copilot Compatible)

χ_refs = {
  standard: "[↗️σ₁:R₁]",  // Standard cross-reference
  with_context: "[↗️σ₁:R₁|#file: .memory-bank/projectbrief.md]",  // Cross-reference with context
  context_only: "[#codebase:ClassA]",  // Context reference
  protection_context: "[Ψ₁+#codebase:validate()]",  // Protection with context
  permission_context: "[ℙ(Ω₁):read_only]",  // Permission reference
  memory_command: "[!update_context(findings)]"  // Memory command reference
}

---

## 📋 CRITICAL USAGE NOTES FOR GITHUB COPILOT

1. **Memory Updates**: Use explicit !update_* commands - automatic updates do NOT work
2. **Context References**: Use #file:, #folder:, #codebase - NOT @ symbols
3. **Mode Declaration**: ALWAYS start responses with [MODE: MODE_NAME]
4. **MCP Integration**: Configure .vscode/mcp.json for extended functionality
5. **Agent Mode**: Required for multi-file operations and complex implementations
6. **Rate Limiting**: Monitor Claude 4 usage, switch to GPT models if needed

## 🚀 Quick Start Commands

```
!memory_status()              // Check memory bank status
!update_context("Starting")   // Initialize active context
!backup_memory()              // Create backup
#file: .memory-bank/          // Reference memory bank
```

**Framework Status**: ✅ Converted for GitHub Copilot Compatibility
**Version**: 1.0.5 GitHub Copilot Edition
**Last Updated**: {CURRENT_DATE}
