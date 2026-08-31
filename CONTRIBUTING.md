# Contributing

Thank you for considering a contribution. This file applies to every repository in this organisation
that does not carry one of its own.

## Licensing of contributions

By submitting a contribution — code, documentation, examples, issue text meant to become content —
you agree that:

- it is licensed under the **MIT licence**, the same terms as the repository it goes into
  (*inbound = outbound*), and
- the copyright holder may additionally publish it under **other licences**, for example a
  documentation licence such as CC BY 4.0 for prose.

The second point keeps the door open for text to be dual-licensed later without having to track down
every contributor. You keep the copyright in your contribution; nothing is assigned.

## What makes a contribution easy to accept

- **One concern per pull request.** Architecture changes touch several artifacts at once; a focused
  change is reviewable, a bundle of them is not.
- **The rules stay green.** Both reference implementations run the DCA rule catalog in their build
  (`./gradlew test-architecture`, `dotnet test tests/DcaShop.ArchitectureTests`). A rule that fails is
  either a finding in the change or a finding in the rule — say which you think it is.
- **Consistency across artifacts.** The guide, the two samples and the rule catalog describe the same
  architecture. If a change makes one of them disagree with the others, name the others in the pull
  request; each repository's `AGENTS.md` lists what has to follow.
- **Decisions get recorded.** A non-obvious choice belongs in an ADR, not only in the commit message.

## Reporting a problem

Open an issue in the repository the problem is in. For a mismatch *between* repositories — the guide
says one thing, a sample does another — open it where you think the wrong side is, and say what the
other side does.
