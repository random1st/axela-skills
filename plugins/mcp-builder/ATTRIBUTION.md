# Attribution

- **Source**: https://github.com/anthropics/skills
- **Commit**: 3b3fad96af16a10759d930941b4520ba0c40edae
- **Path**: skills/mcp-builder
- **Upstream license**: Apache-2.0, © Anthropic, PBC — see LICENSE.txt in this folder (shipped by upstream inside the skill).
- **Changes**: repackaged as a standalone plugin (added `.claude-plugin/plugin.json`, the license copy and
  this file). The skill content itself is byte-identical to upstream at the pinned commit.
- **Security review**: 2026-08-28, before signing. Full read of the skill instructions and every executable;
  automated scan of all files for prompt-injection patterns, hidden unicode and undisclosed network calls.
- **Scanner**: SkillSpector do not install, score 76, static analysis only (no file contents were sent to any model).
  Signed over the refusal. The high findings are a documented CLI flag naming a model, and a credential
  noun appearing in a best-practices reference. Both are prose about how to build MCP servers, not behaviour
  of this skill; the medium findings are unpinned package-runner invocations in example commands, also prose.
  (An earlier draft of this note scored higher than the skill it describes, because quoting a flagged phrase
  is indistinguishable, to a pattern matcher, from using it.)
- **What our signature claims**: this exact content, from this source, passed that review. It does not prove
  the skill is right for your threat model, and it cannot vouch for anything the skill fetches at runtime.
