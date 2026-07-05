# write-post

A Claude Code skill that transforms your AI-powered work into **case study posts**, optimized for **scoring rubrics**.

- **Basic mode**: Automatically generate AI case study posts from DEVLOG
- **goksung mode**: Generate case study posts optimized for 100-point rubric scoring

---

## 🎯 Features

### Basic Mode (`/write-post`)
- Automatic DEVLOG generation (supports 5 AI tools)
- Case study writing for non-technical audience
- Low-friction one-question-at-a-time interview
- Copy-paste ready reusable prompts included

### goksung Mode (`/write-post goksung`)
- **100-point Rubric Optimization**:
  - Problem Definition (20 points)
  - Solution Process (20 points)
  - Output Completeness (25 points)
  - Business Applicability (25 points)
  - Case Shareability (10 points)

- **3 New Interview Questions**:
  1. Quantified Severity ("Express in numbers?")
  2. Alternative Solutions Review ("Why didn't existing methods work?")
  3. **AI Output Verification** ("How did you verify the AI results?") ⭐ Key

- **9-Item Self-Diagnostic Checklist**:
  - Proof-of-work (screenshots/links/logs)
  - Quantified before/after metrics
  - Reusable prompts ≥2
  - Cross-domain application scenario
  - Episode structure (request→work→result→learning)
  - No source code exposure
  - Existing alternative review documented
  - Sensitive data masked ✓
  - Honest limitation statements

- **Anti-Fabrication 3-Step Rule**:
  - Never fabricate items without evidence
  - Extract only from actual user responses
  - Mark missing items as "N/A" honestly

---

## 📦 Installation

### Mac / Linux

```bash
# Global installation (use in all projects)
curl -fsSL https://raw.githubusercontent.com/tearess/write-post/main/install_mac.sh | bash

# Or local project installation
curl -fsSL https://raw.githubusercontent.com/tearess/write-post/main/install_mac.sh | bash
```

### Windows (PowerShell)

```powershell
iwr -useb https://raw.githubusercontent.com/tearess/write-post/main/install_win.ps1 | iex
```

### Manual Installation

Copy `.claude/skills/write-post/SKILL.md` from this repo to your project's `.claude/skills/write-post/`:

```bash
# In your project folder:
mkdir -p .claude/skills/write-post
cp <write-post-repo>/.claude/skills/write-post/SKILL.md .claude/skills/write-post/
```

**Restart your Claude Code tool** after installation for the skill to be recognized.

---

## 🚀 Usage

### Basic Mode (Original write-post)

```bash
/write-post
```

**Process**:
1. **Phase 1**: Generate DEVLOG (parse session files)
2. **Phase 2**: Review and edit DEVLOG
3. **Phase 3**: Write case study (one question at a time)

**Output**: `AI_CASE_STUDY.md`

### goksung Mode (Rubric-Optimized)

```bash
/write-post goksung
```

**Trigger**: Include literal **"goksung"** in your request (case-insensitive)
- ✅ `/write-post goksung`
- ✅ `run write-post goksung mode`
- ❌ `/write-post` (basic mode)
- ❌ `/write-post scoring` ("scoring" alone won't trigger)

**Process**:
1. Phases 1~2: Same as basic mode
2. Phase 3: **goksung follow-up questions added**
   - Quantified severity, alternative solutions, AI verification, tool choice rationale, cross-domain scenarios, etc.
3. Phase 5: **Self-diagnostic checklist** (9 items)
   - Missing items questioned once, then marked "N/A" if not available
   - No fabrication allowed

**Output**: `AI_CASE_STUDY.md` (rubric-optimized)

**Optional**: Include scoring checklist (on request)
- Add rubric category → section mapping table at end of document

---

## 📋 100-Point Rubric Structure

### 1️⃣ Problem Definition (20 points) — 12 sub-criteria

| Item | Description |
|------|-------------|
| Concreteness | Specific job/tool/repetitive task named |
| Quantified Severity | Time/cost/frequency metrics included |
| Origin Authenticity | Specific event/timing/emotion described |
| Urgency | Loss accumulation if postponed stated |
| Scope | Personal/team/organizational impact range |
| Reader Relatability | Target audience and problem fit |
| Problem-Solution Logic | Before pain ↔ Solution function 1:1 mapping |
| Vividness | Concrete scene/emotion descriptions |
| **Existing Alternative Review** ⭐ | **Why existing methods fell short** (goksung new) |
| Recurrence | Frequency signals (daily/weekly/per-project) |
| Measurability | Before/after metric unit alignment |
| Target Reader Clarity | Persona-level specificity |

### 2️⃣ Solution Process (20 points) — 11 sub-criteria

| Item | Description |
|------|-------------|
| Approach Logic | Problem→Method causal connection |
| **Method/Tool Choice Rationale** ⭐ | **Why this vs other methods/tools** (goksung new) |
| Trial-Error Concreteness | Specific failure + cause + improvement |
| Decision Rationale | Judgment criteria shown |
| Active AI Collaboration | User intervention/judgment/correction scenes |
| Iteration Cycle | First→discovery→second improvement loop |
| Elegance vs Difficulty | Technical difficulty vs solution conciseness |
| Reproducibility | Original request code blocks ≥2 |
| Failure Cause Honesty | AI misunderstanding vs user request insufficiency |
| Human-AI Role Division | Clear person/AI contribution boundaries |
| Episode Causality | Request→action→result→learning 4-step |

### 3️⃣ Output Completeness (25 points, HARD) — 10 sub-criteria

| Item | Description |
|------|-------------|
| **Proof-of-Work** | Screenshots/links/logs ≥1 |
| **Quantified Before/After** | Metric pairs (3 hours→10 minutes, etc.) |
| End-to-End Completeness | Entry→core action→result flow complete |
| Exception Handling | Error/edge-case handling mentioned |
| Visual Evidence Quality | Captions/context with proper placement |
| Objective Verifiability | Third-party verification path provided |
| **Reusable Prompts** | Copy-paste ready prompts ≥2 |
| Durable Reusability | Repeatable form, not one-off |
| **Honest Scope** | Completion/incomplete boundary clear + "N/A" marking ⭐ |
| Result-Goal Alignment | Opening goal = After metric mapping |

### 4️⃣ Business Applicability (25 points, HARD) — 11 sub-criteria

| Item | Description |
|------|-------------|
| **Cross-Domain Transferability** | Concrete application to different job/domain (gate) |
| **Reusable Deliverables** | Copy-paste possible artifacts ≥2 (gate) |
| Parameterization | `[variable]` marked for immediate customization |
| Immediate Actionability | "What→which tool→which order" clarity |
| Non-Developer Barrier | Achievable with conversational AI + copy-paste |
| ROI Generalization | Stated with repeatable reason |
| Application Breadth | Character-different domains ≥2 (bonus) |
| Scalability | Team/organization size adaptation points |
| Prerequisite Clarity | Required tools/data/permissions/costs stated |
| Scenario Authenticity | Evidence-backed transplant vs fabrication (gate) |
| Limitation Awareness | Unsuitable situations/human intervention points |

### 5️⃣ Case Shareability (10 points) — 12 sub-criteria

| Item | Description |
|------|-------------|
| Title Hook Power | Specific audience + impact/surprise |
| Introduction Hook | First 3~4 sentences trigger empathy/curiosity |
| Skimmability | "Read this only if busy" 3~5 line summary |
| Target Audience Clarity | Role/situation/pain level specificity |
| Sentence Readability | Non-developer friendly language |
| Terminology Explanation | First appearance jargon/acronyms defined |
| Emotional Engagement | Honest struggle/failure/emotion expression |
| Community Response Trigger | Actionable takeaway/surprise/discussion prompt |
| Visual Scannability | Emoji headings/tables/bullet structure |
| Voice Consistency | One person's voice throughout |
| Summary-Body Coherence | Title/summary promises = body delivery |
| Appropriate Length | One-sitting completable pace |

---

## 📁 File Structure

```
.
├── README.md                                    # Korean guide
├── README.en.md                                 # English guide
├── .claude/
│   └── skills/
│       └── write-post/
│           └── SKILL.md                         # Skill definition (661 lines)
├── .omc/
│   ├── plans/
│   │   ├── goksung-write-post-option.md        # Approved consensus plan
│   │   └── goksung-rubric-detailed-checklist.md # 76 sub-criteria items
│   └── drafts/
│       ├── rubric-detail-problem-definition.md
│       ├── rubric-detail-solution-process.md
│       ├── rubric-detail-output-completeness.md
│       ├── rubric-detail-applicability.md
│       └── rubric-detail-shareability.md
```

---

## 🛠️ Supported AI Tools

| Tool | DEVLOG Parsing |
|------|----------------|
| **Claude Code** | `~/.claude/projects/` .jsonl |
| **OpenCode** | MCP session tool or `~/.local/share/opencode/` |
| **Codex CLI** | `~/.codex/sessions/YYYY/MM/DD/` |
| **Gemini CLI** | `~/.gemini/tmp/<hash>/chats/` |
| **Antigravity** | Internal search or `~/.gemini/antigravity/` |

Project-level **automatic collection of all tool sessions** for unified DEVLOG generation.

---

## 📝 goksung Mode Detailed Guide

### Step 1: Trigger Confirmation

Literal **"goksung"** required in request:
```bash
# ✅ Works
/write-post goksung
/write-post with goksung mode
write-post skill goksung option

# ❌ Won't work
/write-post
/write-post scoring
/write-post rubric
```

### Step 2: New Interview Questions

Original 8 questions + **goksung 3 new**:

| Section | New Question | Purpose |
|---------|-------------|---------|
| Problem Situation | "Express in numbers?" / "Existing alternatives?" | Strengthen problem def |
| Work Highlight | "Why choose this method/tool?" | Strengthen solution proc |
| Result Impact | "How did you verify AI results?" ⭐ | Core output completeness |

Each question: "one sentence, skip if not applicable" — maintains low friction.

### Step 3: Self-Diagnostic Checklist (9 items)

Auto-runs **after Phase 5** draft creation:

```
[ ] 1. Quantified before/after metrics present
[ ] 2. Proof (screenshots/links/logs) exists
[ ] 3. Reusable prompts ≥2
[ ] 4. Cross-domain scenario present
[ ] 5. Episodes ≥2 with original code blocks
[ ] 6. No source code exposure
[ ] 7. Existing alternative review documented
[ ] 8. Sensitive info (company/API key) masked
[ ] 9. Incompleteness/limitations stated honestly
```

**Missing Item Handling**:
1. Check DEVLOG + user response for real evidence
2. No evidence? Ask **once more**
3. Still nothing? Mark as **"N/A"** — never fabricate

### Step 4: Scoring Checklist (Optional)

On request, add **rubric mapping table** at document end:

```markdown
## 📎 Scoring Checklist (For submission — delete before sharing)

| Rubric Category | Related Section | Sub-Items |
|---|---|---|
| Problem Def (20) | 📝 Summary + 😫 Situation | [12 items] |
| Solution (20) | 🔧 Process | [11 items] |
| ...
```

---

## 💡 Usage Tips

### When to Use goksung Mode

✅ **Use it for**:
- Internal AI adoption evaluation (rubric-based scoring required)
- Bootcamp assignment submission (rubric-scored)
- Community awards application (rubric criteria clarity)
- Self-validation of post completeness

❌ **Skip it for**:
- Casual blog posts (basic mode recommended)
- Internal team sharing (basic mode recommended)

### Anti-Fabrication Principle

**Rule**: No evidence = "N/A"

```markdown
❌ Bad example:
"3 colleagues tested it and all said they're satisfied"
— Actually never asked them

✅ Good example:
"Third-party Testing: N/A"
— Mark honestly
```

### Sensitive Data Masking

Gate [8] **must verify**:

```markdown
❌ Must NOT expose:
- Company name (real name)
- API keys/secrets
- Personal data (name/email/phone)
- Internal URLs (intranet addresses)
- Confidential information

✅ Masking examples:
- "XYZ Company's marketing team"
- "REDACTED_API_KEY"
- "Internal portal (internal access only)"
```

---

## 🔧 Requirements

- **Claude Code** 1.0.0+ (or other supported AI tool)
- **Node.js** 16+ (for DEVLOG parsing)
- **Git** (for commit parsing in basic mode)

---

## 📚 Additional Resources

- **Plan Document**: `.omc/plans/goksung-write-post-option.md` — Consensus planning process
- **Detailed Analysis**: `.omc/plans/goksung-rubric-detailed-checklist.md` — 76 items explained
- **Team Work**: `.omc/drafts/` — 5 expert specialist analyses

---

## 📄 License

MIT

---

## 🤝 Contributing

Issues/feedback/improvement suggestions welcome on GitHub Issues!

- **Bug Report**: Describe issue + reproduction steps
- **Feature Request**: Use case + expected behavior
- **Question**: Ask about goksung mode usage

---

**write-post goksung** — Write honest, high-quality AI case studies with confidence.
