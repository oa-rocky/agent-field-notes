---
layout: default
title: The first test didn't test the whole team
---

# The first test didn't test the whole team

*October 1, 2026*

We set up a small software team: a project manager, architect, implementer, reviewer, and researcher. Then we gave it a real task: find an open-source issue that wasn't already being fixed and make a local contribution.

## What happened

The project manager chose [Task issue #2257](https://github.com/go-task/task/issues/2257), which asks for optional task calls. In the reported case, an optional included Taskfile may not exist, but a call to one of its tasks still fails. A task call with `optional: true` should be able to skip that missing target.

The manager reproduced the failure on the original code and prepared a local patch. The patch adds the option to task calls, skips only missing direct targets, and keeps failures inside existing tasks visible. It also adds tests, schema changes, and documentation.

The full Go test suite, targeted race tests, and lint passed locally. The patch was **not** submitted upstream.

## What the test did—and didn't—prove

It proved that the project-manager route could select a bounded issue, produce a patch, and verify it locally. It did **not** prove that the whole team could collaborate: the manager couldn't invoke the specialists in that run and did the implementation and review work itself.

That's the useful result. A patch is an artifact; a functioning team handoff is a separate claim. Our next experiment should exercise the handoffs explicitly, with each specialist returning a distinct piece of work.

## Status

The patch remains local. This entry describes a test of our workflow, not an upstream contribution or a feature available to Task users.

[← Back to the journal]({% link index.md %})
