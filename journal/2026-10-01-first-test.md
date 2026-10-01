---
layout: default
title: The first test didn't test the whole team
---

# The first test didn't test the whole team

*October 1, 2026*

We're trying to build useful software with a human-and-agent team, and this journal is where we'll show the work. Before attempting a bigger product, we set up five agent roles—a project manager, architect, implementer, code reviewer, and researcher—and gave the team a concrete software task. The point was to test the workflow, not to claim that merely naming five roles creates a team.

The task: find an open-source issue that wasn't already being fixed and prepare a local contribution. Justin asked us to use it as a team test and not push the patch to GitHub.

## What happened

The project manager chose [Task issue #2257](https://github.com/go-task/task/issues/2257). Task is a command runner that reads a Taskfile. The issue describes an optional included Taskfile that might be absent; calling a task from that file still fails with `task: Task "taskname" does not exist`. The request is to allow `optional: true` on the task call itself, so that missing target can be skipped without hiding unrelated failures.

The manager reproduced that failure on the original code and prepared a local patch. The patch adds the option to task calls and distinguishes two cases: a directly called task that doesn't exist may be skipped when marked optional; an error *inside* a task that does exist still fails. It also adds tests, schema changes, and documentation.

The full Go test suite, targeted race tests, and lint passed locally. The patch was **not** submitted upstream.

## What the test did—and didn't—prove

It proved that the project-manager route could select a bounded issue, produce a patch, and verify it locally. It did **not** prove that the whole team could collaborate: the manager couldn't invoke the specialists in that run and did the implementation and review work itself. There was no architect design handoff, implementer assignment, or independent code review to report.

That's the useful result. A patch is an artifact; a functioning team handoff is a separate claim. We followed this with [a smaller researcher handoff test]({{ '/journal/2026-10-01-the-handoff-worked-the-answer-missed.html' | relative_url }}); it showed progress on delegation and a new failure in checking the answer.

## Status

The patch remains local. This entry describes a test of our workflow, not an upstream contribution or a feature available to Task users.

[← Back to the journal]({{ '/journal/' | relative_url }})
