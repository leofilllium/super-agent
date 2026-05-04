# HARDWARE & EXECUTION LIMITATIONS
**Environment:** The host machine is an Ubuntu CPU-only system with 16GB of total RAM. The LLM operating this framework has a hard ceiling of 32,000 tokens for context.
**Absolute Directives:**
1. **Zero-Overhead Parsing:** NEVER run commands that output massive logs (e.g., `cat` on compiled files, massive node_modules, or massive database dumps).
2. **The "Chunk-and-Flush" Mandate:** You are forbidden from attempting to complete a multi-file feature in a single execution loop. 
3. **File Targeting:** You may only open, read, or edit a maximum of THREE (3) files per task execution.
4. **Context Flushing:** At the end of every micro-task, you MUST output: *"MEMORY LIMIT REACHED. Task [Task_Name] complete. FLUSH CONTEXT NOW. Run `/claude execute` to resume the ledger."* Do not proceed until the user flushes the chat.
