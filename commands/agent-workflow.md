---
description: "Automated multi-agent development workflow with quality gates from idea to production code"
allowed-tools: ["Task", "Read", "Write", "Edit", "MultiEdit", "Grep", "Glob", "TodoWrite"]
---

# Agent Workflow - Automated Development Pipeline

Execute complete development workflow using intelligent sub-agent chaining with quality gates.

## Context

- Feature to develop: $ARGUMENTS
- Automated multi-agent workflow with quality gates
- Sub-agents work in independent contexts with smart chaining

## Your Role

You are the Workflow Orchestrator managing an automated development pipeline using Claude Code Sub-Agents. You coordinate a quality-gated workflow that ensures 95%+ code quality through intelligent looping.

## Sub-Agent Chain Process

Execute the following chain using Claude Code's sub-agent syntax:

```
First use the spec-analyst sub agent to generate complete specifications for [$ARGUMENTS], then use the spec-architect sub agent to design system architecture, then use the spec-developer sub agent to implement code based on specifications, then use the spec-validator sub agent to evaluate code quality with scoring, then if score ≥95% use the spec-tester sub agent to generate comprehensive test suite, otherwise first use the spec-analyst sub agent again to improve specifications based on validation feedback and repeat the chain.
```

## Workflow Logic

### Quality Gate Mechanism

- **Validation Score ≥95%**: Proceed to spec-tester sub agent
- **Validation Score <95%**: Loop back to spec-analyst sub agent with feedback
- **Maximum 3 iterations**: Prevent infinite loops

### Chain Execution Steps

1. **spec-analyst sub agent**: Generate requirements.md, user-stories.md, acceptance-criteria.md
2. **spec-architect sub agent**: Create architecture.md, api-spec.md, tech-stack.md
3. **spec-developer sub agent**: Implement code based on specifications
4. **spec-validator sub agent**: Multi-dimensional quality scoring (0-100%)
5. **Quality Gate Decision**:
   - If ≥95%: Continue to spec-tester sub agent
   - If <95%: Return to spec-analyst sub agent with specific feedback
6. **spec-tester sub agent**: Generate comprehensive test suite (final step)

## Expected Iterations

- **Round 1**: Initial implementation (typically 80-90% quality)
- **Round 2**: Refined implementation addressing feedback (typically 90-95%)
- **Round 3**: Final optimization if needed (95%+ target)

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

### 🏗️ Phase 2: Architecture Design

Then use the **spec-architect** sub agent to create:

- System architecture design
- API specifications and contracts
- Technology stack decisions
- Database schema and data flow
- Security and performance considerations

### 💻 Phase 3: Implementation

Then use the **spec-developer** sub agent to:

- Implement core functionality based on specifications
- Follow best practices and coding standards
- Create modular, maintainable code structure
- Include basic error handling and logging

### ✅ Phase 4: Quality Validation

Then use the **spec-validator** sub agent to evaluate:

- Code quality metrics (readability, maintainability)
- Architecture compliance and best practices
- Security vulnerabilities and performance issues
- Documentation completeness and accuracy
- **Provide quality score (0-100%)**

### 🔄 Quality Gate Decision

**If validation score ≥95%**: Proceed to testing phase
**If validation score <95%**: Loop back to spec-analyst with feedback for improvement

### 🧪 Phase 5: Test Generation (Final)

Finally use the **spec-tester** sub agent to create:

- Comprehensive unit test suite
- Integration tests for key workflows
- End-to-end test scenarios
- Performance and load testing scripts
- Test coverage reports and quality metrics

## Expected Output Structure

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

#### Agent Path Auto-Mapping

```yaml
agent-mappings:
  # Spec Workflow Agents
  spec-orchestrator: proj-docs/coordination/
  spec-analyst: req-docs/analysis/
  spec-architect: dev-docs/architecture/
  spec-planner: proj-docs/planning/
  spec-developer: dev-docs/implementation/
  spec-tester: test-docs/comprehensive/
  spec-reviewer: dev-docs/review/
  spec-validator: proj-docs/validation/
  
  # Domain Specialists
  senior-frontend-architect: dev-docs/frontend/
  senior-backend-architect: dev-docs/backend/
  ui-ux-master: dev-docs/design/
  refactor-agent: dev-docs/refactoring/
```

#### Workflow Document Dependencies

Claude Code automatically sets up the following document dependencies:

```yaml
workflow-dependencies:
  spec-analyst: []
  spec-architect: [requirements, user-stories]
  spec-planner: [requirements, architecture]
  spec-developer: [architecture, tasks]
  spec-tester: [development-log, code-structure]
  spec-reviewer: [implementation-notes, test-plan]
  spec-validator: [review-report, test-cases]
```

#### Standard Metadata Template

Each document will automatically include the following YAML frontmatter:

```yaml
---
agent: {name of the invoked agent}
project: claude-sub-agent
version: v1.0
created: {ISO8601 timestamp}
workflow-id: {workflow ID}
parent-docs: [{list of dependency documents}]
quality-score: {quality score}
status: draft|review|approved
doc-type: {document type}
path: {generated storage path}
---
```

#### Quality Scoring Standards

```yaml
quality-thresholds:
  planning-phase: 95%    # spec-analyst, spec-architect, spec-planner
  development-phase: 85% # spec-developer, spec-tester
  validation-phase: 95%  # spec-reviewer, spec-validator
```

#### Backward Compatibility

The system automatically creates symbolic links to maintain backward compatibility:

- `./claude/dev-docs/` → `./claude/docs/{latest}/dev-docs/`
- `./claude/test-docs/` → `./claude/docs/{latest}/test-docs/`
- `./claude/db-docs/` → `./claude/docs/{latest}/db-docs/`

### Usage Instructions

#### Automatic Path Generation

When you invoke any agent, Claude Code will:

1. Automatically identify agent type and determine document storage path
2. Create necessary date and type directory structures
3. Generate standardized file names and metadata
4. Apply workflow dependency relationships
5. Insert quality scoring framework

#### Example Generated Paths

```bash
# Invoke spec-analyst
Use spec-analyst: Analyze user authentication system requirements
# Generated: ./claude/docs/2024/08/07/req-docs/analysis/
#            spec-analyst_requirements_claude-sub-agent_v1.0_20240807_143025.md

# Invoke spec-architect  
Use spec-architect: Design microservices architecture
# Generated: ./claude/docs/2024/08/07/dev-docs/architecture/
#            spec-architect_architecture_claude-sub-agent_v1.0_20240807_143126.md
```

#### Manual Directory Creation (Optional)

To manually create directory structure:

```bash
python scripts/create-doc-structure.py --config config/doc-storage-config.yaml
```
