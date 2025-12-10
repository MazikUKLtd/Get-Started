# Examples Guide

This guide walks you through each example file and how to use it with GitHub Copilot. Start with Exercise 1 and work your way through—each builds on skills from the previous one.

## File Structure

```
examples/
├── js/
│   ├── hello.js                 (Exercise 1)
│   └── phone-validator.js       (Exercise 2)
├── python/
│   ├── factorial.py             (Exercise 3)
│   └── factorial_test.py        (Exercise 3 - tests)
├── typescript/
│   ├── merge-sorted-arrays.ts   (Exercise 4 & 5)
│   └── merge-sorted-arrays.test.ts (Exercise 5 - tests)
└── GUIDE.md                     (this file)
```

---

## Exercise 1: Accept a Suggestion

**File:** `js/hello.js`

**Goal:** Learn how to accept a Copilot suggestion.

**Steps:**
1. Open `js/hello.js` in VS Code
2. Place your cursor after the comment `// returns true if input is palindrome`
3. Press Enter to go to a new line
4. Copilot should suggest a function. You'll see a greyed-out suggestion.
5. Press **Tab** or **Enter** to accept it, or **Escape** to dismiss it.
6. Try typing the first few characters (`function` or `const`) to trigger suggestions manually.

**Expected outcome:** A working palindrome checker function.

**Tips:**
- If no suggestion appears, press `Ctrl+Alt+\` (or `Cmd+Alt+\` on Mac) to trigger Copilot manually.
- Review the suggestion before accepting—does it make sense?

---

## Exercise 2: Prompt-Driven Generation

**File:** `js/phone-validator.js`

**Goal:** Use a detailed comment to guide code generation.

**Steps:**
1. Open `js/phone-validator.js`
2. The file has a detailed prompt already: `/* Create a function that validates UK phone numbers and includes unit tests */`
3. Go to the next line and let Copilot suggest the implementation
4. Accept the suggestion and review it
5. Run the code: `node js/phone-validator.js` (if tests are included)
6. If the output isn't what you wanted, modify the comment and re-prompt

**Refining your prompt:**
- Too vague? Add constraints: `/* Validate UK phone numbers in format +44... or 0... with proper error messages */`
- Want specific tests? Add them: `/* Include tests for: valid numbers, invalid formats, edge cases */`

**Tips:**
- More specific prompts = better results
- Include format details, edge cases, and expected behavior in comments
- Test the generated code before moving on

---

## Exercise 3: Turn Comments into Tests

**Files:** `python/factorial.py` and `python/factorial_test.py`

**Goal:** Generate a function, then generate matching tests.

**Steps:**
1. Open `python/factorial.py`
2. The comment says `# Compute factorial` — let Copilot complete the function
3. Accept the suggestion and review the implementation
4. Open `python/factorial_test.py`
5. Add a comment: `# Test cases for the factorial function including edge cases`
6. Let Copilot generate test cases using pytest
7. Run tests: `pytest python/factorial_test.py -v`
8. If tests fail, edit the function or refine the test prompt

**Expected outcome:** A factorial function and a set of passing tests.

**Tips:**
- If Copilot's tests don't import the function, add the import statement manually and re-prompt
- Common edge cases: 0!, negative numbers, non-integers
- Use `pytest` output to guide fixes

---

## Exercise 4 & 5: Multi-File Task (TypeScript)

**Files:** `typescript/merge-sorted-arrays.ts` and `typescript/merge-sorted-arrays.test.ts`

**Goal:** Create a feature spanning multiple files with implementation and tests.

**Steps:**
1. Open `typescript/merge-sorted-arrays.ts`
2. The comment says `// Write a TypeScript function that merges two sorted arrays`
3. Let Copilot suggest the function, then accept it
4. Add type hints if Copilot didn't: `function mergeSortedArrays(arr1: number[], arr2: number[]): number[] { ... }`
5. Open `typescript/merge-sorted-arrays.test.ts`
6. Add a comment: `// Comprehensive tests for mergeSortedArrays including edge cases and performance`
7. Let Copilot generate tests (using Jest or similar)
8. Run tests (see setup instructions below)

**Setup (optional):**
```bash
npm install --save-dev jest @types/jest ts-jest typescript
npx jest
```

**Expected outcome:** A working merge function and passing tests.

**Tips:**
- TypeScript's type system helps Copilot understand your intent
- Specify edge cases in comments: `// Handle empty arrays, single elements, duplicates`
- Use descriptive test names to guide generation

---

## General Tips for All Exercises

### Getting Better Suggestions

1. **Add context** – Include types, examples, or edge cases in comments
2. **Break it down** – Write smaller functions; Copilot suggests better for short tasks
3. **Be specific** – "validate email" is vague; "validate email format using regex with error messages" is better
4. **Show, don't tell** – Add example inputs/outputs in comments

### If Suggestions Aren't Good

- Press `Ctrl+Enter` (or use Copilot Chat) to see multiple suggestions
- Rewrite the comment with more detail
- Add a few lines of code manually, then re-prompt
- Check that your file is saved (unsaved files may affect context)

### Testing Generated Code

- Always run the code before accepting it
- Look for syntax errors, logical issues, or missing imports
- Edit and re-run; Copilot adapts to your changes
- Use debugger breakpoints to step through complex logic

### Iterating on Code

- Small edits + re-prompt = better results
- If a function is 80% correct, edit the remaining 20% manually
- Don't be afraid to reject suggestions and try again

---

## Next Steps

- Try combining exercises (e.g., write a palindrome validator with tests)
- Create your own files with similar prompts to practice
- Use Copilot Chat (`Ctrl+Shift+I` in VS Code) for multi-turn conversations about code
- Check the main [README.md](../README.md) for best practices and troubleshooting

Happy coding! 🚀
