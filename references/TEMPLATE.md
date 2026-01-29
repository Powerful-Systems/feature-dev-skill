# Project Patterns Template

This is a template for creating project-specific pattern documentation. Copy this file and customize it for your project.

## Technology Stack

List your core technologies:

- **Frontend**: [e.g., React 19, Vue 3, Svelte, etc.]
- **Backend**: [e.g., Node.js, Python FastAPI, Ruby on Rails, etc.]
- **Database**: [e.g., PostgreSQL, MongoDB, etc.]
- **Validation**: [e.g., Zod, Yup, Joi, etc.]
- **UI Library**: [e.g., ShadCN, Material-UI, Chakra, etc.]
- **Icons**: [e.g., lucide-react, heroicons, etc.]

## Critical Rules

List your project's most important coding rules that should NEVER be violated:

1. **Example Rule 1** - Brief explanation
2. **Example Rule 2** - Brief explanation
3. **Example Rule 3** - Brief explanation

Example:
1. **Never modify UI library components directly** - Always wrap them in custom components
2. **Database client is last parameter** - `(filters, db: Client)` not `(db, filters)`
3. **Validate with Zod** - Always `.parse()` external data

## Common Patterns

### Pattern Category 1 (e.g., Data Layer)

Describe your standard pattern for this category.

```typescript
// Example code showing the pattern
export async function fetchUser(id: string, db: Client): Promise<User> {
  // Implementation
}
```

**Key patterns**:
- Point 1
- Point 2
- Point 3

### Pattern Category 2 (e.g., API Endpoints)

```typescript
// Example code
```

**Key patterns**:
- Point 1
- Point 2

### Pattern Category 3 (e.g., Components)

```typescript
// Example code
```

**Key patterns**:
- Point 1
- Point 2

## File Organization

Show your project's directory structure:

```
src/
├── api/              # API routes
├── components/       # React components
│   ├── ui/          # UI library (don't modify)
│   └── shared/      # Shared components
├── lib/             # Utilities
└── types/           # TypeScript types
```

## Do's and Don'ts

### ✅ Do This

```typescript
// Good example
export function GoodComponent({ data }: Props) {
  // ...
}
```

### ❌ Don't Do This

```typescript
// Bad example
export const BadComponent = (props) => {
  // ...
}
```

## Common Gotchas

List common mistakes and how to avoid them:

1. **Gotcha 1**: Description of problem
   - **Solution**: How to fix it

2. **Gotcha 2**: Description of problem
   - **Solution**: How to fix it

## Testing Patterns

Describe how to test different types of code:

### Unit Tests

```typescript
// Example test
```

### Integration Tests

```typescript
// Example test
```

### E2E Tests

```typescript
// Example test
```

## Development Workflow

```bash
# Start dev server
npm run dev

# Run tests
npm test

# Run linter
npm run lint

# Format code
npm run format

# Build for production
npm run build
```

## Documentation Files

Link to other important docs:

- **docs/architecture.md** - System architecture
- **docs/api.md** - API documentation
- **docs/deployment.md** - Deployment guide
- **CLAUDE.md** - Claude-specific patterns

## Quick Reference Checklist

Before committing code, verify:
- [ ] Follows established patterns
- [ ] Validated with schema validation library
- [ ] Follows naming conventions
- [ ] Includes appropriate tests
- [ ] No linter errors
- [ ] Formatted with project formatter
- [ ] Updated relevant docs

---

## Customization Instructions

1. Copy this template to `references/project-patterns.md`
2. Replace all placeholder content with your project's details
3. Add or remove sections as needed
4. Update SKILL.md Phase 4 to reference this file
5. Keep it updated as patterns evolve
