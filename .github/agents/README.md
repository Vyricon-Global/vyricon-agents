# Agent Configuration for Copilot

This directory contains agent definitions for GitHub Copilot to use in the Vyricon Multi-Agent System.

## Available Agents

### 1. vyricon-architect
**File**: `vyricon-architect.md`  
**Role**: System architecture design and technical planning  
**Use for**: Initial system design, technology stack decisions, component breakdown

### 2. vyricon-frontend
**File**: `vyricon-frontend.md`  
**Role**: Frontend development (Next.js 16, React 19, TailwindCSS)  
**Use for**: UI components, pages, layouts, responsive design, accessibility

### 3. vyricon-backend
**File**: `vyricon-backend.md`  
**Role**: Backend development (API routes, Server Actions, database)  
**Use for**: API endpoints, server actions, database schemas, authentication

### 4. vyricon-ai
**File**: `vyricon-ai.md`  
**Role**: AI/ML integration (Vercel AI SDK, OpenAI, Claude, Gemini)  
**Use for**: AI features, streaming, tool calling, embeddings, vector search

### 5. vyricon-security
**File**: `vyricon-security.md`  
**Role**: Security and compliance (NIST 800-53, OWASP, zero-trust)  
**Use for**: Security audits, threat modeling, compliance mapping, vulnerability scanning

### 6. vyricon-qa
**File**: `vyricon-qa.md`  
**Role**: Quality assurance and testing  
**Use for**: Test generation, coverage analysis, performance testing, accessibility testing

## Usage with GitHub Copilot

### In VS Code/Cursor
Reference agents in your prompts:
```
@vyricon-architect Design a tour booking system architecture

@vyricon-frontend Create a responsive search form component

@vyricon-backend Build an API endpoint for tour bookings

@vyricon-ai Add AI-powered tour recommendations

@vyricon-security Audit this authentication implementation

@vyricon-qa Generate test suite for booking flow
```

### In GitHub Actions
Agents are automatically invoked by the orchestrator workflow:
```yaml
workflow_dispatch:
  inputs:
    task_description: "Build tour agency website"
```

## Agent Collaboration

Agents work together in this flow:
1. **Architect** creates system design
2. **Frontend + Backend + AI** develop in parallel
3. **Security** audits all components
4. **QA** validates everything

## Knowledge Base

All agents access:
- 174+ documentation URLs
- Theia Enterprise protocols
- Corporate standards
- Security frameworks
- Best practices

## Quality Standards

All agents enforce:
- ✅ TypeScript strict mode
- ✅ 90%+ test coverage
- ✅ WCAG 2.1 AA accessibility
- ✅ NIST 800-53 compliance
- ✅ OWASP Top 10 clean
- ✅ Performance budgets met

---

*Vyricon Global Agent System*
