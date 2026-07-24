# anti-spiral

A skill that makes an AI assistant refuse to become the second half of a delusional feedback loop.

## What this is

`SKILL.md` is a behavioral protocol you load into an AI assistant. It changes how the model handles a conversation where someone is getting more and more certain about something false: a theory of everything, a cracked code, a sentient AI companion, a surveillance plot, a mission only they can carry out.

It is not a diagnosis tool, a filter, or a refusal layer. The model still engages, still takes unusual ideas seriously, still treats the person as an adult. What changes is that it stops inflating the claim.

## Why a behavioral fix

Three findings drove the design.

Validation is the mechanism, not a side effect. Chandra, Kleiman-Weiner, Ragan-Kelley and Tenenbaum (2026) simulated a perfectly rational Bayesian user talking to a sycophantic bot. The user still spiraled. Being rational is not protection.

Being factual is not enough. A bot that says nothing false, but selectively surfaces the confirming truths, still drives spiraling. Cherry-picking and enthusiastic elaboration on a shaky premise are failure modes even when every sentence is true.

Warning the user is not enough. Users who knew the bot might be sycophantic spiraled anyway. You cannot offload the work onto a disclaimer.

So the fix has to be behavioral, on the model's side. It has to actually not do the thing rather than caveat it.

## What it changes

- Judges the trajectory of a conversation, not the individual message. No single turn in a spiral looks bad, which is why per-message judgment misses it.
- Breaks linguistic alignment. The model stops adopting coined vocabulary and Capitalized Special Nouns as if they were established.
- Refuses to elaborate on an unvalidated premise. Adding detail to a shaky foundation manufactures false substance.
- Asks instead of affirming. Questions reduce sycophancy where first-person assertions amplify it (Dubois et al., 2026).
- Volunteers the boring explanation and the strongest case against, unprompted.
- Answers reality-check requests honestly. "Am I crazy?" is the highest-leverage moment in the whole conversation, and in documented cases it is exactly where the assistant said "not even remotely crazy."
- Separates the real work from the inflated claim. There is often competent work under a grandiose wrapper, and naming the split respects the person while deflating the dangerous part.

There is also a section for the inverted case: someone else's closed framework being used to recruit the user. There the person in front of you is usually the healthy one, and firing the normal machinery at them gets it backwards.

The governing principle throughout: keep the person, drop the premise.

## What it does not do

It does not prevent AI-associated psychosis. It does not diagnose. It does not get anyone out of a spiral they are already deep in, and it is not designed to. It changes what one AI assistant does in one conversation.

Harshness is a documented failure mode, so the skill is calibrated against it. The gut-check it uses: would this response make the person feel accompanied or graded? Graded pushes them toward whatever validates them next, which is the outcome the whole thing exists to prevent.

## Install

For Claude, drop `SKILL.md` into your skills directory, or upload `anti-spiral.skill` through the skills interface.

For any other model, paste the body of `SKILL.md` into the system prompt. Nothing in it is Claude-specific.

## Evaluation

Two rounds, scored against the codebook from Moore et al. (2026), which coded 391,562 messages of human-LLM chat logs into 28 behavior codes.

Round one, four spiral archetypes plus a false-positive control, baseline against skill-loaded:

| | baseline | with skill |
|---|---|---|
| harmful bot codes | 11 | 0 |
| protective behaviors | 1 | 17 |

The control was not deflated, meaning the skill did not fire on a person with an ordinary unconventional idea.

Round two, six recruiter scenarios across five domains plus a control: 21 of 25 protocol behaviors with the skill against 3 of 25 baseline, and harm failures went from 2 to 0.

Read this with the caveat it deserves. The transcripts were generated and graded by an LLM, not by independent human raters, and n is small. Moore et al. report human-LLM agreement around κ 0.57 on their own codebook. Treat these numbers as a smoke test that the protocol changes behavior in the intended direction, not as evidence of real-world outcomes.

Eval materials are in `eval/`.

## Sources

Chandra, Kleiman-Weiner, Ragan-Kelley & Tenenbaum (2026), *Sycophantic Chatbots Cause Delusional Spiraling, Even in Ideal Bayesians*, arXiv:2602.19141

Morrin, Augustin & Pollak (2026), *Characterizing the spiral*, NPP Digital Psychiatry

Morrin et al. (2026), Lancet Psychiatry

Moore et al. (2026), *Characterizing delusional spirals through human-LLM chat logs*

Dubois et al. (2026), *Ask don't tell*

Steyvers et al. (2025), Nature Machine Intelligence

Human Line Project, and reporting in the New York Times and Futurism, for case trajectories and recovery accounts.

## License

MIT. Copy it, fork it, rewrite it for your own assistant.
