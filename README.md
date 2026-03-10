# Factory Custom Droids

Personal [Factory](https://factory.ai) droid collection for Spring Boot development workflows.

## Quick Install

**macOS / Linux:**
```bash
mkdir -p ~/.factory/droids && cd ~/.factory/droids && \
git init && git remote add origin https://github.com/mptapasdas/factory-droids.git && \
git fetch origin && git checkout -f origin/main -- . && \
echo "Droids installed to ~/.factory/droids/"
```

**Windows (PowerShell):**
```powershell
New-Item -ItemType Directory -Force -Path "$HOME\.factory\droids" | Out-Null
Set-Location "$HOME\.factory\droids"
git init; git remote add origin https://github.com/mptapasdas/factory-droids.git
git fetch origin; git checkout -f origin/main -- .
Write-Host "Droids installed to $HOME\.factory\droids\"
```

This works whether the directory is empty or already has files -- existing droids with the same name are overwritten, and any other files are left untouched. To update later, run `git fetch origin && git checkout -f origin/main -- .` from inside `~/.factory/droids`.

## Droids

### Spring Boot Pipeline

These droids form a sequential pipeline for feature development:

| Order | Droid | Purpose |
|-------|-------|---------|
| 1 | **springboot-architect** | Designs entities, endpoints, DTOs, migrations, security config. Outputs a JSON spec. |
| 2 | **springboot-codegen** | Generates source code from the architect's JSON spec. |
| 3 | **springboot-tester** | Writes and runs unit + integration tests (JUnit 5, Mockito, WebMvcTest, DataJpaTest). |
| 4 | **springboot-reviewer** | Read-only code review for security, performance, correctness, and best practices. |
| 5 | **docs-updater** | Updates Postman collection and RELEASE.md after reviewer approves. |

### General Purpose

| Droid | Purpose |
|-------|---------|
| **worker** | Bounded research, exploration, impact analysis, dependency investigation. |

### Mission-Specific

| Droid | Purpose |
|-------|---------|
| **scrutiny-feature-reviewer** | Code review for a single feature during mission validation. |
| **user-testing-flow-validator** | Tests validation contract assertions through real user surface. |
