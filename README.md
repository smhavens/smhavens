# Mila Havens | Software Engineer Portfolio

Software engineer with 3+ years of experience building data-driven applications, SQL Server databases, and secure APIs. I enjoy turning stakeholder requirements into reliable, well-documented code.

**Core skills:** Python · C# / .NET 8 · SQL (SQL Server, MySQL) · REST APIs · React · Java · Docker · AWS · Git · Power BI

[GitHub](https://github.com/smhavens) · [Website](https://havensmila.com) · [LinkedIn](https://www.linkedin.com/in/mila-havens/) · [Email](mailto:havenssydneym@gmail.com)

---

## About me

Software engineer with experience in data systems, backend APIs, and XR. I’m looking for roles building software for healthcare and research teams.

---

## Projects at a glance

| Project | What it shows | Stack | Code |
|---|---|---|---|
| [Insta485: full-stack photo-sharing app](#insta485-full-stack-photo-sharing-app) | SQL schema design, REST API, React front end | Python, Flask, SQLite, React, pytest | On request |
| [Distributed MapReduce framework](#distributed-mapreduce-framework) | Distributed systems, fault tolerance, sockets, threading | Python, TCP/UDP, threads | On request |
| [Hadoop inverted-index pipeline](#hadoop-inverted-index-pipeline-search-engine) | Data processing pipelines | Python, Hadoop Streaming, SQL | On request |
| [Mutation testing and fuzzing](#mutation-testing-and-fuzzing-a-python-calculator) | Test quality and automated testing | Python, unittest, MutPy, Atheris |
| [AnalogyArcade](#analogyarcade-nlp-word-game) | ML model evaluation, deployment, documentation | Python, Gradio, Hugging Face | [Public](https://github.com/smhavens/NLPCategoryGame) |
| [Personal Cookbook](#personal-cookbook-desktop-app) | Requirements, design, and testing across a full project lifecycle | Python, PyQt5, pandas | [Public](https://github.com/smhavens/CSI5220) |
| [Interesting-Co (Rememri)](#interesting-co-rememri-android-ar-app) | Mobile front end, API integration, teamwork | Android, Mapbox, ARCore, Flask, Firebase | [Public wiki](https://github.com/michigan224/Interesting-Co/wiki) |
| [MiniOS](#minios-operating-system-simulation) | Systems programming, processes, signals, scheduling | C, Linux | On request |

---

## Full-stack and data projects

### Insta485: full-stack photo-sharing app

| | |
|---|---|
| **Stack** | Python, Flask, SQLite, Jinja, React, pytest |
| **Type** | University course project (University of Michigan) |
| **Code** | Not public. Walkthrough available on request. |

**What it is:** An Instagram-style web app where users post photos, follow each other, like, and comment.

**What I built:**
- A relational SQLite schema with five related tables (users, posts, following, comments, likes) and cascading deletes.
- Server-rendered pages for login, account management, posts, user profiles, followers and following, and an explore page.
- A versioned REST API (`/api/v1`) for posts, likes, and comments, with session and HTTP basic authentication and JSON error handling.
- A React front end with infinite scrolling, like and unlike, and comment add and delete, all calling the REST API.
- Salted SHA-512 password hashing and verification.
- About 2,000 lines of Python and JavaScript in total.

**What I'd improve today:** upgrade the old dependency versions, replace SHA-512 with a modern password hashing library such as bcrypt or argon2, add TypeScript and a CI pipeline.

---

### Distributed MapReduce framework

| | |
|---|---|
| **Stack** | Python, TCP and UDP sockets, threads, subprocesses |
| **Type** | University course project (University of Michigan) |
| **Code** | Not public. Walkthrough available on request. |

**What it is:** A small distributed MapReduce framework with a Manager that coordinates jobs and Workers that run map and reduce programs, plus a job submission client.

**Provided by the course:** The project skeleton, which included the job submission client, a utilities module, example socket and thread scripts, the test suite, and empty Manager and Worker classes (under 50 lines each, marked "IMPLEMENT ME").

**What I built:** The Manager (about 760 lines) and the Worker (about 250 lines), including:
- Worker registration and acknowledgment over TCP, with JSON messages for tasks and status.
- A job queue and a task queue, so the Manager runs one job at a time and holds the next ones.
- Partitioning of input files across mappers, then a group-and-sort stage and a reduce stage. The Manager merges sorted worker output with `heapq.merge`.
- UDP heartbeats from each Worker, and a Manager thread that marks any worker dead after about 10 seconds without one.
- Workers that run the user-supplied map, group, and reduce programs as subprocesses.
- Clean shutdown handling across the Manager and its Workers.

---

### Hadoop inverted-index pipeline (search engine)

| | |
|---|---|
| **Stack** | Python, Hadoop Streaming (MapReduce), SQLite, Flask |
| **Type** | University course project (University of Michigan) |
| **Code** | Not public. Walkthrough available on request. |

**What it is:** The data pipeline behind a small Wikipedia search engine: a chain of MapReduce jobs that processes document data into an inverted index, plus ranking data and a SQL database of article metadata for the search server.

**Highlights:**
- A chained pipeline of Hadoop Streaming jobs (a document-count job followed by indexing jobs), each written as a Python mapper and reducer.
- A pipeline script that runs the jobs in order, passing each job's output to the next.

---

### Mutation testing and fuzzing a Python calculator

| | |
|---|---|
| **Stack** | Python, unittest, MutPy (mutation testing), Atheris (fuzzing) |
| **Type** | University software testing project (University of Michigan) |
| **Code** | Not public. Walkthrough available on request. |

**What I did:**
- Wrote a unit test suite of 27 test cases for a calculator module (arithmetic, powers, roots, LCM and HCF, factorials, and trigonometry), including edge cases such as division by zero, negative inputs, and large numbers.
- Ran mutation testing with MutPy on a small vector and matrix library. The initial mutation score was 60.4% (159 mutants) when an untested transformations module was included, and 78.7% on the library alone (122 mutants).
- Wrote new tests to kill surviving mutants, such as an invalid-operand test, which raised the score to 79.5% and the passing test count from 22 to 25.
- Found unused functions through the mutation analysis, and recommended removing them for readability.
- Added an Atheris fuzzing harness, which found an uncaught exception (a ValueError for the tangent of 90 degrees) that the handwritten tests had missed.

---

### AnalogyArcade: NLP word game

| | |
|---|---|
| **Stack** | Python, Gradio, Hugging Face (Spaces, Transformers, sentence-transformers) |
| **Links** | [Live demo](https://huggingface.co/spaces/smhavens/AnalogyArcade) · [Code](https://github.com/smhavens/NLPCategoryGame) |
| **Type** | University NLP implementation project (Oakland University) |

**What it is:** A web game where the player fills in the blank of an analogy ("A is to B as C is to ___"). The system uses language models and word embeddings, so some of its prompts and answers get quite strange.

**What I built:**
- Fine-tuned a sentence-transformer (`all-MiniLM-L6-v2`) on about 2k analogy questions, then used a fill-mask pipeline to generate and check answers.
- Compared three approaches: the fine-tuned sentence-transformer, a word2vec model, and in-context prompting with Flan-T5.
- Evaluated them with 11 automated test prompts and a human ranking study (5 participants, 10 prompts).
- Deployed the app on Hugging Face Spaces and documented the methods, results, and limitations.

**What I learned:** Human raters ranked the sentence-transformer outputs best, even though none of the models did well on the automated tests. Small training data and limited vocabulary were the main bottlenecks.

---

## Team and application projects

### Personal Cookbook (desktop app)

| | |
|---|---|
| **Stack** | Python, PyQt5, pandas |
| **Links** | [Code and final write-up](https://github.com/smhavens/CSI5220) |
| **Type** | University software project course, team project (Oakland University) |
| **My role** | Documentation, Class and Function implementation, Database |

**What it is:** A desktop app for building a personal recipe library and pantry. Users can add, edit, and remove recipes and pantry items, publish recipes to a shared library, search recipes by ingredient, plan meals, and generate a shopping list from what's missing in their pantry. The project is about 3,200 lines of Python across 24 Python files.

**Highlights:** The write-up (52 pages) covers the full lifecycle: a proposal and problem statement, a budget estimate, a Gantt chart and dependency diagram, use cases and use-case descriptions, class and sequence diagrams, coding and testing, and system test cases per screen.

---

### Interesting-Co (Rememri): Android AR app

| | |
|---|---|
| **Stack** | Android, Mapbox, ARCore, Flask REST API, Firebase, Google Cloud Run, JWT |
| **Links** | [Project wiki](https://github.com/michigan224/Interesting-Co/wiki) · [Repository](https://github.com/michigan224/Interesting-Co) |
| **Type** | University mobile development course, team of 6 (2022) |

**What it is:** A location-based Android app where users drop image "pins" on a map and view them in augmented reality, with friends and comments. The backend is a Flask API on Google Cloud Run backed by Firebase.

**My contribution (from the team roster):**
- Programmed front-end features and designed many of the app's views and list items.
- Connected the app to the backend with API requests, populating list views such as friend requests and comments.
- Built the sign-in views and functions.
- Passed pin data between views so each pin showed the correct image and all its comments.

---

### MiniOS: operating system simulation

| | |
|---|---|
| **Stack** | C, Linux (fork, signals, shared memory) |
| **Type** | University operating systems course project (Oakland University) |
| **Code** | Not public. Walkthrough available on request. |

**What it is:** A simulated operating system with an interactive shell that creates, lists, kills, and resumes processes and schedules them with First Come First Serve or Round Robin policies (with a configurable time quantum).

**Highlights:**
- Process states (Ready, Running, Suspended, Terminated) with a documented state-transition diagram.
- Signal handling for interrupts (Ctrl-C) and alarm-driven scheduling.
- A limit on concurrent processes for safe debugging.
- Documented commands and behavior in a README.

---

## Currently building

- [ ] Public Health data explorer using Python, SQL, and PowerBI.
- [ ] Patient Records REST API using Synthea data.

---

## Contact

I'm open to software engineering roles, especially in data systems, back-end and API development, and healthcare or research technology. The best way to reach me is [Email](mailto:havenssydneym@gmail.com).
