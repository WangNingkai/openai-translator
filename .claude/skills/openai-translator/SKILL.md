```markdown
# openai-translator Development Patterns

> Auto-generated skill from repository analysis

## Overview
This skill introduces the core development patterns and conventions used in the `openai-translator` TypeScript codebase. It covers file organization, code style, commit practices, and testing patterns, providing practical examples and suggested commands for efficient collaboration and contribution.

## Coding Conventions

### File Naming
- Use **camelCase** for file names.
  - Example: `openaiTranslator.ts`, `apiClient.ts`

### Import Style
- Both default and named imports are used. Prefer named imports for clarity.
  - Example:
    ```typescript
    import { translateText, detectLanguage } from './openaiTranslator';
    import apiClient from './apiClient';
    ```

### Export Style
- Use **named exports** for all modules.
  - Example:
    ```typescript
    // openaiTranslator.ts
    export function translateText(text: string, targetLang: string): Promise<string> { ... }
    export function detectLanguage(text: string): string { ... }
    ```

### Commit Message Conventions
- Follow **Conventional Commits** with the `feat` prefix for features.
  - Example:
    ```
    feat: add support for batch translation in apiClient (75 chars)
    ```

## Workflows

### Adding a New Feature
**Trigger:** When implementing a new functionality or feature.
**Command:** `/add-feature`

1. Create a new TypeScript file using camelCase naming.
2. Write your feature logic, using named exports.
3. Import necessary dependencies using named or default imports.
4. Add or update corresponding test files (`*.test.*`).
5. Commit your changes using the conventional commit format with `feat` prefix.
6. Submit a pull request for review.

### Running Tests
**Trigger:** When validating code changes or before submitting a pull request.
**Command:** `/run-tests`

1. Identify test files matching the `*.test.*` pattern.
2. Use the project's test runner (framework unknown; check project docs or package.json).
3. Run all tests and ensure they pass.
4. Address any failing tests before committing.

## Testing Patterns

- Test files follow the `*.test.*` naming pattern (e.g., `openaiTranslator.test.ts`).
- The specific testing framework is not detected; check the project documentation or `package.json` for details.
- Write tests in separate files alongside or near the implementation files.
- Example test file:
  ```typescript
  // openaiTranslator.test.ts
  import { translateText } from './openaiTranslator';

  test('translates text to Spanish', async () => {
    const result = await translateText('Hello', 'es');
    expect(result).toBe('Hola');
  });
  ```

## Commands
| Command        | Purpose                                      |
|----------------|----------------------------------------------|
| /add-feature   | Start the workflow for adding a new feature  |
| /run-tests     | Run all tests in the codebase                |
```