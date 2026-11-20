# CPM Exam Coach

A study tool for the AIPMM Certified Product Manager (CPM) exam. It's a single HTML file with no build step, no dependencies and no account. Open it in a browser and start practicing.

## What's in it

- **Learn:** concept summaries for all six exam domains, ordered by exam weight.
- **Practice quiz:** untimed questions with an explanation after each answer. Selection favors the topics you miss most. You can filter by domain and choose 10, 15, 25 or 40 questions.
- **Exam simulation:** a 30-question module (30 minutes) or the full 120-question exam (2 hours). Domain mix follows the real weights, the timer is strict, and you see no feedback until the end. The pass mark is 74%.
- **Flashcards:** flip cards with self-grading. Cards you mark as unknown come back more often.
- **Essay practice:** the real exam includes short essays, so this section gives you prompts, a model answer and a checklist of key points to grade yourself against.
- **Review misses:** every question you got wrong, collected in one place.
- **Dashboard:** accuracy by domain, a readiness estimate and your recent exam scores.
- **Voice:** optional read-aloud and voice answers, using your browser's built-in speech features.

The bank holds 300 questions, 82 flashcards and 18 essay prompts.

## Exam domains

| Domain | Weight |
| --- | --- |
| Product Lifecycle Management | 40% |
| Marketing Research, Business Plans & Documentation | 20% |
| Teams, People & Organizational Issues | 15% |
| New Product Development Methodology | 10% |
| Strategy | 10% |
| Tools & Measurements | 5% |

## Running it

Download `index.html` and open it in any modern browser. Or, to host it, turn on GitHub Pages for this repo (Settings → Pages → deploy from the main branch) and it will be served as is.

## Your progress

Progress is saved in your browser's local storage, so it stays put when you close and reopen the page. It doesn't sync, which means it won't follow you to another browser or computer, and clearing your browsing data erases it. Use **Back up progress** on the dashboard to save a JSON file, and **Restore backup** to load it again.

## Where the content comes from

Claude wrote every question for this tool, working from public study material and standard product management references. The wording won't match the real exam, so use official material to calibrate before test day. The sources are:

- A personal study guide compiled from AIPMM, Productside, Coursera, SkillUp, Udemy, Quizlet and SlideShare material
- The EmpowerPM 3-Day AIPMM CPM Prep Course outline
- Public exam details from [aipmm.com/cpm](https://aipmm.com/cpm) and [Productside](https://productside.com/aipmm-certification/)
- Frameworks from the product management canon, including Kotler, Porter, Ansoff, BCG, Moore, Rogers, Tuckman, McKinsey 7S, Lean Startup, the Scrum Guide and the Business Model Canvas

This isn't affiliated with or endorsed by AIPMM. The ProdBOK® Guide is the book the exam is written from, and you should work through it and the official practice exam as well.

## Adding questions

The question bank is a plain JavaScript array near the top of `index.html`. Each entry looks like this:

```js
{d:1, q:"Question text", c:["Option A","Option B","Option C","Option D"], a:1, x:"Explanation shown after answering."}
```

`d` is the domain number (1–6), `c` holds the four choices, and `a` is the index of the correct one (starting at 0). Flashcards and essay prompts follow similar patterns in the `FLASH` and `ESSAYS` arrays. New questions can be appended without affecting saved progress.
