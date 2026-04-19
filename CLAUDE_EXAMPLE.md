# [Project Name] — Claude Code Master Context (Sanitized Harness)

This is a comprehensive, production-grade context file designed to orchestrate complex AI Agent workflows for high-stakes SaaS applications. It acts as the "Brain" for Claude Code.

## 1. Platform & Mission
- **Domain:** [Industry] SaaS providing [Key Value Proposition] (e.g., Real-time Financial Insights / ML-driven Analytics).
- **Tech Stack:** 
    - **Frontend:** [Framework] (e.g., Next.js 15) + [Language] (TypeScript) + [UI Lib] (Tailwind/shadcn).
    - **Backend:** [Framework] (e.g., FastAPI/Python) for [Logic Type] (ML/Data Processing).
    - **Database:** [Provider] (e.g., Supabase/PostgreSQL) with [Feature] (RLS/Realtime).
    - **Payments:** [Provider] (e.g., Stripe) — Webhook-driven status sync only.
- **Goal:** [Primary Objective] (e.g., Deliver high-precision insights via self-optimizing data processing pipelines).

## 2. Team & Ownership Matrix (Zero-Overlap Rules)
To prevent code collisions and maintain responsibility, the following matrix is strictly enforced:

| Zone | Primary Owner | Mandatory Workflow |
|------|---------------|-------------------|
| `frontend/**` | [Role A] | `npx tsc --noEmit` check required after every change. |
| `backend/**` | [Role B] | Dry-run validation via `[script-name]` before any commit. |
| `infra/**` | [Role C] | systemd unit source-of-truth must live in `[repo-path]`. |
| `db/migrations` | [Role B] | Migration SQL reviewed by [Role A] before applying. |

## 3. The "Harness" — Execution Hard-Limits
These boundaries prevent "agent-drift" and keep the codebase maintainable.
- **Bug Fixes:** ≤ 50 lines changed per session. One fix = One commit.
- **New Features:** ≤ 300 lines per session. 
- **File Hygiene:** Max 500 lines per file. If exceeded, extract logic to `[utils/components]`.
- **Validation:** Never claim a task is "done" without running `[verify-command]` and showing output.
- **Verification:** For high-stakes logic (Auth/Payments), use the **"Multi-Model Consensus"** trigger.

## 4. Local-First Deployment Strategy
The production server has no git repository. We deploy via sanitized [Method] (e.g., rsync/tar-over-ssh).
- **Mandatory Pattern:** Edit Local → Validate (Lint/Types) → Commit → `[deploy-script]` → SSH only for status checks.
- **SSH Discipline:** Never edit files on the server directly. SSH is for `systemctl status` and `journalctl` only.
- **Anti-Collision Rule:** Announce deployments in [Communication Channel] before execution. Concurrent deploys are FORBIDDEN.

## 5. Data & Machine Learning Discipline (If Applicable)
Rules for maintaining consistent, reproducible models or data pipelines.
- **Hyperparameter Optimization / Studies:** When using tuning frameworks (e.g., Optuna, MLflow, W&B), never run in-memory studies. Always configure a persistent storage backend (e.g., `sqlite:///[path]`) to prevent data loss.
- **Long-Running Jobs:** Run training/data jobs with appropriate unbuffered flags (e.g., `PYTHONUNBUFFERED=1`) and auto-backup log files before every restart.
- **Dry-Runs:** Always run a [Time/Iteration-limited] trial locally before deploying heavy training scripts to the production server.
- **Feedback Loops:** All [Outcome/Prediction Data] tables are strictly append-only. Never delete raw historical signals.

## 6. Environment & Security Hygiene
- **Secret Masking:** Claude is allowed to read `.env` files for context but MUST mask values in output using `sed` or equivalent: `sed -E 's/=.{10,}/=<redacted>/g'`.
- **No-Commit Rule:** Never `git add` any `.env`, `*.json` secrets, or local data directories.
- **Boundary Checks:** Never modify `middleware.ts`, Auth configuration, or payment handlers without explicit Human-in-the-Loop verification.

## 7. Intelligent Subagent Orchestration (Hub & Spoke)
Optimize token usage and maintain focus by delegating specialized tasks.
- **The Hub (Opus):** Manages project strategy, memory consolidation, and architectural decisions.
- **The Spokes (Sonnet/Haiku Subagents):** 
    - **Grep-Agent:** "Search the codebase for X and return a 5-bullet summary"
    - **Test-Agent:** "Write unit tests for the functions in [file-path]."
    - **Doc-Agent:** "Use context7/MCP to find the latest documentation for [library] version [X]."
- **Consensus Panel:** Triggered by `[User Phrase]`. Spawns Gemini Pro + Flash + Sonnet in parallel to review a plan/diff.

## 8. Memory, Continuity & Retros
- **Memory Persistence:** Fact-storage at `[path/to/memory]`. Files prefixed with `user_`, `feedback_`, `project_`.
- **Index:** `MEMORY.md` tracks all stored knowledge to prevent redundant re-briefing.
- **Retro Habit:** Automatic generation of `docs/retros/YYYY-MM-DD-[topic].md` after any non-trivial session.
- **Continuity:** The start of every session must load the latest retro to resume momentum.

## 9. Database & Timezone Rules
- **Timezone Integrity:** [Entity.Field] always stores [Region/Timezone] local time. 
- **Formatting:** Use `[helper-function]` for ISO conversion. Never append `Z` (UTC) to raw database timestamps.
- **Data Integrity:** [Crucial Table] is append-only. Feedback loops use [Outcome-Mapping] to self-improve model accuracy.

---
*Note: This is a sanitized, architectural blueprint. To use this as a live CLAUDE.md, replace all [Placeholders] with your specific project metadata.*
