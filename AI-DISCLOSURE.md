# How this was built

This project was written with AI assistance, and the disclosure belongs in the open.

The code, the guide and the rule catalog were drafted mainly by **Claude**, with parts reviewed by
**OpenAI Codex**, in an iterative dialogue with the author — **Christoph Bloemer**
([@chbloemer](https://github.com/chbloemer)) — that has been running **since 2025**. The author
set the direction, made the architectural decisions, reviewed the design and spot-checked the code. None of it is a one-shot generation.

**How the reviewing changed.** In the beginning every change was read line by line. As the rule
catalog grew, that reading moved into the build: what used to be a manual check became a failing
test, which freed the author's attention for design — and for experiments that would have been too
expensive to verify by hand. The catalog is therefore not decoration; it is the reason the
collaboration scales.

**What is checked mechanically.** The architecture rule catalog runs in the build of both
reference implementations (ArchUnit on the Java side, ArchUnitNET on the .NET side), alongside unit,
integration and end-to-end tests. The two implementations serve the same routes and carry two
mirrored end-user suites over one shared, written scenario contract: each build checks its own shop
against every scenario, and fails when a scenario has no test or a test no scenario. Comparing the
two runs against each other is not automated yet. Architectural decisions are recorded as ADRs,
including the ones that were later superseded.

**What that does not mean.** A green build is not proof of correctness, and a rule catalog does not
replace judgement. It narrows the space in which a mistake can hide — a smaller claim, and the one
actually being made here.

**Scope of the samples.** The reference implementations keep their infrastructure deliberately
simple — in-memory storage, a mock payment provider — so the architecture stays visible. Each such
shortcut is named in the sample's ADRs.

**Licence.** Everything in this organisation is published under the MIT licence, which includes its
disclaimer of warranty. See the `LICENSE` file in each repository.
