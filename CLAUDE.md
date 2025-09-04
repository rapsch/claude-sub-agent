# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Claude Sub-Agent Spec Workflow System - A comprehensive AI-driven development workflow system built on Claude Code's Sub-Agents feature. This system transforms project ideas into production-ready code through specialized AI agents working in coordinated phases.

**Rails Specialization**: The system includes specialized Ruby on Rails agents and workflows, providing expert-level Rails development capabilities with Rails conventions, RSpec testing, and Rails-specific quality gates.

## Project Documentation Conventions (Important)

**Documentation Files:** All new documentation or task files must be saved under the `docs/` folder in this repository.For example:

- **Tasks & TODOs**: Save in `docs/{YYYY_MM_DD}/tasks/` (e.g., `docs/t2025_08_08/asks/ReleaseTodo.md` for a release checklist).
- **Requirements/Specs**: Save in `docs/{YYYY_MM_DD}/specs/` (e.g., `docs/2025_08_08/specs/AuthModuleRequirements.md`).
- **Design Docs**: Save in `docs/{YYYY_MM_DD}/design/` (e.g., `docs/2025_08_08/design/ArchitectureOverview.md`).
- **Code Files:** Follow the project structure (place new code in the appropriate src/module folder as discussed).
- **Tests:** Put new test files under the `tests/` directory, mirroring the code structure.

> **Important:** When creating a new file, ensure the directory exists or create it. Never default to the root directory for these files.

## Common Development Commands

### Workflow Execution

```bash
# Execute complete development workflow using slash command
/agent-workflow "Create a todo list web application with user authentication"

# Start workflow manually with orchestrator
Use spec-orchestrator: Create an enterprise CRM system with multi-tenancy support

# Phase-specific execution
Use spec-analyst: Analyze requirements for an e-commerce platform
Use spec-architect: Design system architecture for microservices
Use spec-developer: Implement user authentication based on specifications
```

### Rails-Specific Workflow Execution

```bash
# Rails application development workflow
/agent-workflow "Create a Rails e-commerce application with Stripe integration"

# Rails-specific orchestration
Use spec-orchestrator: Create a Rails SaaS application with multi-tenancy and Hotwire

# Rails domain specialists
Use rails-backend-architect: Design Rails backend architecture with ActiveRecord patterns
Use rails-frontend-architect: Implement Hotwire frontend with Turbo and Stimulus
Use rails-testing-specialist: Create comprehensive RSpec test suite with Factory Bot

# Rails quality validation
Use spec-tester: Generate Rails-specific tests (models, controllers, systems)
Use spec-validator: Evaluate Rails code quality with Rubocop and Brakeman
```

### Quality Gates and Testing

```bash
# The system includes three automated quality gates:
# Gate 1: Planning Quality (95% threshold) - After spec-planner
# Gate 2: Development Quality (80% threshold) - After spec-tester  
# Gate 3: Production Readiness (85% threshold) - After spec-validator

# Manual validation
Use spec-validator: Evaluate code quality and provide scoring
Use spec-tester: Generate comprehensive test suite for the implementation
```

### Rails Quality Gates and Testing

```bash
# Rails-specific quality gates with Rails tools:
# Gate 1: Rails Planning Quality (95% threshold) - Rails architecture, gems, database design
# Gate 2: Rails Development Quality (85% threshold) - Rubocop, RSpec coverage, Brakeman
# Gate 3: Rails Production Readiness (95% threshold) - Rails deployment, monitoring

# Rails quality validation commands
rubocop --auto-correct              # Rails code quality and style
bundle exec rspec --format progress # RSpec test execution
bundle exec brakeman               # Rails security scanning
rails test:system                  # Rails system tests
rails db:migrate:status           # Rails migration status

# Rails testing patterns
Use rails-testing-specialist: Create RSpec tests for Rails models and controllers
Use spec-tester: Generate Rails-specific test suites with Factory Bot
```

### Project Structure Operations

```bash
# Copy agents to a new project
mkdir -p .claude/agents .claude/commands
cp agents/* .claude/agents/
cp commands/agent-workflow.md .claude/commands/

# Organize agent files (current reorganization in progress)
# Backend agents: agents/backend/
# Frontend agents: agents/frontend/ 
# Spec workflow agents: agents/spec-agents/
# UI/UX agents: agents/ui-ux/
# Utility agents: agents/utility/
```

### Rails Project Structure Operations

```bash
# Setup Rails project with agent system
rails new my_app --database=postgresql --css=tailwind
cd my_app
mkdir -p .claude/agents .claude/commands
cp /path/to/claude-sub-agent/agents/spec-agents/* .claude/agents/
cp /path/to/claude-sub-agent/agents/backend/rails-* .claude/agents/
cp /path/to/claude-sub-agent/agents/frontend/rails-* .claude/agents/
cp /path/to/claude-sub-agent/agents/testing/rails-* .claude/agents/

# Rails-specific agent organization:
# rails-backend-architect.md     - Rails backend patterns and ActiveRecord
# rails-frontend-architect.md    - Hotwire, Turbo, Stimulus patterns
# rails-testing-specialist.md    - RSpec, Factory Bot, Rails testing
# spec-orchestrator.md          - Rails workflow coordination
# spec-developer.md             - Rails implementation specialist
# spec-architect.md             - Rails system architecture
# spec-tester.md                - Rails testing and quality
```

## System Architecture

### Multi-Phase Workflow Design

The system follows a three-phase approach with quality gates:

1. **Planning Phase (20-25% of project time)**
   - spec-analyst: Requirements analysis and user stories
   - spec-architect: System architecture and API design
   - spec-planner: Task breakdown and estimation
   - Quality Gate 1: 95% compliance threshold

2. **Development Phase (60-65% of project time)**
   - spec-developer: Code implementation following specifications
   - spec-tester: Comprehensive test suite generation
   - Quality Gate 2: 80% compliance threshold

3. **Validation Phase (15-20% of project time)**
   - spec-reviewer: Code review and best practices validation
   - spec-validator: Final production readiness assessment
   - Quality Gate 3: 85% compliance threshold

### Agent Categories

**Workflow Agents (spec-agents/)**

- spec-orchestrator: Workflow coordination and quality gate management
- spec-analyst: Requirements analysis specialist
- spec-architect: System architecture designer  
- spec-planner: Task breakdown and planning
- spec-developer: Implementation specialist
- spec-tester: Testing expert
- spec-reviewer: Code review specialist
- spec-validator: Final validation expert

**Domain Specialists**

- senior-frontend-architect: React/Vue/Next.js expert
- senior-backend-architect: Go/TypeScript backend systems
- ui-ux-master: UI/UX design and implementation

**Rails Specialists**

- rails-backend-architect: Ruby on Rails backend expert with ActiveRecord, services, jobs
- rails-frontend-architect: Hotwire (Turbo + Stimulus) and Rails frontend specialist  
- rails-testing-specialist: RSpec, Factory Bot, and Rails testing expert
- spec-orchestrator: Rails workflow coordination with Rails-specific quality gates
- spec-developer: Rails implementation specialist following Rails conventions
- spec-architect: Rails system architecture designer
- spec-tester: Rails testing and quality assurance specialist

**Utility Agents**

- refactor-agent: Code quality and refactoring specialist

### Quality Framework

Each phase includes automated quality gates with specific thresholds:

- Requirements completeness validation
- Architecture feasibility assessment
- Code quality metrics and test coverage
- Security vulnerability scanning
- Production deployment readiness

### Rails Quality Framework

Rails-specific quality gates with Rails tools and conventions:

- Rails requirements completeness with user stories and acceptance criteria
- Rails architecture feasibility with MVC pattern compliance
- Rails code quality with Rubocop style guide compliance
- RSpec test coverage thresholds (>80% line coverage)
- Rails security scanning with Brakeman vulnerability detection
- Rails performance benchmarks and N+1 query prevention
- Rails conventions compliance and best practices adherence
- Rails production deployment readiness (Docker, Kamal, environment configs)

### Agent Communication Protocol

Agents communicate through structured artifacts:

- Each agent produces specific documentation (requirements.md, architecture.md, etc.)
- Next agent uses previous outputs as input
- Orchestrator manages the workflow progression
- Quality gates ensure consistency and standards compliance

## Expected Output Structure

```
project/
├── docs/
│   ├── requirements.md      # Detailed requirements specification
│   ├── architecture.md      # System architecture design
│   ├── api-spec.md         # API specifications and contracts
│   └── user-stories.md     # User stories with acceptance criteria
├── src/
│   ├── components/         # Reusable components
│   ├── services/          # Business logic services
│   ├── utils/             # Utility functions
│   └── types/             # Type definitions
├── tests/
│   ├── unit/              # Unit tests
│   ├── integration/       # Integration tests
│   └── e2e/               # End-to-end tests
├── package.json           # Project dependencies
└── README.md              # Project documentation
```

### Rails Expected Output Structure

```
rails_project/
├── docs/
│   ├── requirements.md      # Rails requirements with user stories
│   ├── architecture.md      # Rails MVC architecture design
│   ├── api-spec.md         # Rails API specifications and routes
│   └── deployment.md       # Rails deployment and configuration guide
├── app/
│   ├── models/             # ActiveRecord models with associations
│   ├── controllers/        # Rails controllers with actions
│   ├── views/              # ERB/Haml templates with partials
│   ├── services/           # Rails service objects for business logic
│   ├── jobs/               # ActiveJob/Sidekiq background jobs
│   ├── mailers/            # ActionMailer classes
│   └── helpers/            # Rails view helpers
├── config/
│   ├── routes.rb           # Rails routing configuration
│   ├── database.yml        # Database configuration
│   └── application.rb      # Rails application configuration
├── db/
│   ├── migrate/            # ActiveRecord migrations
│   └── seeds.rb            # Database seed data
├── spec/
│   ├── models/             # RSpec model tests
│   ├── controllers/        # RSpec controller tests
│   ├── systems/            # RSpec system/integration tests
│   ├── jobs/               # RSpec background job tests
│   └── support/            # RSpec support files and factories
├── Gemfile                 # Rails gem dependencies
├── Gemfile.lock           # Locked gem versions
└── README.md              # Rails project documentation
```

## Key Integration Points

### Slash Command Integration

The `/agent-workflow` command provides one-command execution of the entire development pipeline:

- Supports quality threshold configuration (--quality=75-95)
- Allows agent skipping (--skip-agent=spec-analyst)
- Phase-specific execution (--phase=planning|development|validation)
- Language selection (--language=zh|en)

### Sub-Agent Chain Process

The system uses Claude Code's sub-agent syntax for coordinated execution:

```
First use the spec-analyst sub agent → then spec-architect sub agent → then spec-developer sub agent → then spec-validator sub agent → quality gate decision → if score ≥95% continue to spec-tester, otherwise loop back with feedback

### Rails Sub-Agent Chain Process

Rails-specific agent chain for Ruby on Rails applications:

```
First use the spec-analyst sub agent (Rails requirements) → then rails-backend-architect sub agent (Rails architecture) → then spec-developer sub agent (Rails implementation) → then rails-testing-specialist sub agent (RSpec tests) → Rails quality gate decision (Rubocop + Brakeman + RSpec coverage) → if score ≥85% continue to spec-validator, otherwise loop back with Rails-specific feedback
```
```

### Quality Gate Mechanism

- Validation Score ≥95%: Proceed to next phase
- Validation Score <95%: Loop back with specific feedback
- Maximum 3 iterations to prevent infinite loops
- Expected progression: Round 1 (80-90%) → Round 2 (90-95%) → Round 3 (95%+)

## Best Practices

### For Working with Agents

- Start with spec-orchestrator for complete projects
- Use domain specialists for specific expertise areas
- Allow each agent to complete their phase before intervention
- Trust the quality gate system for consistent standards
- Review artifacts between phases for course correction

### For Working with Rails Agents

- Start with spec-orchestrator for complete Rails projects
- Use rails-backend-architect for Rails backend architecture and ActiveRecord design
- Use rails-frontend-architect for Hotwire (Turbo + Stimulus) frontend implementation
- Use rails-testing-specialist for comprehensive RSpec test suites
- Allow Rails agents to implement Rails conventions and best practices
- Trust Rails-specific quality gates (Rubocop, Brakeman, RSpec coverage)
- Review Rails artifacts (models, controllers, migrations) between phases

### For Project Setup

- Copy all agents and slash command to project's .claude directory
- Provide clear project descriptions with constraints and requirements
- Specify quality expectations (75% for prototypes, 95% for enterprise)
- Include existing documentation when available

### For Rails Project Setup

- Copy Rails-specific agents to project's .claude directory (rails-backend-architect, rails-frontend-architect, rails-testing-specialist)
- Provide Rails project descriptions with gem requirements and Rails version
- Specify Rails quality expectations (80% RSpec coverage minimum, Rubocop compliance)
- Include existing Rails documentation, schema, and routes when available
- Set up Rails development environment (Ruby version, database, Redis for caching/jobs)
- Configure Rails testing environment (RSpec, Factory Bot, database cleaner)

### For Customization

- Adjust quality thresholds based on project needs
- Skip agents for simpler projects (e.g., skip spec-analyst if requirements exist)
- Use phase-specific execution for targeted improvements
- Integrate with existing CI/CD workflows

### For Rails Customization

- Adjust Rails quality thresholds (RSpec coverage, Rubocop compliance) based on project needs
- Skip Rails agents for simpler Rails projects (use spec-developer if Rails architecture exists)
- Use Rails phase-specific execution for targeted Rails improvements
- Integrate with Rails CI/CD workflows (GitHub Actions with Rails, Heroku, AWS deployment)
- Customize Rails gem selection and Rails version based on project requirements
- Configure Rails-specific tools (Brakeman security, SimpleCov coverage, Rails generators)

## Troubleshooting

### Common Issues

- **Agent Not Found**: Verify agents are in correct .claude/agents directory
- **Quality Gate Failures**: Review specific criteria, allow agents to revise work
- **Workflow Stuck**: Check orchestrator status, restart from last checkpoint

### Rails Common Issues

- **Rails Agent Not Found**: Verify Rails agents (rails-backend-architect, rails-frontend-architect, rails-testing-specialist) are in .claude/agents directory
- **Rails Quality Gate Failures**: Check Rubocop violations, RSpec test failures, or Brakeman security issues
- **Rails Workflow Stuck**: Check Rails database connection, gem compatibility, or Rails environment setup
- **Rails Migration Issues**: Verify database is running and migrations are compatible with Rails version
- **Rails Test Failures**: Check test database setup, Factory Bot configuration, and RSpec gems

### Debug Mode

Enable verbose logging by requesting: "Use spec-orchestrator with debug mode and show all agent interactions"

### Rails Debug Mode

Enable Rails-specific debug logging:

```bash
# Request Rails debug mode
"Use spec-orchestrator with Rails debug mode and show all Rails agent interactions"

# Rails-specific debugging commands
rails console                    # Rails console for debugging
rails db:migrate:status         # Check migration status
bundle exec rspec --format doc  # Detailed RSpec output
rubocop --display-cop-names     # Detailed Rubocop violations
brakeman --format json          # Detailed security scan results
```

## Integration with External Systems

The system can be integrated with:

- GitHub Actions for CI/CD validation
- Custom quality gates and validation criteria  
- Domain-specific workflows and specialized orchestrators
- Existing development tools and frameworks

## Rails Integration with External Systems

The Rails agent system can be integrated with:

- **GitHub Actions for Rails CI/CD**: Automated RSpec testing, Rubocop linting, Brakeman security scanning
- **Rails Quality Gates**: Custom RSpec coverage thresholds, Rails conventions compliance, performance benchmarks
- **Rails Deployment Systems**: Integration with Kamal, Capistrano, Heroku, AWS Rails deployments
- **Rails Development Tools**: Integration with existing Rails gems, Redis, Sidekiq, PostgreSQL/MySQL
- **Rails Monitoring**: New Relic, DataDog, Sentry integration for Rails application monitoring
- **Rails Security**: Integration with Rails security gems (bundle-audit, strong_migrations, etc.)
