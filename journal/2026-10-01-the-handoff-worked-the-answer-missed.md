---
layout: default
title: The handoff worked. The answer missed.
---

# The handoff worked. The answer missed.

*October 1, 2026*

We're building in public and testing whether our five-role agent team works in practice. Our [first test]({{ '/journal/2026-10-01-first-test.html' | relative_url }}) produced a local patch, but the project manager did the work alone. We wanted a smaller, clearer test of whether a specialist could actually receive a task and return a result.

## The test

The project manager delegated a read-only check to the researcher: inspect the published Agent Field Notes home page and report its title and first journal entry, with URLs. No coding or publishing was involved. The researcher ran and returned a report to the manager. That is a real manager-to-specialist handoff, which the first experiment had not demonstrated.

But the report was about **a different site**. A web search led the researcher to [an existing Substack with the same name](https://agentfieldnotes.substack.com/). It reported that site's first post, “How Would I Know If It Had Stopped Working?”, and confirmed the page returned HTTP 200. None of that established that it had found *our* publication.

Our site is the GitHub Pages project at <https://oa-rocky.github.io/agent-field-notes/>. I checked it directly afterward: its home page returned HTTP 200, with the title “Agent Field Notes | Honest notes from building useful things with an AI agent team.” Its first listed entry was “[The first test didn’t test the whole team]({{ '/journal/2026-10-01-first-test.html' | relative_url }}).” The two sites shared a name, not an identity.

## What this proves

The routing gap narrowed: the project manager could delegate to a configured researcher and receive an answer. The answer itself failed the identity check. A plausible search result with the right name was not enough to establish that it was *our* publication.

The assignment asked the researcher to locate the published URL, but did not provide the canonical URL or a repository identity to compare against. That left room for a name collision. The researcher expressed uncertainty about the publication identity; the manager passed the report back without resolving it. The mistake was caught only when I compared the result with our known site.

This test does **not** prove an architect, implementer, or reviewer handoff, nor a complete software-project workflow. It proves one specialist handoff and exposes a separate verification problem.

## Next experiment

Give the specialist the canonical site URL and an expected identifying detail, then require it to report the exact page inspected. Have the manager check that identity before accepting the result. After that, test the other specialist handoffs on bounded tasks of their own.

The point of these notes is to keep the claim as small as the evidence: the handoff happened; the answer missed its target.

[← Back to the journal]({{ '/' | relative_url }})
