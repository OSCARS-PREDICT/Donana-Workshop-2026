---
layout: default
permalink: /working-practices/
title: "How we work"
eyebrow: "Where things live - during and after the workshop"
standfirst: "One canonical home, one note template, and every action carrying an owner and a date. This is the difference between a good three days and a good three days that changes nothing."
---

## One home, not five

The commonest way a project like ours falls apart is due to 'tool sprawl': notes in a document, decisions in chat, actions in someone's notebook, code somewhere else. By November, nobody knows where the truth is.
That is not how we want to run things in PREDICT. Here is the structure we will aim to follow for the workshop and beyond:

| Layer | Where | Rule |
|---|---|---|
| **Canonical record** — decisions, roadmap, specs, meeting synthesis | >>[Our chosen repo location TBC ./docs], in version control | If it isn't here, it didn't happen |
| **Actions and blockers** | Issues on >>[Our chosen open-source tracker TBC], one board | Every action is an issue with an owner and a due date |
| **Live notes during sessions** | One pad per session, >>[Link TBC] | Migrated into the group repo within 24 hours |
| **Chat** | [https://chat.lifewatch.dev/] | **Not a record.** Anything decided in our chat spaces gets converted to an issue that is trackable |
| **Slides, photos, large files** | >>[Our chosen shared drive location TBC] | Linked from our chosen repo/location, never the only copy |

## During the workshop

**Every session has a rapporteur**, named on the final agenda in advance so nobody is ambushed. The role rotates so no one misses two sessions in a row.

**One note template, used everywhere.** The discussion and the nuance are welcome but optional; these four headings are to keep us on track.

```
SESSION:                                   Date/time:
Owner:               Rapporteur:

DECISIONS   (settled — full sentences, no shorthand)
ACTIONS     (each needs an owner and a date, or it is not an action)
OPEN        (unresolved — who resolves it, and by when)
BLOCKERS    (someone cannot proceed until X)
```

**Fifteen minutes at the end of each day.** Rapporteurs paste their notes into the repo, the decisions and actions are read aloud, and the room confirms or corrects them. That confirmation is what makes an action binding.

**Everything on a wall gets photographed** before it comes down after Friday lunchtime, Emma to digitise and share. The PREDICT pipeline wall, the roadmap/timeline and the pre-mortem clusters are the best material, and not to be lost!

## In the week(s) afterwards

(Did you know, momentum from an in-person meeting has a half-life of about ten days?)

| When | What |
|---|---|
| +2 working days | Every action converted into a tracker issue with an owner, a due date and a subgroup label. Ideally this is done by the end of the workshop itself. |
| +5 working days | Each of you gets a three-line follow up email listing only your own actions and dates to confirm |
| +7 working days | Feedback survey results shared around |
| +10 working days | **The synthesis document circulated** — decisions made, roadmap, subgroup charters, action list, risks highlighted, wall photos. Four pages max |
| +15 working days | Every subgroup has held its first meeting |


## The suggested rhythm for the remaining 18 months

- **Sub-group meetings** — fortnightly, 45 minutes, self-organised. Same agenda every time: progress against milestones, blockers, next action.
- **All-hands** — monthly, 60 minutes. Not a round of status updates; those are read in advance from the tracker. One subgroup shares something genuinely unresolved, then blockers are shared.
- **LWE Integration clinic** — monthly, 60 minutes, optional, drop-in. No agenda. Bring a broken pipeline and someone helps (Emma & LWE).
- **Quarterly checkpoint** — ~2hrs, online led by Maria. Roadmap reviewed against reality, milestones re-dated honestly, risks revisited. Four of these before the project ends, all four in the calendar from Day 3.
- **One more in-person meeting** at roughly the nine-month mark — agreed at this workshop and booked in.
- **The final Brussels meeting** booked in at the next in-person meeting, date TBC at the end of the project life cycle.

## Two numbers we will report at every all-hands meeting

**Milestones delivered against milestones planned**, and **the number and status of partner components/ workflows successfully integrated**. 

## Good ideas that are not for now

They should go in `parked.md` in the shared notes repo, with one line saying why and the date. Revisited at each quarterly checkpoint. This is how we say "not now" without losing the idea.
