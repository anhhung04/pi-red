# pi-red

Offensive security skill library for [omp](https://omp.sh) — 79 drop-in red-team `SKILL.md`
playbooks across 23 categories. Each skill primes the agent with methodology, tooling, edge
cases and escalation paths for one attack surface, loaded on demand.

Ported from [`SnailSploit/claude-red`](https://github.com/SnailSploit/claude-red) (MIT) —
upstream packaged these as a 23-entry omp *marketplace*; this repo flattens them into a single
omp **plugin package** with one `skills/` tree, which is the simpler shape for one author's
library.

## Install

From [personal-toolkit](https://github.com/anhhung04/personal-toolkit):

```sh
omp plugin marketplace add git@github.com:anhhung04/personal-toolkit.git
omp plugin install pi-red@personal-toolkit
```

Directly from git:

```sh
omp plugin install github:anhhung04/pi-red
```

## Categories

active-directory · ai · api · auth · cicd · cloud · container · crypto · exploit-dev ·
forensics · fuzzing · infrastructure · iot · mobile · network · post-exploitation · privesc ·
recon · social-engineering · supply-chain · utility · web · wireless

## What changed vs upstream

- `plugins/<category>/skills/<skill>/SKILL.md` → flat `skills/<skill>/SKILL.md`
- the 23-entry `.omp-plugin/marketplace.json` is gone; a single `package.json` with
  `omp.skills: ["./skills"]` replaces it
- 28 skills had no YAML frontmatter (only `# SKILL:` / `## Description` markdown). omp's loader
  **silently skips** any `SKILL.md` without a `description`, so those were dead files upstream;
  each now carries generated `name` + `description` frontmatter
- `## Instructions for Claude` → `## Instructions for the Agent`
- `offensive-osint` renamed to `offensive-osint-checklist` so it does not collide with the
  `offensive-osint` skill in [`pi-osint`](https://github.com/anhhung04/pi-osint)

## Intended use

Authorized red team engagements, bug bounty triage, security research, CTF preparation,
operator training, and methodical attack-surface exploration. See [SECURITY.md](SECURITY.md).

## License

MIT — see [LICENSE](LICENSE).
