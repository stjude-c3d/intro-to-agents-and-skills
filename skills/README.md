# Skills

## What's a skill?
Minimally, a SKILL.md file: Contains a YAML front matter block (name and description) and markdown instructions detailing step-by-step procedures.

<img width="518" height="152" alt="image" src="https://github.com/user-attachments/assets/b3296837-3f1a-4cde-a8f2-cde65866dcf8" />

Agents load skills through _progressive disclosure_, in three stages:
1. Metadata: At startup, agents load only the name and description of each available skill, just enough to know when it might be relevant.
2. Instruction: When a task matches a skill’s description, the agent reads the full SKILL.md instructions into context.
3. Execution: The agent follows the instructions, optionally executing bundled code or loading referenced files as needed.

Your SKILL.md should be SHORT and only contain four core things:
1. YAML Frontmatter: A name (max 64 chars) and a brief description (max 1,024 chars).
2. Activation Rules: Clear "When to use" triggers.
3. Execution Sequence: A numbered, step-by-step workflow.
4. Output Spec: The specific final shape of the result.

More powerful skills can include scripts (executable code), templates, documentation, and other resources. If a step needs an extensive template or deep domain rules, tell the agent to open a separate file in /references or /assets during that specific step.

*Blueprint Example of a Lean SKILL.md*
```
markdown---
name: pull-request-reviewer
description: Reviews local git diffs for security vulnerabilities before pushing.
---

## Activation Triggers
- When the user asks to review changes before a commit.
- Automatically right before running `git push`.

## Process Steps
1. Execute `git diff` on the staged changes.
2. Read the security checklist found in `./references/security-checklist.md`.
3. Compare the diff against the checklist items.
4. If a violation is found, halt and report it using the template in `./assets/report-template.md`.

## Output Specification
Return a markdown summary listing the file name, line number, severity level, and a suggested fix.
```

## Harness Installations
Most LLMs follow the same installation hierarchy, and are installed into a hidden folder in root. To see hidden folders in MacOS in Finder us the key comp: _control-shift-period_.
```~/userid/.claude```
```~/userid/.codex```
```~/userid/.copilot```
```~/userid/.cursor```

Global skills go in a subfolder called "skills" inside the tool's install folder: ```~/userid/.copilot/skills```

Or, you can put /skills inside a particular a repository to limit its use to just that repository. See [How Copilot uses Skills](https://code.visualstudio.com/docs/agent-customization/agent-skills#_how-copilot-uses-skills) for details on how this is applied in GitHub Copilot, or the same for [Claude](https://code.claude.com/docs/en/skills).

## A List of Useful Skills

### General
1. Tell your coding harness to make you a skill after you make a Python script!
2. [Prompt Master](https://github.com/nidhinjs/prompt-master) A Claude skill that writes the accurate prompts for any AI tool.
3. [Matt Pocock skills](https://github.com/mattpocock/skills) including “grill me” for SWE.
4. [CRIT Framework](https://www.reddit.com/r/PromptEngineering/comments/1lmp9cb/whats_the_most_underrated_tip_youve_learned_about/) prompting strategy from Geoff Woods, author of The AI-Driven Leader.
5. [Caveman](https://github.com/JuliusBrussee/caveman). Why use many token when few token do trick. See also: [ponytail](https://github.com/dietrichgebert/ponytail).


### Scientific
1. [K-Dense-AI/scientific-agent-skills](https://github.com/K-Dense-AI/scientific-agent-skills) Database: PubMed, Semantic Scholar, Gen Office Docs, Research, Polars, Seaborn, Matplotlib, scikit, DepMap, BioPython, Writing, etc.
2. NVIDIA NIMS running on St. Jude's PCAI inference server. There are multiple tools for protein structure generation and drug discovery. [link](https://github.com/stjude/ris-pcai-protein-nim-skills). 
3. [CNS:](https://github.com/faridrashidi/cnsplots) Python plotting for Cell Nature and Science, optimized for Illustrator
4. [SciClaw](https://github.com/drpedapati/sciclaw ): a paired-scientist agent for rigorous research work. 


