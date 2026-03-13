# Copilot Instructions for Repository

## Language Policy

All code, comments and instructions in this repository must be written in English. 

## Tech Stack

- .NET 10+ class libraries, Blazor Server, WPF, console apps, MSTest
- Single Visual Studio Solution (`.sln`, `.slnx`) under src/

## Always Enforce

- Branch from main for /delegate tasks
- Never commit directly to main
- Run `dotnet format`, `dotnet test` before commits
- Use flat structures over lambdas. Execution order is explicit
- Use file-scoped namespaces in C#
- MSTest projects: `[TestClass]`, `[TestMethod]`, AAA pattern
- PRs must pass CI (lint + tests)
