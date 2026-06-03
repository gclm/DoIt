```markdown
# DoIt Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill provides guidance on contributing to the DoIt TypeScript codebase. It covers established coding conventions, dependency management workflows, and testing patterns. By following these patterns, contributors can ensure consistency and maintainability across the project.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `taskManager.ts`, `userProfile.test.ts`

### Import Style
- Use **relative imports** for modules within the project.
  - Example:
    ```typescript
    import { getUser } from './userService';
    ```

### Export Style
- Use **named exports** rather than default exports.
  - Example:
    ```typescript
    // userService.ts
    export function getUser(id: string) { /* ... */ }
    export function createUser(data: UserData) { /* ... */ }
    ```

### Commit Messages
- Use mixed commit types, often with the `chore` prefix for maintenance tasks.
- Keep commit messages concise (average ~70 characters).
  - Example: `chore: bump lodash from 4.17.20 to 4.17.21`

## Workflows

### Dependency Update and Merge
**Trigger:** When a dependency needs to be updated to a newer version  
**Command:** `/update-dependency`

1. Update the dependency version in the relevant files:
    - `package.json`
    - `package-lock.json`
    - `flake.lock` (if applicable)
2. Commit the changes with a message indicating the dependency bump.
    - Example: `chore: bump typescript from 4.5.2 to 4.6.0`
3. Open a pull request for the update.
4. After review, merge the pull request into the main branch.

## Testing Patterns

- Test files follow the `*.test.*` naming convention.
  - Example: `taskManager.test.ts`
- The specific testing framework is not detected, but tests are colocated with source files or in the same directory.
- Example test file structure:
    ```typescript
    // taskManager.test.ts
    import { addTask } from './taskManager';

    describe('addTask', () => {
      it('should add a new task', () => {
        // test implementation
      });
    });
    ```

## Commands

| Command            | Purpose                                             |
|--------------------|-----------------------------------------------------|
| /update-dependency | Update a dependency and merge the change to main    |
```
