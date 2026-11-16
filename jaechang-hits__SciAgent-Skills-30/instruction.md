# Issue

**Title:** feat: sciagent-skill-creator scaffold

## Description

## Summary
Repo-local Claude Code skill that scaffolds a new SciAgent-Skills entry without hand-editing `registry.yaml` or copying templates by hand. Mechanizes the boilerplate from `CLAUDE.md` Steps 1, 2, 4, 5, 6 so authoring effort stays on content.

### Layout
```
.claude/skills/sciagent-skill-creator/
├── SKILL.md                       # invocation + workflow + TRIGGER patterns
└── scripts/
    ├── scaffold.py                # non-interactive scaffolder
    └── validate_description.py    # description linter (standalone CLI + importable)
```

### scaffold.py behavior
- Validates: sub-type, category, name (kebab-case + uniqueness against `registry.yaml` AND `legacy/`), description (length + first-120-char keyword lead + no promotional adjectives), tags (kebab-case)
- Renders `skills/{category}/{name}/SKILL.md` from the matching template (pipeline/toolkit/database → toolkit-style; guide → prose) with frontmatter substituted
- Appends a `registry.yaml` entry with today's date and optional tags
- Runs `pixi run validate` post-write; reverts the partial scaffold (directory + registry append) if validation fails

### validate_description.py
Standalone CLI and importable. Enforces 1024-char ceiling; blocks stop-verb leads (`Use`, `A`, `An`, `The`, `Query`, `Fetch`, `Run`); flags promotional adjectives (`powerful`, `comprehensive`, `state-of-the-art`, ...).

---

## Changes since first push

Three follow-up commits respond to issues found while dogfooding the scaffolder:

1. **`a6983ce` fix(scaffold): tolerate leading HTML comment in templates** — PR #29 added an HTML comment block before the YAML frontmatter fence in all three `SKILL_TEMPLATE_*.md` files. The scaffolder's frontmatter slicer assumed the file starts with `---` and produced a malformed SKILL.md. Fix: locate the opening fence with `text.index(\"---\")` instead of byte 0.

2. **`cf4908b` Merge** — merge `origin/main` to pick up #24 / #25 / #26 / #27 / #28 / #29 so this PR validates against the current registry, CLAUDE.md, and template state.

3. **`07b1ea6` fix(skill-creator): strengthen trigger so agent uses scaffolder** — observed failure: in a fresh session, asking the agent to add a new SciAgent skill caused it to pattern-match on \"add\" and go straight to manual file/registry editing, bypassing this skill entirely. Two soft signals were the cause:
   - `CLAUDE.md` Step 0 pointer was phrased as a \"shortcut\" that \"automates Steps 1, 2, 4, 5, 6\" — advisory, not mandatory.
   - `SKILL.md` frontmatter description had no explicit TRIGGER patterns.

   Now:
   - `CLAUDE.md`: blockquote replaced with a \"STOP — invoke the scaffolder first\" block that lists trigger phrases (EN + KR), states the agent MUST invoke the skill before touching `skills/` or `registry.yaml`, names the failure mode (drift), and carves out the two legitimate skip cases (editing existing entry, migrating existing entry).
   - `SKILL.md`: frontmatter description rewritten as a multi-line YAML block with explicit `TRIGGER` / `DO NOT TRIGGER` sections, mirroring the convention used by high-recall skills like `ecc:prompt-optimizer` and `claude-api`.

---

## How to use

### Path 1 — through Claude Code (recommended)
The skill is discovered automatically. Open a session in this repo and tell the agent what you want to add:

```
> Add a new SciAgent skill for the bedtools-genomic-intervals toolkit.
> 스킬 만들어줘 — DESeq2 differential expression.
```

The agent will:
1. Load `.claude/skills/sciagent-skill-creator/SKILL.md` automatically (TRIGGER patterns now catch a wider range of phrasings)
2. Ask any missing fields (sub-type, category, name, license, optional tags)
3. Run a duplicate check (`grep -i <topic> registry.yaml legacy/`)
4. Invoke `scripts/scaffold.py` with explicit args
5. Hand back a skeleton `skills/{cat}/{name}/SKILL.md` for the agent to fill with Overview, Workflow, Recipes, References

### Path 2 — direct CLI (manual)
For scripted or batch use, call the scaffolder yourself:

```bash
python .claude/skills/sciagent-skill-creator/scripts/scaffold.py \
  --sub-type pipeline \
  --category genomics-bioinformatics \
  --name pydeseq2-differential-expression \
  --description \"PyDESeq2 differential expression for bulk RNA-seq. Wraps DESeq2's negative-binomial model in Python; pandas in, results DataFrame out. For single-cell DE use scanpy.tl.rank_genes_groups.\" \
  --license MIT
```

With optional cross-cutting `tags`:

```bash
python .claude/skills/sciagent-skill-creator/scripts/scaffold.py \
  --sub-type database \
  --category scientific-writing \
  --name openalex-database \
  --description \"OpenAlex literature database REST API. Search papers, authors, venues...\" \
  --license MIT \
  --tags databases,literature
```

### Path 3 — description linter only
Test a description string before scaffolding:

```bash
python .claude/skills/sciagent-skill-creator/scripts/validate_description.py \
  \"PyDESeq2 differential expression for bulk RNA-seq. ...\"
# OK

python .claude/skills/sciagent-skill-creator/scripts/validate_description.py \
  \"Use this comprehensive ML toolkit for analysis.\"
# FAIL: first word 'use' is a stop verb. ...
# FAIL: promotional word 'comprehensive' adds no discovery signal — remove it
```

### After scaffolding
The script outputs a skeleton — content is still your job. Next steps it prints:

1. Fill in `Overview`, `When to Use`, `Workflow` / `Core API`, `Recipes`, `References` in the generated `SKILL.md`
2. Run `pixi run test` — full suite, not just `validate` — to catch sub-type-specific structural failures (code block counts, table row counts, section presence)

### Failure paths (each surfaces a clear error, no partial state written)
- Nonexistent category → fails before write
- Bad-case name (`BadName`, `123-tool`, `-leading-hyphen`) → fails before write
- Name already in `registry.yaml` → fails before write
- Name already in `legacy/` → fails before write
- Description starts with stop verb → fails before write, prints which word
- Description contains promotional adjective → fails before write, prints which word
- `pixi run validate` rejects the new entry → directory and registry append both reverted automatically

---

## Not in registry.yaml
This skill ships agent tooling, not domain knowledge. It lives under `.claude/skills/` and is picked up by Claude Code automatically — no entry needed.

## Test plan
- [x] \`pixi run test\` passes (4051 tests on the merged branch)
- [x] smoke tests during development: bad category / bad name / colliding name / happy path with tags — all confirmed
- [x] template parsing fix verified by re-running scaffold against current templates
- [ ] reviewer runs \`python .claude/skills/sciagent-skill-creator/scripts/scaffold.py --help\` to confirm flag surface
- [ ] reviewer tries a happy-path scaffold and confirms revert behavior on intentional validate failure
- [x] reviewer asks a fresh agent session \"add a SciAgent skill for <tool>\" and confirms the scaffolder triggers (this was the gap fixed in \`07b1ea6\`)

## Task

Modify the repository so that the issue described above is resolved. The repository is checked out at base commit `bba33b3ef988`. Edit files in place; the verifier captures your changes via `git diff` and scores them against an oracle patch using SWE-RL-style diff-similarity reward.