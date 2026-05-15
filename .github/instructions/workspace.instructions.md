---
name: workspace
description: Workspace conventions, architecture, development practices, and project structure for Socops - a Spring Boot interactive bingo game platform.
applyTo: "**/*.java,**/*.html,**/*.css,pom.xml"
---

# Socops Workspace Instructions

## ✅ Development Checklist (Mandatory)

Before committing code, complete all checks:

- [ ] **Lint**: `./mvnw clean compile` (checks syntax & dependencies)
- [ ] **Build**: `./mvnw clean package` (compiles, packages, ready for deploy)
- [ ] **Test**: `./mvnw test` (all tests pass)

**Verify all three pass before pushing changes.**

---

## 🎯 Project Overview

**Socops** is an interactive Social Bingo game for in-person mixers. Built with Spring Boot 3.4.2, Thymeleaf, and utility-first CSS. Service-driven architecture with composable, testable components.

---

## 📁 Structure

```
socops/src/main/java/com/socops/
├── SocOpsApplication.java          # Spring Boot entry
├── data/IcebreakerPrompts.java     # Game content
├── model/                          # Domain objects (BingoCell, PlayPhase, WinningStreak)
├── service/BoardAssembler.java     # Game logic
└── web/BingoRestController.java    # REST endpoints (/api/*)

socops/src/main/resources/
├── application.properties
├── static/css/app.css              # Utility-first CSS
└── templates/game.html             # Thymeleaf template
```

---

## 🚀 Essential Commands

```bash
./mvnw clean package          # Build project
./mvnw spring-boot:run        # Dev server (http://localhost:8080, hot-reload enabled)
./mvnw test                   # Run tests
./mvnw test -Dtest=BoardAssemblerTests  # Single test class
```

---

## 🏗️ Architecture

**Layered**: Controller → Service → Model → Data

- **Controller** (`BingoRestController`): Maps requests, no logic
- **Service** (`BoardAssembler`): Game logic, board assembly, cell state
- **Models**: `BingoCell`, `PlayPhase`, `WinningStreak` (immutable/records)
- **Data**: `IcebreakerPrompts` (static prompts library)

**API**: All routes use `/api/*` prefix. Current: `GET /api/board`, `GET /api/marked/{id}`

---

## 💻 Conventions & Best Practices

**Java**: PascalCase classes (`BoardAssembler`), camelCase methods (`generateBoard`), UPPER_SNAKE_CASE constants. Package: `com.socops.<layer>`. Keep logic in services, not controllers. Use immutable records for DTOs.

**Frontend**: Use Thymeleaf attributes (`th:each`, `th:if`). Minimize logic in templates. Use utility CSS from `app.css` (see CSS guide for utilities). Semantic HTML.

**Testing**: Place in `src/test/java` mirroring source structure. Use JUnit 5. Service tests should not require Spring context. Run all before committing.

---

## 📝 Common Tasks

**Add Icebreaker Prompts** → Edit `IcebreakerPrompts.java`'s `ALL_PROMPTS` list

**Add REST Endpoint** → Add method to `BingoRestController` with `@GetMapping`, use `BoardAssembler` for logic

**Modify Game Board** → Edit `BoardAssembler.generateBoard()` for logic, `game.html` for UI

**Extend Game Rules** → Update `PlayPhase` enum → Add to `BoardAssembler` → Add endpoint

---

## 🧪 Testing & Building

```bash
./mvnw test                    # Run all tests
./mvnw test -X                 # Verbose output
./mvnw clean package           # Full build with tests
```

Tests: `src/test/java/com/socops/service/BoardAssemblerTests.java`

---

## ⚙️ Configuration

`application.properties`:
- `server.port=8080` (change for different port)
- `spring.devtools.restart.enabled=true` (hot-reload)

---

## 🔗 References

- **Workshop**: `/workshop/` (00-overview through 04-multi-agent)
- **CSS Guide**: `.github/instructions/css-utilities.instructions.md`
- **Frontend Design**: `.github/instructions/frontend-design.instructions.md`
- **Spring Docs**: https://spring.io/projects/spring-boot

---

*Socops v0.0.1 | May 2026*
