# Usage Examples

This document provides concrete examples of using the Feature Development Workflow skill.

## Example 1: Simple Feature Addition

**Scenario**: Adding a new filter to a search page

**Issue**: `#456 - Add date range filter to search`

**Invocation**:
```
/feature-dev-workflow #456
```

**Flow**:
1. **Phase 1**: Explored existing filter implementations, proposed 3 approaches (dropdown, calendar, preset ranges), user chose calendar
2. **Phase 2**: Identified files to modify (SearchFilters.tsx, useSearchParams hook)
3. **Phase 3**: Simplified by reusing existing DatePicker component
4. **Phase 4**: Implemented in 2 files, took 15 minutes
5. **Phase 5**: Tested in browser, found and fixed timezone bug
6. **Phase 6**: Removed unnecessary state management
7. **Phase 7**: Aligned with design system spacing
8. **Phase 8**: Tested all edge cases, ran formatter and build
9. **Phase 9**: Created PR with before/after screenshots
10. **Phase 10**: No docs needed (simple UI change)

**Outcome**: Clean implementation, 1 bug caught early, shipped in 1 PR

---

## Example 2: Complex Backend Feature

**Scenario**: Implementing a new API endpoint with database changes

**Issue**: `ENG-789 - Add user activity tracking`

**Invocation**:
```
/feature-dev-workflow ENG-789
```

**Flow**:
1. **Phase 1**:
   - Explored existing analytics patterns
   - Proposed 3 approaches: client-side only, server-side batch, hybrid
   - User chose server-side batch for privacy
   - Updated ticket with refined spec and privacy considerations

2. **Phase 2**:
   - Planned database schema (new `user_activities` table)
   - Identified API endpoints needed
   - Mapped dependencies (requires auth middleware)

3. **Phase 3**:
   - Challenged need for real-time processing (batch is simpler)
   - Removed unnecessary activity types
   - Simplified to 3 core events instead of 10

4. **Phase 4**:
   - Used parallel execution (one agent for DB migration, one for API)
   - Backend agent implemented schema and queries
   - API agent implemented endpoints with validation
   - Coordinated on shared types

5. **Phase 5**:
   - Tested API with curl and Postman
   - Verified database writes
   - Found and fixed N+1 query issue

6. **Phase 6**:
   - Ran code-simplifier
   - Removed redundant validation layer
   - Simplified batch processing logic

7. **Phase 7**: Skipped (no UI changes)

8. **Phase 8**:
   - Ran full test suite
   - Added integration tests
   - Verified build passes
   - Load tested with 1000 requests

9. **Phase 9**:
   - Created PR with API documentation
   - Included database migration notes
   - Added testing instructions

10. **Phase 10**:
    - Updated API.md with new endpoints
    - Added one-line to CLAUDE.md about activity tracking pattern

**Outcome**: Robust implementation, caught performance issue early, good documentation

---

## Example 3: Bug Fix with Scope Creep

**Scenario**: Fixing a UI bug that revealed larger issues

**Issue**: `BUG-123 - Button not disabled during loading`

**Invocation**:
```
/feature-dev-workflow BUG-123
```

**Flow**:
1. **Phase 1**:
   - Explored button implementation
   - Found inconsistent loading states across 5 components
   - **Used AskUserQuestion**: "Found 5 components with same issue. Fix all or just this one?"
   - User chose: "Fix all, let's make it consistent"
   - Updated ticket scope

2. **Phase 2**:
   - Identified all affected components
   - Planned to create shared `useLoadingState` hook

3. **Phase 3**:
   - Challenged hook approach - maybe just props pattern?
   - Decided hook is cleaner for this case
   - Kept it simple (no extra features)

4. **Phase 4**:
   - Created `useLoadingState` hook
   - Refactored 5 components to use it
   - Removed duplicate loading logic

5. **Phase 5**: Tested all 5 components in browser

6. **Phase 6**: Code-simplifier suggested removing unused hook options

7. **Phase 7**: Design review confirmed consistent loading states

8. **Phase 8**: Tested all edge cases, formatter and build passed

9. **Phase 9**: PR showed before/after for each component

10. **Phase 10**: Added pattern to project docs for future use

**Outcome**: Fixed bug + improved codebase consistency, well-documented pattern

---

## Example 4: Workflow Stopped Early

**Scenario**: Feature seemed simple but revealed architectural issues

**Issue**: `FEAT-999 - Add export to CSV button`

**Invocation**:
```
/feature-dev-workflow FEAT-999
```

**Flow**:
1. **Phase 1**:
   - Explored data structure
   - Found data is paginated and not all loaded client-side
   - Proposed 3 approaches:
     1. Export current page only (simple)
     2. Fetch all pages then export (slow)
     3. Server-side export endpoint (proper solution)

2. **Phase 2**:
   - Started planning approach #3
   - Realized this requires backend changes not in scope
   - **Stopping condition hit**: Scope creep detected

3. **Asked User**:
   - "This requires backend work. Export all data or just current page?"
   - User chose: "Just current page for now, we'll do full export later"

4. **Returned to Phase 1**:
   - Updated ticket to reflect simplified scope
   - Documented that full export is follow-up work

5. **Phase 2-9**: Continued with simple approach

6. **Phase 10**: Created follow-up ticket for server-side export

**Outcome**: Avoided scope creep, shipped simple version fast, documented next step

---

## Example 5: Parallel Execution

**Scenario**: Independent backend and frontend work

**Issue**: `#777 - Add user profile page`

**Invocation**:
```
/feature-dev-workflow #777
```

**Flow**:
1. **Phase 1-3**: Normal planning and simplification

2. **Phase 4** with parallel execution:
   - Clearly defined boundaries:
     - Agent A: API endpoint + database queries
     - Agent B: Profile page component + routing
   - Documented interface contract (API shape)
   - Both agents worked simultaneously
   - No conflicts (separate files)

3. **Phase 5**: Integrated and tested together

4. **Phases 6-10**: Normal flow

**Outcome**: Saved time with parallel work, clear boundaries prevented conflicts

---

## Common Patterns

### When to Use AskUserQuestion

✅ **Good times to ask**:
- Scope is ambiguous (Example 3)
- Found larger issues than expected (Example 3)
- Multiple valid approaches with tradeoffs (Example 1, 2)
- Uncertain about product priorities (Example 4)

❌ **Don't ask about**:
- Implementation details (just use best practices)
- Code style choices (follow project conventions)
- Obvious bugs (just fix them)

### When to Stop and Reassess

From the examples above:
- Example 4: Scope creep detected → stopped and asked
- Example 3: Found broader issue → asked to expand scope
- Example 2: No issues → completed full workflow

### When to Update Documentation

- Example 1: No docs (simple UI change)
- Example 2: Updated API docs (new endpoints)
- Example 3: Added pattern docs (reusable pattern)
- Example 4: Created follow-up ticket

## Tips for Success

1. **Trust the self-checks**: They catch issues early
2. **Don't skip simplification phases**: They improve code quality
3. **Use parallel execution carefully**: Only when boundaries are clear
4. **Stop when blocked**: The workflow is designed to help you ask for help
5. **Track state continuously**: Helps with long sessions and context

## Customizing for Your Project

See README.md for detailed customization instructions. Key areas:
- Tech stack patterns (Phase 4)
- Required skills (Critical Reminders)
- Testing approaches (Phase 5, 8)
- Documentation standards (Phase 10)
