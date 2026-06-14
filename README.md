# Fable 5 Lite for Claude Opus

**A clean, lightweight distillation of the famous Fable 5 system prompt**, specifically optimized for **Claude Opus 4.8** (claude.ai, Anthropic API, and Claude Code).

### Why this Lite version?

- Only **~3,000 tokens** instead of 9k–10k+ from the original Fable 5 prompt.
- Retains the signature **tone, agentic behavior, and high-quality coding** of Fable 5.
- Removed all unnecessary bloat while keeping the best parts.
- Works great in both standard Claude and Claude Code environments.

### Key Features

- Warm, direct, and mentor-style tone
- Strong software engineering practices (immutability, small functions/files, TDD, etc.)
- Excellent step-by-step reasoning and agentic planning
- Strict copyright, web search, and citation rules
- Optimized for serious coding and real-world projects

### How to Use

#### 1. Claude Code (Recommended for power users)
1. Place the file as **`CLAUDE.md`** in the root of your project folder.
2. Start a new conversation in Claude Code — it will automatically detect and load `CLAUDE.md`.
3. For best results, also add it to your workspace root if you're using multiple projects.

#### 2. Claude Projects (claude.ai)
1. Create or open a Project.
2. Upload `fable5-lite-system-prompt.md` as **`CLAUDE.md`** in the project root.
3. Claude will load it automatically in every chat within that project.

#### 3. Anthropic API
```python
with open("CLAUDE-OPUS-LITE.md", "r") as f:
    system_prompt = f.read()

response = client.messages.create(
    model="claude-opus-4.8",
    max_tokens=8192,
    system=system_prompt,
    messages=[...]
)
