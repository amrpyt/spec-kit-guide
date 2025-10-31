# Spec-Kit Quick Start Guide

> **Get started with GitHub Spec-Kit in minutes. Visual workflows, practical examples, and ready-to-use commands.**

---

## 🚀 5-Minute Quick Start

### Installation
```bash
# 1. Install uv
curl -LsSf https://astral.sh/uv/install.sh | sh

# 2. Install Spec-Kit (from official repository)
uv tool install specify-cli --from git+https://github.com/github/spec-kit.git

# 3. Initialize project
cd your-project
specify init --here

# Or initialize with specific AI agent
specify init --here --ai claude
specify init --here --ai cursor-agent
specify init --here --ai windsurf
```

### Your First Feature
```bash
# Set principles (once per project)
/speckit.constitution

# Build your feature
/speckit.specify "Add user authentication"
/speckit.plan
/speckit.tasks
/speckit.implement
```

**That's it!** Your feature is built with tests, documentation, and following best practices.

---

## 📊 Visual Workflow Overview

### Complete Development Flow

```mermaid
graph TB
    START([Start Feature]) --> CONST{Constitution<br/>Exists?}
    
    CONST -->|No| STEP1["/speckit.constitution<br/>Set Principles"]
    CONST -->|Yes| STEP2["/speckit.specify<br/>Describe Feature"]
    STEP1 --> STEP2
    
    STEP2 --> CLARIFY{Need<br/>Clarification?}
    CLARIFY -->|Yes| STEP3["/speckit.clarify<br/>Q&A Session"]
    CLARIFY -->|No| STEP4["/speckit.plan<br/>Create Plan"]
    STEP3 --> STEP4
    
    STEP4 --> ANALYZE{Want to<br/>Validate?}
    ANALYZE -->|Yes| STEP5["/speckit.analyze<br/>Quality Check"]
    ANALYZE -->|No| STEP6["/speckit.tasks<br/>Task Breakdown"]
    STEP5 --> ISSUES{Critical<br/>Issues?}
    ISSUES -->|Yes| STEP4
    ISSUES -->|No| STEP6
    
    STEP6 --> STEP7["/speckit.implement<br/>Build & Test"]
    STEP7 --> DONE([Feature Complete])
    
    style START fill:#4caf50
    style DONE fill:#4caf50
    style STEP1 fill:#2196f3
    style STEP2 fill:#ff9800
    style STEP3 fill:#9c27b0
    style STEP4 fill:#f44336
    style STEP5 fill:#00bcd4
    style STEP6 fill:#8bc34a
    style STEP7 fill:#e91e63
```

### Command Dependencies

```mermaid
graph LR
    A[constitution] --> B[specify]
    B --> C[clarify*]
    C --> D[plan]
    D --> E[analyze*]
    E --> F[tasks]
    F --> G[implement]
    
    style A fill:#4caf50
    style B fill:#2196f3
    style C fill:#9c27b0
    style D fill:#ff9800
    style E fill:#00bcd4
    style F fill:#8bc34a
    style G fill:#f44336
```
*Optional steps

---

## 🎯 Core Commands

### 1. `/speckit.constitution` - Set Project Rules

**When**: Once per project  
**What**: Define your development principles

```
User: /speckit.constitution

AI: What are your key principles?
User: I want modular design, comprehensive testing, 
     and simple, maintainable code.

AI: [Creates constitution with your principles]
```

### 2. `/speckit.specify` - Describe What to Build

**When**: Starting any new feature  
**What**: Write detailed requirements

```
User: /speckit.specify "Add user authentication with email"

AI: I'll help you specify this feature:
1. What authentication method? (JWT, sessions?)
2. Password requirements?
3. Email verification needed?

User: JWT auth, 8+ char passwords, email verification required

AI: [Creates complete specification]
```

### 3. `/speckit.plan` - Create Technical Plan

**When**: After specification is complete  
**What**: Design the implementation

```
User: /speckit.plan

AI: What's your tech stack?
User: Node.js, Express, PostgreSQL, JWT

AI: [Creates architecture plan, API contracts, 
     database schema, testing strategy]
```

### 4. `/speckit.tasks` - Break Down Work

**When**: After planning is complete  
**What**: Create actionable task list

```
User: /speckit.tasks

AI: Generated 8 tasks:
1. [PARALLEL] Setup database schema
2. [PARALLEL] Create user model  
3. [DEPENDS: 1,2] Implement auth endpoints
4. [DEPENDS: 3] Add email verification
...
```

### 5. `/speckit.implement` - Build It

**When**: Tasks are ready  
**What**: Write code with TDD

```
User: /speckit.implement

AI: Executing tasks:
[1/8] Setup database schema
✅ Write tests (fail) → Implement schema → Tests pass → Commit

[2/8] Create user model
✅ Write tests (fail) → Implement model → Tests pass → Commit

...
[8/8] Complete ✅
```

---

## 🏗️ Brownfield Projects: Easy Integration

### Adding Spec-Kit to Existing Projects

```mermaid
graph TB
    EXISTING([Existing Project]) --> INIT["specify init --here"]
    INIT --> DOCUMENT["Document Current Patterns"]
    DOCUMENT --> CONSTITUTION["Set Integration Constitution"]
    CONSTITUTION --> PARALLEL["New Features with Spec-Kit"]
    PARALLEL --> GRADUAL["Gradual Modernization"]
    GRADUAL --> FULL["Full Integration"]
    
    style EXISTING fill:#ff9800
    style FULL fill:#4caf50
```

### Quick Integration Steps

```bash
# 1. Initialize without touching existing code
cd your-existing-project
specify init --here

# 2. Document what you have
/speckit.constitution
# "Document current patterns, preserve existing APIs,
#  integrate gradually with new patterns"

# 3. Build NEW features with Spec-Kit
/speckit.specify "New feature using modern patterns"
# "Follow new patterns but integrate with existing systems"

# 4. Gradually modernize existing code
/speckit.specify "Modernize auth module"
# "Maintain backward compatibility, provide migration path"
```

### Brownfield Checklist Usage

**Use `/speckit.checklist` when:**

- 🔄 **Before Integration**: Ensure compatibility with existing systems
- 🔧 **During Modernization**: Verify legacy behavior is preserved  
- 🚀 **Before Deployment**: Confirm rollback procedures are ready

```bash
/speckit.checklist
# Generates integration-specific checklist:
# ✅ Are existing API contracts maintained?
# ✅ Is backward compatibility ensured?
# ✅ Are migration scripts tested?
# ✅ Is performance impact assessed?
```

---

## ✅ When to Use Checklists

### Decision Tree

```mermaid
graph TD
    START([Need Quality Check?]) --> FEATURE{Feature Type}
    
    FEATURE -->|Complex Feature| COMPLEX["Use /speckit.checklist<br/>After specification"]
    FEATURE -->|Integration| INTEGRATION["Use /speckit.checklist<br/>Before planning"]
    FEATURE -->|Brownfield| BROWNFIELD["Use /speckit.checklist<br/>At each phase"]
    FEATURE -->|Simple| SKIP["Optional: Skip for simple features"]
    
    COMPLEX --> VALIDATE["Validate completeness"]
    INTEGRATION --> COMPATIBLE["Check compatibility"]
    BROWNFIELD --> SAFE["Ensure safe integration"]
    
    style START fill:#2196f3
    style COMPLEX fill:#ff9800
    style INTEGRATION fill:#9c27b0
    style BROWNFIELD fill:#f44336
    style SKIP fill:#8bc34a
```

### Checklist Examples

#### For Complex Features
```bash
/speckit.checklist
# Generated checklist:
# - [ ] Are all user roles defined?
# - [ ] Are success criteria measurable?
# - [ ] Are error scenarios documented?
# - [ ] Are performance requirements specified?
# - [ ] Are security requirements addressed?
```

#### For Integration Projects
```bash
/speckit.checklist
# Generated checklist:
# - [ ] Are existing API contracts maintained?
# - [ ] Is backward compatibility ensured?
# - [ ] Are data migrations validated?
# - [ ] Are rollback procedures tested?
```

---

## 🔄 Error Recovery: What to Do When Things Break

### Error Type Detection

```mermaid
graph TD
    ERROR([Error Occurred]) --> TYPE{What Type?}
    
    TYPE -->|Tests Failing| TESTS["Spec vs Code Mismatch"]
    TYPE -->|Build Errors| BUILD["Missing Dependencies"]
    TYPE -->|Runtime Errors| RUNTIME["Logic Issues"]
    TYPE -->|Doesn't Work as Expected| REQUIREMENTS["Unclear Requirements"]
    
    TESTS --> ANALYZE["/speckit.analyze"]
    BUILD --> PLAN["/speckit.plan"]
    RUNTIME --> FIX["Fix Code Directly"]
    REQUIREMENTS --> SPECIFY["/speckit.specify"]
    
    ANALYZE --> FIX_ROOT["Fix Root Cause"]
    PLAN --> UPDATE_PLAN["Update Dependencies"]
    FIX_ROOT --> REIMPLEMENT["/speckit.implement"]
    
    style ERROR fill:#f44336
    style TESTS fill:#ff9800
    style BUILD fill:#ff9800
    style RUNTIME fill:#ff9800
    style REQUIREMENTS fill:#ff9800
```

### Quick Recovery Commands

```bash
# Tests failing?
/speckit.analyze
# Review findings → Fix spec or plan → /speckit.implement

# Build errors?  
/speckit.plan
# Add missing dependencies → /speckit.tasks → /speckit.implement

# Requirements unclear?
/speckit.clarify
# Answer questions → /speckit.specify → /speckit.plan

# Constitutional violations?
/speckit.analyze
# Fix violations → /speckit.plan → /speckit.implement
```

---

## 📁 Project Structure

### What Gets Created

```mermaid
graph TB
    ROOT[Project Root] --> SPECIFY[".specify/"]
    ROOT --> MEMORY["memory/"]
    ROOT --> AGENT[".claude/ or .cursor/"]
    ROOT --> SPECS["specs/"]
    
    SPECIFY --> TEMPLATES["templates/"]
    SPECIFY --> SCRIPTS["scripts/"]
    
    MEMORY --> CONSTITUTION["constitution.md"]
    
    AGENT --> COMMANDS["commands/"]
    
    SPECS --> FEATURE["001-feature/"]
    FEATURE --> SPEC["spec.md"]
    FEATURE --> PLAN["plan.md"]
    FEATURE --> TASKS["tasks.md"]
    
    style ROOT fill:#4caf50
    style SPECIFY fill:#2196f3
    style MEMORY fill:#ff9800
    style SPECS fill:#9c27b0
```

### Key Files

| File | Purpose |
|------|---------|
| `memory/constitution.md` | Your project principles |
| `specs/NNN-feature/spec.md` | Feature requirements |
| `specs/NNN-feature/plan.md` | Technical design |
| `specs/NNN-feature/tasks.md` | Implementation steps |
| `.specify/templates/` | Customizable templates |

---

## 🎯 Common Scenarios

### Scenario 1: New Web Application

```bash
# 1. Start fresh
mkdir my-web-app
cd my-web-app
specify init --here

# 2. Set web app principles
/speckit.constitution
# "RESTful API, React frontend, PostgreSQL, 
#  comprehensive testing, JWT authentication"

# 3. Build first feature
/speckit.specify "User registration and login"
/speckit.plan
/speckit.tasks
/speckit.implement
```

### Scenario 2: Adding Feature to Existing Project

```bash
# 1. Go to existing project
cd existing-project

# 2. Initialize Spec-Kit (safe - won't change existing code)
specify init --here

# 3. Document current patterns
/speckit.constitution
# "Current: Express.js, MongoDB, existing auth system.
#  New: Follow existing patterns, maintain compatibility."

# 4. Add new feature
/speckit.specify "Add user notifications"
# "Integrate with existing user system, use current database"
```

### Scenario 3: Microservices Project

```bash
# 1. Set microservices constitution
/speckit.constitution
# "Service-first design, API communication, Docker deployment,
#  independent databases, service discovery"

# 2. Specify first service
/speckit.specify "User service with authentication"
# "Standalone service, REST API, PostgreSQL database"

# 3. Plan service architecture
/speckit.plan
# "Docker container, Express.js, separate database,
#  JWT tokens, health check endpoints"
```

---

## ⚡ Pro Tips

### DO ✅
- Run `/speckit.constitution` once at project start
- Be detailed in `/speckit.specify` - more detail = better results
- Always run `/speckit.plan` before implementing
- Use `/speckit.analyze` to catch issues early
- Review generated files before proceeding

### DON'T ❌  
- Skip the constitution - it prevents technical debt
- Rush through specification - be thorough
- Ignore analysis warnings - they prevent future problems
- Edit generated task files manually
- Override constitutional principles without good reason

### Best Practices

```bash
# Before any implementation
/speckit.analyze  # Always validate first

# During implementation  
/speckit.checklist  # Use checklists for quality

# After errors occur
/speckit.analyze  # Find root cause, don't just patch symptoms
```

---

## 🔧 Quick Reference

### Command Cheat Sheet

| Command | Purpose | When to Use |
|---------|---------|-------------|
| `/speckit.constitution` | Set project principles | Project start |
| `/speckit.specify` | Write feature specification | New feature |
| `/speckit.clarify` | Resolve ambiguities | Unclear requirements |
| `/speckit.checklist` | Generate quality checklist | Complex features |
| `/speckit.plan` | Create technical plan | After spec |
| `/speckit.analyze` | Validate artifacts | Before implementation |
| `/speckit.tasks` | Generate task list | After planning |
| `/speckit.implement` | Build the feature | Ready to code |

### Available AI Agents

```bash
# Initialize with your preferred AI agent:
specify init --here --ai claude          # Claude Code
specify init --here --ai cursor-agent   # Cursor Agent
specify init --here --ai windsurf        # Windsurf
specify init --here --ai gemini          # Gemini CLI
specify init --here --ai copilot         # GitHub Copilot
# ... and 10+ more supported agents
```

### File Locations

```
your-project/
├── memory/constitution.md          # Project principles
├── specs/001-feature/
│   ├── spec.md                     # Requirements
│   ├── plan.md                     # Technical design
│   └── tasks.md                    # Implementation steps
└── .specify/                       # Configuration (don't edit)
```

### Error → Action Map

```
Test failures          → /speckit.analyze → Fix root cause
Build errors           → /speckit.plan → Update dependencies
Unclear requirements   → /speckit.clarify → Answer questions
Design flaws           → /speckit.plan → Revise architecture
Integration issues     → Check contracts → Update plan
```

---

## 🎉 You're Ready!

### Your First Workflow

```bash
# 1. Install and initialize
uv tool install specify-cli
cd your-project
specify init --here

# 2. Set your principles  
/speckit.constitution

# 3. Build something amazing
/speckit.specify "Your feature idea"
/speckit.plan
/speckit.tasks  
/speckit.implement

# 🎉 Feature complete with tests, docs, and best practices!
```

### Need More Detail?

- 📖 **Comprehensive Guide**: `spec-kit-comprehensive-guide.md`
- 🐛 **Error Recovery**: See Error Recovery section above
- 🏗️ **Brownfield Integration**: See Brownfield Projects section
- ✅ **Quality Checklists**: Use `/speckit.checklist` at any time

---

## 📚 Learn More

### Official Resources
- **GitHub Spec-Kit**: https://github.com/github/spec-kit
- **Official Docs**: Repository README.md
- **Spec-Driven Development**: spec-driven.md

### Community
- **Issues**: Report bugs and request features
- **Discussions**: Ask questions and share experiences
- **Contributing**: Help improve the project

---

**Happy coding with Spec-Kit!** 🚀

Transform your development process from code-first to spec-first, and build better software faster.

---

*Last Updated: 2025 | Version: Latest | License: MIT*
