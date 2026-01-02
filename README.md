# Self-Verifying Task Runner (JavaScript)

A two-system project where **one part acts** and **another observes, verifies, and corrects**.  
Simple in scope. Strict in logic. No pretending things are fine when they aren’t.

---

## Core Idea

You build a small runtime where tasks **declare what they promise**, then get judged on whether they kept that promise.

- **Actor** runs the task.
- **Observer** evaluates the result.
- **Controller** decides what happens next.

No task fixes itself.  
No observer improvises.  
Everything is verified using the same rules that detected the failure.

---

## Architecture

### 1. Task (The Actor’s Unit of Work)

Each task is a function plus a contract.

```js
export const task = {
  name: "sumNumbers",
  contract: {
    maxTimeMs: 100,
    outputType: "number",
    noThrow: true
  },
  run(input) {
    return input.a + input.b
  }
}
