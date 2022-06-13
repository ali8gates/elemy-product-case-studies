# Case Study: Building the Data Capability

Joined as employee number twelve, as the first technical product manager, with no data function to inherit. This is the part of the work that made the other case studies measurable.

## The problem nobody asks for help with

At a company growing from a dozen people to more than 1,200, every team builds the data it needs to do its own job. Admissions counts a family one way, clinical counts them another, finance counts a third way, and each definition is correct inside its own system.

That is survivable until the company tries to make a decision that crosses those boundaries. Cost to acquire a family is exactly that kind of decision. It touches marketing, admissions, scheduling, and clinical delivery. If those four teams cannot agree on what a family is or when one counts as acquired, the number is unusable and the arguments never end.

The onboarding automation program was justified on that number. So it had to exist and it had to be defensible.

## What I built

**Definitions for the core entities.** Family, prospective family, enrolled family, therapist, availability record, session, care plan. Each with one owner, one definition, and one system of record. Boring work with an outsized effect, because most cross-team disagreement is a definitional disagreement wearing a costume.

**A governance model that fit a startup.** Heavyweight governance dies at this stage of company. What worked was narrow: a named owner per entity, a written definition, a change process for altering one, and a rule that new systems adopt the existing definition rather than inventing a local variant. That is enough to prevent drift without adding a committee.

**Funnel instrumentation.** Events at each onboarding step, so drop off was a number instead of a story from whoever last talked to a family. This is what made it possible to say availability collection cost 25 minutes per family and to prove what changed when it did not.

**A data platform the team could actually run.** Standard pipelines, a shared place for the tables, and reporting built on the certified entities instead of on whatever extract a team had lying around.

## The scaling constraint

The reason to do this at twelve people rather than at 300 is that entity definitions are cheap to establish and expensive to retrofit. Every month you wait, another system encodes another local definition of a family, and unwinding it later means touching production code owned by teams who have no reason to care.

The company grew past 1,200 employees. The definitions held. That is the entire return on the work.

## Team

I hired and scaled the group that carried this, growing to roughly 40 to 50 people with 12 direct reports. Two things I would tell anyone doing it:

- Hire the first data engineer before you think you need one. The window where a founding definition can be set cleanly is short.
- Make the entity owner a person, not a team. Shared ownership of a definition means nobody defends it during the argument that matters.

## What it enabled

- Cost per acquired family became a number the whole company used the same way.
- Funnel drop off became visible per step, which is what let the onboarding program be sequenced by cost rather than by opinion.
- The availability work could be evaluated on real outcomes: hours offered, insufficient submissions, follow up contacts, and whether schedules were buildable afterward.
- Reporting stopped being reconciliation work. Teams argued about what to do rather than about whose spreadsheet was right.

## The honest part

Not all of it held. Some definitions got worked around under delivery pressure, usually by a team shipping against a deadline, and the fix was always slower than the shortcut. The governance model was strong enough to catch drift after it happened and too light to prevent it. At that stage of company that was probably the right trade, but it was a trade, not a win.
