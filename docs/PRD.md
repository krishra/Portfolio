# Portfolio site PRD

Status: stub, to be filled in by Krishnan. See [PLAN.md](PLAN.md) for the plan this supports.

Each section lists prompts to answer. Delete the prompts as you fill them in.

## 1. Overview

- What is this product, in two or three sentences?
- What problem does it solve, and for whom?

## 2. Goals and non-goals

- Goals: what must be true for this to count as a success?
- Non-goals: what is deliberately out of scope for the first version?
- Success measures: which numbers will you watch (visits, questions asked, resume downloads, contacts)?

## 3. Users and scenarios

- Recruiter with 30 seconds: what must they see?
- Hiring manager preparing for an interview: what do they want to ask?
- Anyone else (peers, founders, press)?

## 4. Functional requirements

### 4.1 Static page

- Sections and their order
- Resume downloads (which variants)
- Contact options

### 4.2 Ask feature

- What visitors can ask, and suggested questions
- What the assistant must decline, and what it says when it declines
- Conversation length and message length limits
- Hand-off to a human ("talk to the human")

### 4.3 Content and grounding

- Source of truth for answers
- How content is updated and who approves changes

## 5. Usability

- First-visit experience: what happens in the first five seconds?
- Mobile and desktop expectations
- Accessibility requirements (keyboard use, screen readers, contrast, reduced motion)
- Error and empty states (model unavailable, rate limit reached)

## 6. Design

- Visual direction and tone
- Typography and colour (match the resumes?)
- Voice of the assistant (first person or third person, formality)

## 7. Performance and latency

- Page load target
- Time to first word of an answer
- Time to complete a typical answer
- Behaviour when the target is missed

## 8. Quality bar for the assistant

- Eval set size and categories (factual, behavioural, off-limits, hostile)
- Pass criteria per category
- Minimum pass rate to launch, and to ship a content change

## 9. Safety, privacy and abuse

- Topics that are off-limits (reference only; keep the list outside this repo)
- Chat log retention and what visitors are told
- Rate limits and spending cap
- Prompt injection and misuse handling

## 10. Analytics

- What is measured, and with what tool
- What is not collected

## 11. Cost

- Monthly budget and hard cap
- What happens when the cap is reached

## 12. Launch criteria

- Checklist that must be complete before the domain is repointed

## 13. Open questions

-
