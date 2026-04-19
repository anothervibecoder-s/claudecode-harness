# Claude Code Engineering Harness 🦾

Stop chatting with AI. Start engineering with it.

This repository provides the blueprint for the **"Project Harness"** I use to run Claude Code (Opus 4.7) for 8+ hours a day on high-stakes SaaS projects without hitting quotas or losing model accuracy.

🚀 Key Features
- **Context Discipline:** Drastically cuts token usage by keeping the main session lean.
- **Hub & Spoke Model:** Uses Sonnet/Haiku subagents for "dirty work" (grep, research, unit tests).
- **Multi-Model Consensus:** Automated triggers for parallel reviews by Gemini Pro + Flash + Sonnet.
- **Persistent Memory:** A structured hierarchy for session continuity and decision tracking.
- **Strict Guardrails:** Hard limits on lines-per-fix and mandatory verification steps.

## 🛠️ How to use
1. Copy the `CLAUDE_EXAMPLE.md` file to your project root.
2. Replace all `[Placeholders]` with your specific tech stack, ownership matrix, and verification commands.
3. Configure your `.claude/settings.json` to include the `Stop` hooks for auto-retros.
4. (Optional) Install `claude-flow` and `graphify` to augment the harness.
   
## 📈 Results
- **Zero Quota Hits:** Even on 5x Max plan with heavy tool use.
- **Zero Hallucinated Success:** Mandatory verification blocks "fake" fixes.
- **Senior-Level Autonomy:** The model stops asking repetitive questions and follows your architectural standards.
  
*Inspired by the viral discussion on r/ClaudeAI, r/claude, and r/vibecoding.*
