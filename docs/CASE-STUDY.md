# Case Study: Dry Run Is a Separate Evidence Tier

## Context

Serving a large local model involves more than starting a process. The artifact, runtime, roles, lifecycle, and response all need independent verification.

## Problem

A dry run can prove that configuration resolves and that a plan is internally consistent. It cannot prove that a model loaded, that distributed participants joined, that requests completed, or that teardown was clean.

## What I built

The public operations method uses distinct receipts:

- intent records model and runtime versions;
- inventory contains synthetic roles only;
- preflight checks required inputs;
- dry_run resolves the proposed plan;
- launch is a separate, unclaimed stage;
- verify defines model, readiness, request, and lifecycle gates; and
- teardown defines process and partial-artifact checks.

## Engineering decisions

- Versions are explicit rather than implied by a moving latest tag.
- Inventory is data, not hard-coded shell text.
- Dry-run output cannot be promoted to a live result.
- Distributed roles use fictional names and documentation-only addresses.
- Acceptance requires both positive response checks and clean lifecycle checks.
- Public records omit cache paths and operational endpoints.

## Representative artifact

The synthetic serving plan contains a fictional inventory, pinned intent, dry-run state, and verification contract. It has no real command, model path, endpoint, or execution result.

## Evidence available here

- The plan parses as JSON.
- Every identity is synthetic.
- The document separates planned and observed states.
- The publication checker rejects common private-data patterns.
- CI runs the same checker.

## Lessons

The most important word in a dry-run report is dry. It is useful evidence, but only for plan resolution. Live serving requires a different receipt.

## Limitations

No model artifact, runtime test, distributed launch, response, benchmark, or teardown was executed for this public example.
