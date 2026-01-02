# Self-Verifying Task Runner (JavaScript)

A system designed around one rule:  
**execution and judgment must never be the same thing.**

One part acts.  
Another part observes.  
Truth lives in the distance between them.

---

## Core Idea

Tasks do not prove they work by running.  
They prove they work by **surviving inspection**.

Each task declares what it promises *before* execution.  
After execution, it is judged only on whether reality matches that promise.

There are three distinct roles:

- **Actor** — performs the work
- **Observer** — evaluates the outcome
- **Controller** — applies constrained responses

No role overlaps.  
No role negotiates.

---

## Actor

The Actor exists to execute, not to reflect.

Its responsibilities are limited to:
- Running a task
- Capturing what happened
- Reporting facts exactly as they occurred

The Actor does not:
- Decide success or failure
- Apply fixes
- Interpret meaning

It produces raw evidence and stops.

---

## Observer

The Observer never runs tasks.

It consumes reports from the Actor and compares them against:
- Declared contracts
- Invariants and constraints
- Historical baselines

Judgment is deterministic.
If the rules say it failed, it failed.
Intent is irrelevant.

The Observer outputs a verdict:
- Pass
- Degraded
- Fail

Along with reasons and severity.

---

## Contracts

A contract defines the boundaries of acceptable behavior.

It answers:
- What must be true for success
- What must never happen
- What limits cannot be crossed

Contracts are immutable during execution.  
Verification always uses the same contract that detected the failure.

A fix that changes the definition of success is invalid.

---

## Controller

The Controller is not creative.

It reacts to Observer verdicts using **pre-approved actions**:
- Retry
- Roll back
- Disable
- Escalate

No free-form fixes.
No silent recovery.

Every action is followed by re-evaluation.

---

## Verification Loop

Correction does not end the process.

After any intervention:
1. The Actor executes again
2. The Observer re-applies the same rules

If the failure persists, the system rejects the intervention.

A state is only considered stable if it can be re-proven as stable.

---

## Separation by Time

The Actor operates in the present moment.
The Observer may operate across time.

This enables detection of:
- Performance drift
- Repeated instability
- Behavioral regression

Short-term action and long-term judgment remain isolated.

---

## Failure Philosophy

Failure is not an exception.
Failure is information.

The system does not attempt to look correct.
It attempts to **know** whether it is correct.

---

## Foundational Rule

**If the Observer cannot prove it works, it does not work.**

This rule is non-negotiable.
