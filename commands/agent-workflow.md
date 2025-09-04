---
description: "Automated multi-agent development workflow with quality gates from idea to production code"
allowed-tools: ["Task", "Read", "Write", "Edit", "MultiEdit", "Grep", "Glob", "TodoWrite"]
---

# Agent Workflow - Automated Development Pipeline

Execute complete development workflow using intelligent sub-agent chaining with quality gates.

**Rails Support**: Enhanced with specialized Ruby on Rails workflow capabilities, including Rails conventions, RSpec testing, and Rails-specific quality gates.

## Context

- Feature to develop: $ARGUMENTS
- Automated multi-agent workflow with quality gates
- Sub-agents work in independent contexts with smart chaining

## Your Role

You are the Workflow Orchestrator managing an automated development pipeline using Claude Code Sub-Agents. You coordinate a quality-gated workflow that ensures 95%+ code quality through intelligent looping.

**Rails Orchestration**: For Ruby on Rails projects, you coordinate Rails-specific agents (rails-backend-architect, rails-frontend-architect, rails-testing-specialist) and apply Rails conventions, RSpec testing standards, and Rails quality gates.

## Sub-Agent Chain Process

Execute the following chain using Claude Code's sub-agent syntax:

### General Development Chain
```
First use the spec-analyst sub agent to generate complete specifications for [$ARGUMENTS], then use the spec-architect sub agent to design system architecture, then use the spec-developer sub agent to implement code based on specifications, then use the spec-validator sub agent to evaluate code quality with scoring, then if score ≥95% use the spec-tester sub agent to generate comprehensive test suite, otherwise first use the spec-analyst sub agent again to improve specifications based on validation feedback and repeat the chain.
```

### Rails Development Chain
```
First use the spec-analyst sub agent to generate Rails requirements and user stories for [$ARGUMENTS], then use the rails-backend-architect sub agent to design Rails MVC architecture with ActiveRecord patterns, then use the spec-developer sub agent to implement Rails code following conventions, then use the rails-testing-specialist sub agent to create RSpec test suite, then use the spec-validator sub agent to evaluate Rails code quality with Rubocop and Brakeman, then if score ≥85% use the spec-tester sub agent for final Rails validation, otherwise first use the rails-backend-architect sub agent again to improve Rails architecture based on feedback and repeat the chain.
```

## Workflow Logic

### Quality Gate Mechanism

- **Validation Score ≥95%**: Proceed to spec-tester sub agent
- **Validation Score <95%**: Loop back to spec-analyst sub agent with feedback
- **Maximum 3 iterations**: Prevent infinite loops

### Chain Execution Steps

### General Development Steps
1. **spec-analyst sub agent**: Generate requirements.md, user-stories.md, acceptance-criteria.md
2. **spec-architect sub agent**: Create architecture.md, api-spec.md, tech-stack.md
3. **spec-developer sub agent**: Implement code based on specifications
4. **spec-validator sub agent**: Multi-dimensional quality scoring (0-100%)
5. **Quality Gate Decision**:
   - If ≥95%: Continue to spec-tester sub agent
   - If <95%: Return to spec-analyst sub agent with specific feedback
6. **spec-tester sub agent**: Generate comprehensive test suite (final step)

### Rails Development Steps
1. **spec-analyst sub agent**: Generate Rails requirements.md with user stories and acceptance criteria
2. **rails-backend-architect sub agent**: Create Rails architecture.md with MVC patterns, database design, gem selection
3. **spec-developer sub agent**: Implement Rails models, controllers, views following Rails conventions
4. **rails-testing-specialist sub agent**: Create RSpec test suite (models, controllers, systems)
5. **spec-validator sub agent**: Rails quality scoring with Rubocop, Brakeman, RSpec coverage (0-100%)
6. **Rails Quality Gate Decision**:
   - If ≥85%: Continue to spec-tester sub agent
   - If <85%: Return to rails-backend-architect sub agent with Rails-specific feedback
7. **spec-tester sub agent**: Generate comprehensive Rails test validation (final step)

## Expected Iterations

### General Development Iterations
- **Round 1**: Initial implementation (typically 80-90% quality)
- **Round 2**: Refined implementation addressing feedback (typically 90-95%)
- **Round 3**: Final optimization if needed (95%+ target)

### Rails Development Iterations
- **Round 1**: Initial Rails implementation (typically 75-85% quality)
- **Round 2**: Rails convention compliance and optimization (typically 85-90%)
- **Round 3**: Final Rails quality optimization if needed (85%+ target)

## Output Format

1. **Workflow Initiation** - Start sub-agent chain with feature description
2. **Progress Tracking** - Monitor each sub-agent completion
3. **Quality Gate Decisions** - Report review scores and next actions
4. **Completion Summary** - Final artifacts and quality metrics

## Key Benefits

- **Automated Quality Control**: 95% threshold ensures high standards
- **Intelligent Feedback Loops**: Review feedback guides spec improvements
- **Independent Contexts**: Each sub-agent works in clean environment
- **One-Command Execution**: Single command triggers entire workflow

---

## Execute Workflow

**Feature Description**: $ARGUMENTS

Starting automated development workflow with quality gates...

### 🎯 Phase 1: Specification Generation

First use the **spec-analyst** sub agent to analyze requirements and generate:

- Detailed requirements documentation
- User stories with acceptance criteria
- Technical constraints and assumptions
- Success metrics and validation criteria

#### Rails-Specific Phase 1

For Rails projects, spec-analyst also generates:

- Rails-specific user stories with Rails conventions
- Rails gem requirements and version constraints
- Rails database design considerations
- Rails authentication and authorization requirements
- Rails API design patterns and RESTful conventions

### 🏗️ Phase 2: Architecture Design

Then use the **spec-architect** sub agent to create:

- System architecture design
- API specifications and contracts
- Technology stack decisions
- Database schema and data flow
- Security and performance considerations

#### Rails-Specific Phase 2

For Rails projects, use **rails-backend-architect** sub agent to create:

- Rails MVC architecture design with proper separation
- ActiveRecord model associations and database relationships
- Rails routing and RESTful API design
- Rails gem selection and dependency management
- Rails security patterns (strong parameters, CSRF protection)
- Rails performance patterns (caching, background jobs)
- Rails deployment architecture (Docker, Kamal, environment configs)

### 💻 Phase 3: Implementation

Then use the **spec-developer** sub agent to:

- Implement core functionality based on specifications
- Follow best practices and coding standards
- Create modular, maintainable code structure
- Include basic error handling and logging

#### Rails-Specific Phase 3

For Rails projects, spec-developer implements:

- ActiveRecord models with proper associations and validations
- Rails controllers with RESTful actions and strong parameters
- Rails views with ERB/Haml templates and partials
- Rails service objects for complex business logic
- Rails background jobs (ActiveJob/Sidekiq) for async processing
- Rails mailers for email functionality
- Rails helpers and concerns for code reuse
- Rails migration files for database schema changes

### ✅ Phase 4: Quality Validation

Then use the **spec-validator** sub agent to evaluate:

- Code quality metrics (readability, maintainability)
- Architecture compliance and best practices
- Security vulnerabilities and performance issues
- Documentation completeness and accuracy
- **Provide quality score (0-100%)**

#### Rails-Specific Phase 4

For Rails projects, also use **rails-testing-specialist** sub agent for:

- RSpec test suite creation (models, controllers, systems)
- Factory Bot setup for test data generation
- Rails-specific testing patterns and helpers
- Test coverage analysis with SimpleCov
- Rails integration and system testing

Then spec-validator evaluates Rails-specific quality:

- Rails conventions compliance (Rubocop style guide)
- Rails security scanning (Brakeman vulnerability detection)
- RSpec test coverage thresholds (>80% line coverage)
- Rails performance patterns (N+1 query prevention)
- ActiveRecord best practices and optimization
- **Provide Rails quality score (0-100%)**

### 🔄 Quality Gate Decision

**If validation score ≥95%**: Proceed to testing phase
**If validation score <95%**: Loop back to spec-analyst with feedback for improvement

#### Rails Quality Gate Decision

**If Rails validation score ≥85%**: Proceed to final Rails testing phase
**If Rails validation score <85%**: Loop back to rails-backend-architect with Rails-specific feedback for improvement

### 🧪 Phase 5: Test Generation (Final)

Finally use the **spec-tester** sub agent to create:

- Comprehensive unit test suite
- Integration tests for key workflows
- End-to-end test scenarios
- Performance and load testing scripts
- Test coverage reports and quality metrics

#### Rails-Specific Phase 5

For Rails projects, spec-tester creates Rails-specific validations:

- Final Rails code review and quality assessment
- Rails deployment readiness checklist
- Rails security validation (Brakeman final scan)
- Rails performance validation and optimization recommendations
- Rails documentation completeness (README, API docs)
- Rails environment configuration validation
- Rails monitoring and logging setup validation

## Expected Output Structure

### General Project Structure
```
project/
├── docs/
│   ├── requirements.md
│   ├── architecture.md
│   ├── api-spec.md
│   └── user-stories.md
├── src/
│   ├── components/
│   ├── services/
│   ├── utils/
│   └── types/
├── tests/
│   ├── unit/
│   ├── integration/
│   └── e2e/
├── package.json
└── README.md
```

### Rails Project Structure
```
rails_project/
├── docs/
│   ├── requirements.md      # Rails requirements with user stories
│   ├── architecture.md      # Rails MVC architecture design
│   ├── api-spec.md         # Rails API routes and specifications
│   └── deployment.md       # Rails deployment configuration guide
├── app/
│   ├── models/             # ActiveRecord models
│   ├── controllers/        # Rails controllers
│   ├── views/              # ERB/Haml templates
│   ├── services/           # Rails service objects
│   ├── jobs/               # ActiveJob background jobs
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
│   ├── systems/            # RSpec system tests
│   └── support/            # RSpec configuration and factories
├── Gemfile                 # Rails gem dependencies
└── README.md               # Rails project documentation
```

**Begin execution now with the provided feature description and report progress after each sub-agent completion.**

## Unified Document Storage Configuration

### Project Document Storage Standards

All agent-generated documents follow the unified storage standards below:

#### Basic Configuration

```yaml
project-info:
  name: "claude-sub-agent"
  display-name: "Claude Sub-Agent Spec Workflow System"
  version: "v1.0"
  doc-root: "./claude/docs/"
  legacy-root: "./claude/"
```

#### Path Generation Rules

Claude Code automatically applies the following path generation logic:

```
./claude/docs/{YYYY}/{MM}/{DD}/{doc-type}/{subdirectory}/
{agent}_{artifact}_{project}_{version}_{timestamp}.md
```
