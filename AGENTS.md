# AGENTS.md

Guidance for AI coding agents working in the organisation repository `domain-centric-development/.github`:
the organisation profile (`profile/README.md`), the organisation-wide `CONTRIBUTING.md`, `AI-DISCLOSURE.md` and
`LICENSE`. GitHub shows these defaults on every repository of the organisation that has no file of its own.

## Principles every repository follows

1. **The samples exist to make the AI harness deterministic, not to ship features.** The reference shops are the
   experiment field for the harness — knowledge catalog, architecture rules, markers, plugins. An architectural
   change in a sample is finished when it has answered: does the catalog need a node? could a rule check it (same
   id in `dca-java` and `dca-dotnet`)? would one more generic marker make it checkable? "None" is an answer, recorded.
2. **Rules, markers and the catalog are general.** They are the foundation other production systems — any
   industry — build on with AI. Nothing in them exists only because the shop needs it: no shop vocabulary, no
   selection that only fits the sample, no catalog node that presupposes a cart.
3. **The core libraries are framework-neutral.** `dca-building-blocks` / `DomainCentric.BuildingBlocks` have zero
   dependencies; `dca-archunit` / `DomainCentric.ArchRules` know frameworks only as configurable presets.
   Framework-specific code lives in satellite artifacts (`dca-spring`, `dca-archunit-spring-modulith`).
4. **Each reader artifact stands alone.** Guide, book and catalog bundle are independently readable; links never
   cross repository boundaries.

## Working here

- `profile/README.md` is the organisation's landing page. Repository names, package coordinates and the rule count
  it states must match the published state — check `dca-java/rules.json` (Java) and `dca-dotnet/rules.json` (.NET)
  in the monorepo checkout before changing a number; today it says 114 Java rules in 10 sets.
- `CONTRIBUTING.md` carries the licensing terms (inbound = outbound MIT, plus the copyright holder's right to
  relicense prose) and the principles above. Changes to the terms are the owner's decision, not an editorial fix.
- `AI-DISCLOSURE.md` is the honest account of how the project is built; extend it when the way of working changes,
  never soften it.
- Community health files still missing here, by the owner's decision so far: `SECURITY.md`, `CODE_OF_CONDUCT.md`.
  Adding them here makes them the default for all repositories.
- This checkout lives in the monorepo as `dca-org-github/`; the remote is `domain-centric-development/.github`.
