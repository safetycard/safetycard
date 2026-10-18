# Scorecard changelog

SafetyCard has one version, shared by the skill (`SKILL.md`), its plugin manifests, `SCORECARD_VERSION` in `score.py` and the website's `criteria.json`; every release bumps it in all of them. Each entry's `scorecard_version` records the version it was scored under and never changes afterwards. When a change can move ratings, rerun every existing scorecard under the new version (the new entry carries the new version) and log rating changes in each `reaudit_log`.

## 0.9
First public release. All entries scored before 0.9.2 are labelled 0.9: until then the scorecard kept the two-part version while the skill moved to 0.9.1.

- **Safest setup (output only, 2026-10-10, skill 0.9.1).** Every review now carries a `safe_setup` section, rendered as "Safest setup" after the headline: how to run the agent most safely, written from the review's own findings (SKILL.md step 6). It changes no criterion, level, cap, weight or score, so `scorecard_version` stays 0.9 and published entries were backfilled without rescoring.
- **Scanner-friendly wording (2026-10-18, skill 0.9.2).** Reworded phrases in `criteria.md`, `search-patterns.md` and the worked example that static skill scanners read as instructions to the agent, and made `score.py` re-run only plain `rg` searches scoped inside the target repo. No criterion, level, cap, weight or score changes. From this release the scorecard and the skill share one version, so new entries are labelled 0.9.2; existing entries keep 0.9, the version they were scored under.
