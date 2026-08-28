# axela-skills

Curated agent skills you can verify, not just trust.

Every plugin here is **byte-identical to a pinned commit** of a well-known open-source
skill repository, keeps its **upstream license and attribution**, and went through a
**security review before signing** — a full read of the instructions and every
executable, plus an automated scan for prompt-injection patterns, hidden unicode and
undisclosed network calls. The catalog is signed by the publisher and countersigned by
the [Axela](https://axela.app) notary; a machine that pins both keys at threshold 2
refuses the catalog if either signature is missing — and learns within a day when
a skill is revoked.

## Install (verified)

```sh
curl -sO https://notary.axela.app/notary.pub
skillctl subscribe https://github.com/random1st/axela-skills \
  --catalog https://notary.axela.app/v1/catalogs/random1st/axela-skills \
  --key catalog.pub --key notary.pub
skillctl sync
```

Or just add it as a plain Claude Code marketplace — the skills work without
verification; you simply give up tamper detection and revocation:

```
/plugin marketplace add random1st/axela-skills
```

## What is in the batch

| Skill | From | License |
|---|---|---|
| test-driven-development, systematic-debugging, verification-before-completion, writing-plans, requesting-code-review | [obra/superpowers](https://github.com/obra/superpowers) | MIT |
| code-review-and-quality, git-workflow-and-versioning, security-and-hardening, debugging-and-error-recovery | [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills) | MIT |
| mcp-builder, webapp-testing | [anthropics/skills](https://github.com/anthropics/skills) | Apache-2.0 |

Each plugin's `ATTRIBUTION.md` names the exact source commit, license and what our
signature does and does not claim. Skills whose upstream license does not permit
redistribution (or that ship no license at all) are excluded, whatever their stars.

## What the signature honestly means

The signature proves **who published these bytes and that they have not changed** —
and our review adds "we read them first". It does not prove a skill is safe for your
threat model, and it cannot vouch for content a skill fetches at runtime. Detection,
not enforcement.

Curation and packaging © the axela-skills maintainers, MIT (see LICENSE).
Each plugin remains under its upstream license.
