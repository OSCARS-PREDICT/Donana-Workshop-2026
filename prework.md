---
layout: default
permalink: /prework/
title: "Before you travel"
eyebrow: "Pre-work · deadline [DATE]"
standfirst: "Three technical requirements, three admin forms, and one set of slides. The technical work is the part that cannot be done on the day."
---

## The technical requirements

Do these in order. Each one depends on the one before it.

### 1. A functional R workflow

<span class="chip">[DATE]</span>

Your own forecasting workflow, running end to end on your own machine, from input data through to forecast output.

**What "functional" means here**

- It runs to completion with a single command and no manual intervention.
- Its inputs are files or an API call, not objects sitting in your R session.
- It writes its output to disk in a documented format.
- Dependencies are declared, not assumed — a `renv.lock`, a `DESCRIPTION`, or at minimum a script that installs what it needs.

**What it does not need to be**

Elegant, fast, final, or scientifically finished. A rough workflow that runs is worth far more to us this month than a good one that doesn't.

<div class="note" markdown="1">
<span class="note__label">Start here</span>
Reference workflow and folder structure: **[LINK]**. If you fork that and swap in your own model, most of the work below is already done for you.
</div>

### 2. Containerised with Docker

<span class="chip">[DATE]</span>

We need every workflow to run the same way on someone else's machine and on shared infrastructure. That means a container.

**What we need to see**

- A `Dockerfile` at the root of your repository.
- An image that builds from scratch, on a clean machine, with no manual steps.
- Your workflow running inside that container and producing the same output as it does on your laptop.

**Starting point** — base image and template: **[LINK]**. We recommend building from the [rocker](https://rocker-project.org) R images rather than starting from bare Ubuntu.

Test it works:

```bash
docker build -t my-workflow .
docker run --rm -v "$(pwd)/output:/output" my-workflow
```

<div class="note note--warn" markdown="1">
<span class="note__label">Three things that catch people out</span>
**Admin rights.** Docker Desktop often needs administrator permission to install. If your institution locks down your laptop, start the IT request **now** — it can take weeks. Podman is an acceptable alternative if Docker is impossible; tell us if you go that route.

**Apple Silicon.** An image built on an M-series Mac will not run on our x86 runners unless you build for the right platform. Use `docker build --platform linux/amd64 ...` and check the [notes at LINK].

**Image size.** If your image is over [X] GB, come to the surgery. It usually means data is baked in that should be mounted instead.
</div>

### 3. Your first push to LWE via GitLab

<span class="chip">[DATE]</span>

LWE ([FULL NAME]) is where the shared infrastructure lives. Getting your first push through before you travel proves the plumbing works, so Day 2 is spent on integration rather than accounts and credentials.

**Steps**

1. Request an account at **[URL]**. <span class="chip">Allow [X] working days</span> — provisioning is not instant, so do this first, before you have anything to push.
2. Add an SSH key or a personal access token — [instructions at LINK].
3. Create a repository under the project group **[GROUP/NAMESPACE]**, named `[convention, e.g. wf-institution-shortname]`.
4. Push your containerised workflow: code, `Dockerfile`, dependency lockfile, and a `README.md` saying what it does, what it needs as input and what it produces.
5. Confirm the CI pipeline runs — even if it only builds the image at this stage.

**Done means:** your repository is visible under [GROUP], the pipeline has run at least once, and you can point at a build log.

## Checklist

<ul class="check">
<li>R workflow runs end to end with one command</li>
<li>Dependencies declared in a lockfile</li>
<li><code>Dockerfile</code> written and image builds from scratch</li>
<li>Workflow runs inside the container and writes output</li>
<li>Built for <code>linux/amd64</code> if you are on Apple Silicon</li>
<li>LWE account requested and active</li>
<li>SSH key or access token added</li>
<li>Repository created under [GROUP] and pushed</li>
<li>CI pipeline has run at least once</li>
<li>Laptop packed, along with its charger</li>
</ul>

## If you get stuck

Please do not go quiet. Two routes, both fine to use as often as you like:

- **Drop-in surgery** — [DAY] at [TIME] on [DATES], [LINK]. No agenda, no preparation. Bring whatever is broken.
- **Open an issue** at [LINK], or email [EMAIL].

The deadline is real, but telling us early costs you nothing.

## The other three things

### Three slides: "My workflow in 5 minutes"

<span class="chip chip--quiet">[DATE]</span> — upload to [LINK]

You will present these on Day 1. Five minutes, hard stop, three slides:

1. **What I run** — a diagram of the workflow
2. **What it takes as input** — data sources, formats, resolution, update frequency
3. **What it produces** — output format, units, uncertainty representation, how often

No motivation slides, no results, no institutional introduction. Everyone in the room already knows why ecological forecasting matters. If you have done requirements 1–3 above, these slides are mostly screenshots of work you have already done.

### Dietary, accessibility and room requirements

<span class="chip chip--quiet">[DATE]</span> — [FORM LINK]

State allergies explicitly and separately from preferences; the caterer needs to know the difference. Anything at all we should know about access, mobility, health or room arrangements goes here, and no explanation is required.

### Travel details

<span class="chip chip--quiet">[DATE]</span> — [FORM LINK]

Arrival time in [CITY], flight or train number, and a mobile number we can reach you on during travel day.
