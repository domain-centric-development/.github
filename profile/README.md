# Domain-Centric Architecture

Business logic in the middle, infrastructure at the edges. DCA synthesises **Domain-Driven Design**,
**Hexagonal Architecture** and **Clean Architecture** into four layers whose dependencies all point
inward — domain, application, adapter, infrastructure — with bounded contexts as the unit of scaling.

What makes it a *style* rather than an opinion: the rules are executable. A catalog of **110 rules in
10 sets** (ids `DCA-<SET>-<NNN>`) runs in your build and fails it when a layer, a port or a naming
convention slips.

## Where to start

| I want to… | Repository |
|---|---|
| understand the architecture | [**dca-guide**](https://github.com/domain-centric-development/dca-guide) |
| read a shop that is built this way — Java | [**dca-ecommerce-sample-java**](https://github.com/domain-centric-development/dca-ecommerce-sample-java) |
| …the same shop in .NET | [**dca-ecommerce-sample-dotnet**](https://github.com/domain-centric-development/dca-ecommerce-sample-dotnet) |
| enforce the rules in my own Java build | [**dca-java**](https://github.com/domain-centric-development/dca-java) |
| …in my own .NET build | [**dca-dotnet**](https://github.com/domain-centric-development/dca-dotnet) |

## The repositories

| Repository | What it is |
|---|---|
| [dca-guide](https://github.com/domain-centric-development/dca-guide) | The compact guide: patterns, layer rules, package templates, ArchUnit governance, Spring Modulith, deployment. The reference for *how* the style is applied. |
| [dca-java](https://github.com/domain-centric-development/dca-java) | Two published libraries: `dca-building-blocks` (DDD and hexagonal marker interfaces) and `dca-archunit` (the rule catalog, on ArchUnit + JUnit 5). On Maven Central as `dev.domaincentric:*`. |
| [dca-dotnet](https://github.com/domain-centric-development/dca-dotnet) | The .NET twin: `DomainCentric.BuildingBlocks` and `DomainCentric.ArchRules(.Xunit)` on ArchUnitNET — **the same rule ids**, so a finding means the same thing in both languages. |
| [dca-ecommerce-sample-java](https://github.com/domain-centric-development/dca-ecommerce-sample-java) | The reference implementation: a Spring Boot shop with eight bounded contexts, full tactical DDD, ports and adapters, and the rule catalog running in its build. |
| [dca-ecommerce-sample-dotnet](https://github.com/domain-centric-development/dca-ecommerce-sample-dotnet) | The same shop on ASP.NET Core, one project per bounded context. |

## Two implementations, one architecture

The two samples are not two projects that happen to look alike. They serve the **same markup, the same
routes and the same seed data**, and either Playwright suite runs against either shop — so a checkout
that diverges breaks four end-to-end runs, not one. The rule catalog is shared: 110 rules on both
sides, four of which cannot apply to .NET, plus six that only exist there (`DCA-NET-*`).

That is the point of the pair: it separates what is *architecture* from what is merely *Java* or
merely *.NET*. When the two disagree, one of them is wrong — and it shows.

## What the style asks of you

- **The domain has no framework.** No annotations from your web stack, your ORM or your container.
- **Dependencies point inward.** Interfaces live where they are used; implementations live in adapters.
- **A bounded context is a boundary, not a folder.** Cross-context traffic goes through a published
  API or an event — never through a foreign domain type.
- **Every use case is one folder**: input port, command or query, result, implementation.
- **Progressive complexity.** Start with four layers; add structure when a directory earns it.

## Website

[**domaincentric.dev**](https://domaincentric.dev)
