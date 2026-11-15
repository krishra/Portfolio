# Portfolio site plan

Status: draft, 14 Nov 2026. Owner: Krishnan Raghupathi.

## Goal

Replace the outdated resume site at krishnanraghupathi.com with a portfolio site where recruiters and hiring managers can read the essentials at a glance and ask an AI assistant questions about Krishnan's work. Over time it grows into a place where a hiring team can learn about him in depth before interviews start.

Inspiration: https://jordannedyck.com/

## Why build it

- **It is a shipped AI product.** A working, evaluated assistant on a personal domain is direct evidence of building with generative AI.
- **It demonstrates product craft.** Eval criteria, a test set and a launch bar for the assistant are the same skills used on production AI features, shown in the open.
- **It gives interested readers depth.** A resume is one page. The site can answer follow-up questions the resume has no room for.

## Principles

1. **The page works without the chat.** Most visitors spend well under a minute. Headline results, resume downloads and contact details are visible without typing anything. The assistant is for readers who want to dig.
2. **The assistant answers only from an approved fact base.** When it does not know, it says so and points to Krishnan. It never guesses.
3. **Nothing confidential goes in.** The fact base holds only material that is fine to publish. The list of excluded topics is kept outside this repository.
4. **It is framed as a portfolio.** The site describes work and results; it does not announce a job search.
5. **Costs stay small.** Free-tier hosting, no database, and a hard spending cap on the AI service.

## Risks and how the plan handles them

| Risk | Mitigation |
|---|---|
| The assistant states something wrong about Krishnan | Answers grounded in the fact base only; visible notice that it can be wrong; a "talk to the human" link; eval set run before every content change |
| Confidential or off-limits detail leaks | Fact base reviewed line by line before launch; excluded topics tested in the eval set |
| Abuse, prompt injection or runaway cost | Rate limit per visitor, message length limit, spending cap, no tools or outside data for the assistant |
| Visitors' chat logs | A stated retention period, shown next to the chat |
| Recruiters never use the chat | Static page carries the core message on its own; suggested questions lower the effort to try it |

## Architecture (first version)

- **Front end:** one static page (HTML, CSS, a little JavaScript), styled to match the resumes.
- **Ask feature:** one small server function that receives a question, adds the fact base and instructions, calls an AI model and streams the answer back.
- **Fact base:** a single Markdown file in this repo. It is short enough to send whole with every question, so there is no search index or vector database.
- **Hosting:** a free-tier static host with serverless functions. The domain is repointed from the current WordPress site at launch.

Choices still open: host, AI model and provider, and where chat logs are stored.

## Phases

| # | Phase | Output | Done when |
|---|---|---|---|
| 1 | Fact base | `content/facts.md`: roles, results, stories, suggested questions | Krishnan has approved every line |
| 2 | PRD | `docs/PRD.md` filled in | Requirements for function, usability, design and latency are agreed |
| 3 | Static page | Headline, proof points, resume downloads, contact | Reads well on phone and desktop with the chat switched off |
| 4 | Ask feature | Server function, chat UI, suggested questions, notices | Answers stream, limits and spending cap work |
| 5 | Evals | About 40 test questions with pass criteria, including hostile ones | Pass rate meets the bar set in the PRD |
| 6 | Launch | Domain repointed; link added to LinkedIn and the resume header | Site is live on krishnanraghupathi.com |
| 7 | Later | Case studies, a "how I built this" page, review of what visitors ask | Ongoing |

## Who does what

- **Claude:** drafts content, writes and tests the code, builds the eval set, writes deployment steps.
- **Krishnan:** approves the fact base and PRD, owns the accounts (domain, host, AI API key), repoints the domain, signs off the eval results.

## Open questions

1. Which topics should the assistant decline to discuss? (Kept outside this repo.)
2. Where is the domain registered, and which host will serve the new site?
3. Which AI model and provider, and what monthly spending cap?
4. How long are chat logs kept, and where?
