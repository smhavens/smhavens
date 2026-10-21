# Mila Havens | Software Engineer Portfolio

Software engineer with 3+ years of experience building data-driven applications, SQL Server databases, and secure APIs. I enjoy turning stakeholder requirements into reliable, well-documented code.

**Core skills:** Python · C# / .NET 8 · SQL (SQL Server, MySQL) · REST APIs · React · Java · Docker · AWS · Git · Power BI

[GitHub](https://github.com/smhavens) · [Website](https://havensmila.com) · [LinkedIn](https://www.linkedin.com/in/mila-havens/) · [Email](havenssydneym@gmail.com)

---

## About me

[2-3 sentences: your background, what kind of work you want next, and what you care about. For example: "I'm interested in building software that supports research and healthcare teams, especially data pipelines, APIs, and tools that make complex data easier to use."]

---

## Featured projects

### AnalogyArcade: NLP word-analogy game

| | |
|---|---|
| **Stack** | Python, Gradio, Hugging Face (Spaces, Transformers, sentence-transformers) |
| **Links** | [Live demo](https://huggingface.co/spaces/smhavens/AnalogyArcade) · [Code](https://github.com/smhavens/NLPCategoryGame) |
| **Type** | [Course project / personal project: fill in] |

**What it is:** A web game where the player fills in the blank of an analogy ("A is to B as C is to ___"). The system uses language models and word embeddings, so some of its prompts and answers get quite strange.

**What I built:**
- Fine-tuned a sentence-transformer (`all-MiniLM-L6-v2`) on about 2k analogy questions, then used a fill-mask pipeline to generate and check answers.
- Compared three approaches: the fine-tuned sentence-transformer, a word2vec model, and in-context prompting with Flan-T5.
- Evaluated them with 11 automated test prompts and a human ranking study (5 participants, 10 prompts).
- Deployed the app on Hugging Face Spaces and documented methods, results, and limitations in the README.

**What I learned:** Human raters ranked the sentence-transformer outputs best, even though none of the models did well on the automated tests. Small training datasets and limited vocabulary were the main bottlenecks. [Add one or two sentences on what you'd do next.]

---

### Minimal API event router

> ⚠️ **Check before publishing:** This was built for an employer's internal ERP. Confirm with your employer what you can share, and keep this write-up high-level. Remove anything proprietary, including system names, internal URLs, and screenshots.

| | |
|---|---|
| **Stack** | C#, .NET 8, Minimal API, JWT, SQL Server |
| **Type** | Professional work (code not public) |

**Problem:** [Describe the general problem, e.g., "Adding a new event to an enterprise app required building new endpoints each time."]

**Approach:**
- Designed a reusable event framework with clearly defined request and response contracts, so server-side handlers can plug in without new endpoints.
- Secured it with JWT access tokens, revocable refresh tokens tracked in a database table, and encrypted server-side secrets.

**Results:** Cut new-event development effort by about 25%. Adopted by 5+ modules.

[Optional: add a simple architecture diagram you draw yourself, not a copy of internal documentation.]

---

### AR virtual workstation

> ⚠️ **Check before publishing:** Confirm what you can share about this employer project. Avoid screenshots of company parts, models, or facilities.

| | |
|---|---|
| **Stack** | Unreal Engine 5 (Blueprints, C++), Meta XR SDK, Interaction SDK, Meta Quest 3 |
| **Type** | Professional work (code not public) |

**What it does:** An augmented reality workstation that converts IGES files to GLB at runtime from an ID number, so engineers can view, measure, delete, and compare 3D models with hand controls to check part integration before production.

**Highlights:** Models load in under 10 seconds, and up to 5 can be compared at once. [Add what you'd like people to know: design decisions, challenges, or what you learned.]

---

## Research and lab experience

**Augmented Reality Center, Oakland University** (2023-2025): [High-level summary only. For example: worked with industry partners on mixed reality demos, upgraded a KUKA robotics mixed reality system, ran Unreal Engine workshops, and presented at trade shows. Check with the lab director before adding photos, demos, or partner names.]

---

## Coursework and academic projects

Some university work can't be shared publicly, so I describe it here without the code. Code walkthroughs are available on request.

| Project | Topic | What I did | Code |
|---|---|---|---|
| [Project name] | [Topic] | [One-sentence summary of what you built and learned] | Available on request |
| [Project name] | [Topic] | [One-sentence summary] | Available on request |

---

## Currently building

- [ ] [New project idea: for example, a small full-stack app with a Python or .NET API, a SQL database, a React front end, Docker, tests, and a clear README]
- [ ] [Public-data project: for example, load an open health dataset into SQL, query it, and build a Power BI dashboard]

---

## Project write-up template

Copy this for each new project:

```markdown
### Project name

| | |
|---|---|
| **Stack** | |
| **Links** | Demo · Code (or "code not public") |
| **Type** | Personal / Course / Professional |

**Problem:** What problem does it solve and for whom?

**Approach:**
- Key design decision or feature
- How you tested or evaluated it

**Results:** Measurable outcomes or what you learned.

**Next steps:** What you'd improve.
```

---

## Contact

I'm open to software engineering roles, especially in data systems, back-end and API development, and healthcare or research technology. The best way to reach me is [Email](havenssydneym@gmail.com).
