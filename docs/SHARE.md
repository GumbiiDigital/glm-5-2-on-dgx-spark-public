# Share Copy

## Short post

I built a public-safe operations method for local GLM 5.2 serving: pin intent, keep inventory as data, dry-run first, and verify model identity, readiness, requests, process lifecycle, and teardown as separate gates.

## Thread-style post

**Opening**

Starting a process is not proof that a local model service works.

**The method**

I separate version intent, synthetic inventory, preflight, dry run, launch, verification, and teardown into distinct receipts.

**Why dry run matters**

It can prove that a plan resolves. It cannot prove a model loaded, participants joined, a request completed, or teardown was clean.

**The public version**

The inventory is fictional and uses documentation-only identities. There are no model files, cache paths, live endpoints, credentials, or benchmark claims.

**The lesson**

Dry-run success and live-serving success are different evidence tiers. I keep them separate.
