# Super-Agent — Project Instructions

## Hardware & Execution Constraints
- **Environment:** CPU-only, 16GB RAM, 32K context ceiling.
- **Zero-Overhead Parsing:** NEVER run commands that dump massive output (compiled files, node_modules, database dumps).
- **Chunk-and-Flush:** Do NOT attempt multi-file features in a single execution loop. Break work into atomic micro-tasks.
- **File Targeting:** Open, read, or edit a maximum of **3 files** per task execution.
- **Context Flushing:** At the end of every micro-task, output: *"MEMORY LIMIT REACHED. Task [Task_Name] complete. FLUSH CONTEXT NOW. Run `/execute` to resume the ledger."*

## Design & Aesthetics
- **Context-Driven Design:** Do NOT use a hardcoded palette or style. Derive all design decisions (color palette, typography, layout paradigm, density, animations) from the project's domain, target audience, and purpose as defined in `.claude/memory/master_blueprint.md`.
- **The Architect Decides:** During the `/architect` phase, analyze the project concept and define a complete design system (palette, typography, spacing, component style) in the blueprint. All subsequent tasks must follow that system.
- **Component Structure:** Strict centralization and reusability of UI components. Design tokens (colors, fonts, spacing) must be defined in a single source of truth (e.g., CSS variables, theme file, or design tokens file).
- **Asset Generation:** All generated assets must be raw images on a solid white background — no stylized mockups.

## Code Standards
- **Anti-Slop:** Production-ready, heavily typed, modular code. No monolithic files.
- **State Management:** Enforce centralized state management for mobile/frontend.
- **API Routing:** Strict controller → service → route separation for backends.

## Execution Mode — CRITICAL
- **ALWAYS write real files.** When building features, creating components, or writing any code — use file write tools to create/edit actual files on disk. NEVER just print code blocks in chat and ask the user to copy them.
- **ALWAYS run real commands.** Use bash to run `npm init`, `npm install`, `mkdir`, `git`, dev servers, etc. directly. Do not suggest commands for the user to run manually.
- **You are an autonomous builder.** You have full permissions (`Bash(*)`, `Write(*)`, `Read(*)`) granted in `.claude/settings.json`. Use them. Create directories, scaffold projects, install dependencies, write source files, and run builds — all directly.
- **No "here's what you should do" responses.** Every task must result in actual files written to disk and commands executed. If a task says "create a React component", the component file must exist on disk when you're done.

## Memory System
Before starting any task, read these files for context:
- `.claude/memory/master_blueprint.md` — Project architecture and tech spec.
- `.claude/memory/active_ledger.md` — Current task queue and phase tracking.
- `.claude/memory/context_buffer.md` — Rolling memory across context flushes.

After completing any task, update `active_ledger.md` (check off completed tasks) and `context_buffer.md` (2-sentence summary of what was done).
