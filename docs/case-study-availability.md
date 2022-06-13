# Case Study: Availability Capture

A deep dive into the hardest piece of a program to automate family onboarding. Worked on and off across nine months, from late 2021 through 2022.

## Why this piece mattered

Automating onboarding was one of the largest company initiatives of the year, and the goal was blunt: cut the cost of acquiring each new family. Most onboarding steps were straightforward to convert into self service. Collecting a family's weekly availability was not.

Availability did two jobs at once:

1. It told us whether the family was a fit, since therapy requires a real block of weekly hours.
2. It let the therapist search start immediately instead of after another round of phone tag.

Agents were calling every family to gather this by hand. That cost 25 minutes of phone time per family, including the many families who never enrolled. It was the single most expensive conversation in the funnel and the one least suited to a phone call, because parents do not have their week memorized.

## My role

I led the family-facing product experience. Across this initiative I oversaw the work of six designers and writers contributing to family-facing products. On this specific piece I did the research, shipped the first version, formed the hypothesis for the second, and stayed accountable for the strategy through delivery.

- At the start I worked alone, because the team was one person.
- By the last stage the team had grown. I supervised an associate who owned delivery of the final designs and partnered with a visual designer on iconography, while I stayed responsible for the direction and the outcome.

## Research, run before there was a research function

The first researcher had not been hired yet and this project was visibly coming. So I ran the interviews myself, with parents and caregivers seeking pediatric autism therapy, focused on one question: how do they actually think about their week and the time they can give to therapy.

Inside my first 60 days I planned and ran the study, delivered the insights, ran an ideation workshop off the questions that came out of it, and put three concepts on the table.

The finding that changed the product: **availability is not binary.** There is time that is truly free, time that is feasible with effort, and time that is technically open but would cost the family something. A form asking for available hours only ever captures the first category. Several families gave nothing but their ideal schedule.

That reframed the problem. It was not "build a scheduling form." It was "how do we get families to offer more of their week than the part they think of as free."

## Shipping the version I did not want

After the research I got pulled onto other work through the end of the year. When I came back, engineering had capacity to build an availability form almost immediately, and the request was for something extremely simple in the older design system so the backend could start storing time per family. Iterate later.

Not ideal. Also the right call, and I understood why. Without a place to store family time, nothing downstream could be built at all. So I took the pieces of research that mattered most and built a simple version, in under a week, that did not disrupt existing operations processes.

Three decisions carried over from the research:

**Do not overload immediately.** Time selection stayed off the default screen so a caregiver could read and absorb the instructions before every field appeared at once.

**Motivate more availability.** Language was written to make offering more time feel worth doing, rather than framing it as a requirement to satisfy.

**Keep the rules simple.** Operations wanted a longer list of validation rules. I pushed back on most of them. With less than a week to design and test, there was no way to convey a complex rule set to a family without making the experience worse than the phone call it replaced.

What landed was a 15 hour weekly minimum with a soft push toward business hours.

**On not over-emphasizing the minimum.** Fifteen hours sounds like a lot to a family hearing it for the first time, so the expectation had to be set. But once a family accepts the number, a prominent counter turns into a stopping point. They hit 15 and stop, when the clinical recommendation is often 25 to 30. So the minimum appeared as a quiet note at the bottom of the page rather than a progress counter reading "14 of 15 hours added."

## The hypothesis

Building that quick version is what produced the real insight. The stronger solution would collect **buckets of time** (mornings, after school, evenings) instead of specific intervals.

Three reasons:

- Lighter mental load at a point in the funnel where the family is already carrying a lot.
- It matches what research found. Availability is not black and white, and buckets let a family express feasible rather than only ideal.
- It gives operations room to propose a schedule slightly wider than what the family volunteered. Closer to how a salary negotiation works than to a calendar invite.

## Testing it before it was needed

I knew the next iteration could arrive with no warning, so I ran a fast concept test with families who had already given availability in earlier studies. Two questions:

1. Filling out the new bucket-based form, would they offer more time than before?
2. If we came back with a schedule containing times they had not originally listed, would they accept it?

Yes to both.

That is the whole reason the second version shipped quickly when it was finally prioritized. The evidence was already in hand.

## What brought it back to the top of the roadmap

A few months after the first version launched without buckets, operations came back with the problem I expected. They were following up by phone with families who had given insufficient availability, because the simple rule set let too many thin submissions through.

That created a real tradeoff. More validation rules make the experience worse for a brand new family. But we could trade a more complex set of rules for a simpler time entry model by switching to buckets. Complexity moved from the family into the system.

By this point I was managing designers, so I worked through one of them on delivery and stayed accountable for the approach.

## The design decision I would defend hardest

Validation runs after submit, not while the family is typing.

Families given a live checklist fill it to the minimum and stop. So all the requirements stayed hidden. The family enters what they can, hits submit, and only if the submission falls short do we start coaching them through what is missing. It behaves like a password strength check: quiet until it needs to say something.

This looks like a small interaction choice. It is the reason the hours went up.

## Results

- Collecting availability no longer required any phone time. It previously took 25 minutes per prospective family.
- Admissions ran with 20 fewer operations agents by the end of the year, across the wider onboarding automation program.
- The quantity of available hours per family increased after time buckets were introduced.
- The quality held. There were no significant obstacles scheduling families for therapy later in the funnel, which was the real test. More hours would have meant nothing if they had not been schedulable.

## What I would do differently

- Push harder for a data model that supported buckets in the first version. The backend shape we shipped fast became a constraint on the second version, and the expansion from buckets to intervals cost more than it needed to.
- Instrument the first version more heavily before launch. I had to reconstruct where families were stopping from operations feedback rather than reading it directly.
- Write down the rule tradeoff with operations at the start. We relitigated the same rule debate twice because the first decision lived in my head instead of in a document.
