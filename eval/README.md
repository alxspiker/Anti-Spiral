# Evaluation materials

What is here, and what it is worth.

## Files

`transcripts.md` — four spiral archetypes plus one false-positive control. The control is a person with an ordinary unconventional idea, included to check the skill does not fire on everyone unusual.

`responses.md` — assistant responses to those transcripts, baseline and skill-loaded.

`score.py` — scores the responses against the Moore et al. (2026) codebook. Counts harmful bot codes and protective behaviors.

`recruiter_transcripts.md` — six scenarios where another person's closed framework is used to recruit the user, across physics, spiritual, crypto, political and health domains, against both steady and shaken targets. Plus a control where a real collaborator gives fair criticism, to check the skill does not misread honest pushback as recruitment.

`recruiter_responses.md` — baseline and skill-loaded responses to those.

`score_recruiter.py` — scores protocol behaviors and harm failures.

`live-test-gemini.md` — the three-turn scenario used for the live cross-model run against Gemini, with the exact prompts and what each turn tests. Not scored against the codebook; read and compared by hand.

## Results

Round one: 11 harmful bot codes at baseline, 0 with the skill. Protective behaviors went from 1 to 17. The control was not deflated.

Round two: 3 of 25 protocol behaviors at baseline, 21 of 25 with the skill. Harm failures went from 2 to 0. The control was correctly not treated as a recruiter.

The largest effect was on shaken targets. Scenario R5, the health-domain recruiter, is the one to watch: the skill names the reframe without endorsing any protocol and routes to a clinician, which is the intended behavior, but it is the case where getting it wrong would matter most.

## What this evidence is not

The transcripts were written by an LLM and the responses were graded by an LLM, the same one that wrote the skill. There were no independent human raters. Moore et al. report human-LLM agreement around κ 0.57 on their own codebook, so even a careful automated grader disagrees with humans often.

n is small. The scenarios are synthetic. Nobody in real distress was involved.

Read this as a smoke test showing the protocol changes model behavior in the intended direction. It is not evidence about outcomes for real people. If you want to run a better version of this, independent human grading and a larger scenario set are the two things missing.
