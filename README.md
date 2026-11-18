# Intro to Agents and Skills
*KIDS26 workshop · St. Jude Children's Research Hospital*

Hands-on workshop material for Knowledge in Data Science Symposium (KIDS26) Workshop on An Introduction to AI Agents and Skills, presented November 18, 2026 at the KIDS26 conference.

In about 30 minutes we will review basics of LLM safety, how LLMs "work," an LLM Harness talks to an LLM Endpoint via its API.

| Resource | Link |
|---|---|
| St. Jude AI HUB (SJCRH only) | [sites/ai](https://sjcrh.sharepoint.com/sites/ai) |
| (SJCRH only) | [AI Use in the Workplace Wiki](https://wiki.stjude.org/pages/viewpage.action?pageId=281777464) |
| When in doubt, see the AI Use in the Workplace Policy (SJCRH only) | [AI Use in the Workplace Policy](<https://sjcrh.policystat.com/policy/19180248/latest/>) |

## Agenda

1. Quick Review of Tools
2. Agents and Harnesses
3. Installation
4. Sandboxing
5. Skills, examples


## Getting Started
Steps to get started at St. Jude. This is a list of software and setup steps you'll probably want to do first. [link](getting-started/README.md).

## Skills
Today, we'll install one skill that's a part of K-Dense's [Scientific Agent Skills](https://github.com/K-Dense-AI/scientific-agent-skills).

1. First, let's do a prompt without a Skill. Without a Skill, ask your LLM: “Generate a structure for carazolol”

2. Navigate to the K-Dense [rdkit](https://github.com/K-Dense-AI/scientific-agent-skills/tree/main/skills/rdkit) skill and check out what it does. This is a more complicated Skills repository, so we won't download from here; I've saved you a copy for simplicity.
3. I've saved this skill to our repo just to make it easy for you to download without synching the repository. Download rdkit.zip.
4. Navigate to the download folder.
4.You can either drag this into the skills dialog inside Settings in Claude, or unzip and put the folder database-lookup into ~/.claude/skills, ~/.copilot/skills etc.

### More?
Download matplotlib.zip from the skills folder, and manhattan_dummy.csv, with a simulated GWAS dataset of about 20,000 SNPs across chromosomes 1–22. Prompt:  "manhattan_dummy_data.csv contains a GWAS dataset of 500K SNPs across chromosomes 1–22. How should I plot this?"


Example popular skills are here: [link](skills/README.md).



