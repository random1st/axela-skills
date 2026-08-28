# Attribution

- **Source**: https://github.com/addyosmani/agent-skills
- **Commit**: f63ec56a3cc936408d792956ae583c3c96a825bd
- **Path**: skills/security-and-hardening
- **Upstream license**: MIT, © Addy Osmani — see LICENSE in this folder (copied verbatim from the source repository).
- **Changes**: repackaged as a standalone plugin (added `.claude-plugin/plugin.json`, the license copy and
  this file). The skill content itself is byte-identical to upstream at the pinned commit.
- **Note**: the text may point to checklist files under `../../references/` in the source repository; those are not part of this plugin.
- **Security review**: 2026-08-28, before signing. Full read of the skill instructions and every executable;
  automated scan of all files for prompt-injection patterns, hidden unicode and undisclosed network calls.
- **Scanner**: SkillSpector do not install, score 76, static analysis only (no file contents were sent to any model).
  Signed over the refusal. This skill teaches defence, so it necessarily contains the strings an attacker
  would use: the cloud metadata address it tells you to block, the dot-env filenames it tells you to exclude
  from git, and a substring spanning a table cell in its STRIDE section. Every high finding is teaching material.
- **What our signature claims**: this exact content, from this source, passed that review. It does not prove
  the skill is right for your threat model, and it cannot vouch for anything the skill fetches at runtime.
