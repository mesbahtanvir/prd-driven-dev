# Webapp Development Workflow
## Build a Complete Webapp from Scratch Using These Prompts

This guide sequences the prompts in chronological order to build a production-ready webapp with clean UI, backend, authentication, and well-structured codebase.

---

## Overview

```
Phase 1: Setup        → webapp-fullstack-setup.md
Phase 2: Planning     → prd-driven-development.md
Phase 3: Code Quality → clean-code-refactoring.md
Phase 4: Security     → security-best-practices.md
Phase 5: Testing      → test-driven-development.md
Phase 6: CI/CD        → github-actions-optimization.md
Phase 7: Review       → code-review-best-practices.md
```

---

## Phase 1: Project Setup

**Prompt:** `webapp-fullstack-setup.md`

**Goal:** Initialize the project structure, configure Claude Code, set up Firebase.

**Run this first to create:**
- Next.js frontend with TypeScript
- Python/FastAPI backend
- Firebase configuration (Auth, Firestore)
- CLAUDE.md with project context
- Claude skills for development
- Basic GitHub workflows

**Output:**
```
my-webapp/
├── frontend/          # Next.js app
├── backend/           # Python FastAPI
├── firebase/          # Security rules
├── .github/           # Workflows
├── .claude/           # Skills
└── CLAUDE.md
```

**Command:** "Set up a new webapp with Next.js frontend, Python backend, and Firebase"

---

## Phase 2: Feature Planning

**Prompt:** `prd-driven-development.md`

**Goal:** Create PRDs for core features before coding.

**Create PRDs for:**
1. PRD-001: User Authentication (login/signup)
2. PRD-002: User Dashboard
3. PRD-003: Core Feature 1 (your main feature)

**Output:**
```
docs/prd/
├── PRD-001-user-auth.md
├── PRD-002-dashboard.md
└── PRD-003-[feature].md
```

**Command:** "Create a PRD for user authentication with email and Google login"

---

## Phase 3: Implement with Clean Code

**Prompt:** `clean-code-refactoring.md`

**Goal:** Write clean, maintainable code as you implement features.

**Apply while building:**
- Small, focused functions
- Clear naming conventions
- Proper error handling
- No code duplication

**Key principles:**
- Functions do one thing
- Names reveal intent
- Extract reusable components
- Follow project conventions from CLAUDE.md

**Command:** "Review this component for clean code principles"

---

## Phase 4: Security First

**Prompt:** `security-best-practices.md`

**Goal:** Implement secure authentication and protect against OWASP Top 10.

**Implement:**
- Firebase Authentication setup
- Protected routes (frontend)
- Auth middleware (backend)
- Firestore security rules
- Input validation
- CORS configuration

**Checklist:**
- [ ] Password authentication with Firebase
- [ ] Google OAuth
- [ ] JWT token validation in backend
- [ ] Protected API endpoints
- [ ] Secure session handling
- [ ] XSS prevention
- [ ] CSRF protection

**Command:** "Audit the authentication flow for security vulnerabilities"

---

## Phase 5: Testing

**Prompt:** `test-driven-development.md`

**Goal:** Add comprehensive tests for reliability.

**Write tests for:**
- Frontend components (Jest + React Testing Library)
- Backend API endpoints (pytest)
- Authentication flows
- E2E critical paths (Playwright)

**Coverage targets:**
- Unit tests: 80%+
- Integration tests for API
- E2E for login and core flows

**Command:** "Generate tests for the authentication module"

---

## Phase 6: CI/CD Optimization

**Prompt:** `github-actions-optimization.md`

**Goal:** Optimize build speed and deployment reliability.

**Configure:**
- Dependency caching
- Build caching (Next.js)
- Parallel jobs
- Preview deployments
- Production deployment

**Output optimized workflows:**
- ci.yml (lint, test, build)
- deploy-frontend.yml
- deploy-backend.yml
- preview.yml

**Command:** "Analyze and optimize the GitHub Actions workflows"

---

## Phase 7: Code Review

**Prompt:** `code-review-best-practices.md`

**Goal:** Review code quality before merging.

**Review checklist:**
- PRD acceptance criteria met
- Tests pass and cover new code
- Security considerations
- Performance implications
- Code style consistency

**Command:** "Review this PR for the authentication feature"

---

## Quick Start Sequence

### Day 1: Foundation

```bash
# 1. Create project using webapp-fullstack-setup.md
"Set up a Next.js + Python + Firebase webapp called [name]"

# 2. Initialize PRD system
"Set up PRD-driven development for this project"

# 3. Create first PRD
"Create PRD for user authentication"
```

### Day 2-3: Authentication

```bash
# 4. Implement auth (following clean code)
"Implement user authentication based on PRD-001"

# 5. Security audit
"Audit the authentication for security issues"

# 6. Write tests
"Generate tests for authentication"
```

### Day 4+: Core Features

```bash
# 7. Create PRD for next feature
"Create PRD for [feature]"

# 8. Implement feature
"Implement [feature] based on PRD-002"

# 9. Test and review
"Generate tests and review code for [feature]"
```

### Before Launch

```bash
# 10. Optimize CI/CD
"Analyze and optimize GitHub Actions"

# 11. Final security audit
"Run full security audit"

# 12. Performance check
"Check for performance issues"
```

---

## Recommended Prompt Pairings

| Task | Primary Prompt | Supporting Prompt |
|------|----------------|-------------------|
| New feature | prd-driven-development | clean-code-refactoring |
| Authentication | webapp-fullstack-setup | security-best-practices |
| Bug fix | prd-driven-development | test-driven-development |
| Performance issue | github-actions-optimization | clean-code-refactoring |
| Code review | code-review-best-practices | security-best-practices |
| Refactoring | clean-code-refactoring | test-driven-development |

---

## Minimal Viable Webapp Checklist

### Structure
- [ ] Next.js frontend initialized
- [ ] Python backend initialized
- [ ] Firebase project created
- [ ] CLAUDE.md configured
- [ ] GitHub repo with workflows

### Authentication
- [ ] Email/password signup
- [ ] Email/password login
- [ ] Google OAuth
- [ ] Protected routes
- [ ] Logout functionality

### Backend
- [ ] Health check endpoint
- [ ] Auth middleware
- [ ] User profile endpoint
- [ ] Error handling
- [ ] CORS configured

### Frontend
- [ ] Login page
- [ ] Signup page
- [ ] Dashboard page
- [ ] Navigation
- [ ] Loading states
- [ ] Error handling

### Code Quality
- [ ] Linting configured
- [ ] Type checking passes
- [ ] Tests written
- [ ] PRDs documented
- [ ] CI/CD working

---

## Prompt Reference

| # | Prompt | Purpose |
|---|--------|---------|
| 1 | `webapp-fullstack-setup.md` | Project initialization |
| 2 | `prd-driven-development.md` | Feature planning |
| 3 | `clean-code-refactoring.md` | Code quality |
| 4 | `security-best-practices.md` | Authentication & security |
| 5 | `test-driven-development.md` | Testing |
| 6 | `github-actions-optimization.md` | CI/CD |
| 7 | `code-review-best-practices.md` | Code review |

### Optional Prompts

| Prompt | When to Use |
|--------|-------------|
| `api-design-principles.md` | Designing REST APIs |
| `nextjs-best-practices.md` | Next.js specific patterns |
| `firebase-integration-best-practices.md` | Firebase deep dive |
| `performance-optimization.md` | Performance issues |
| `domain-driven-design.md` | Complex business logic |

---

## Example: Building a SaaS App

### Week 1: Setup & Auth

```
Day 1: webapp-fullstack-setup.md → Project structure
Day 2: prd-driven-development.md → PRD-001 User Auth
Day 3: security-best-practices.md → Implement auth
Day 4: test-driven-development.md → Auth tests
Day 5: github-actions-optimization.md → CI/CD
```

### Week 2: Core Feature

```
Day 1: prd-driven-development.md → PRD-002 Dashboard
Day 2-3: clean-code-refactoring.md → Implement
Day 4: test-driven-development.md → Tests
Day 5: code-review-best-practices.md → Review
```

### Week 3+: Iterate

```
For each feature:
1. PRD → Plan
2. Implement → Clean code
3. Test → Coverage
4. Review → Quality
5. Deploy → CI/CD
```

---

## Begin

Start with Phase 1:

1. Run `webapp-fullstack-setup.md` prompt
2. Say: "Set up a new webapp with Next.js, Python backend, and Firebase for [your app name]"
3. Follow the setup steps
4. Move to Phase 2 when project structure is ready

**The key insight:** Each prompt builds on the previous. Setup first, plan second, build with quality third.
