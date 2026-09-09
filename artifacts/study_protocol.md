# Think-Aloud Study Protocol: Differential Privacy Library Usability

This document details the standardized study protocol used across all 22 think-aloud programming sessions in our research on developer interactions with Differential Privacy libraries (IBM DiffPrivLib, PyDP, and OpenDP).

---

## 1. Pre-Session Setup

- **Environment**: Containerized Python 3.10 environment pre-installed with `diffprivlib`, `pydp`, and `opendp`.
- **Dataset**: UCI Adult dataset (`adult.csv`) pre-loaded in the local workspace directory.
- **Bookmarks**: Official documentation bookmarked for all 3 target libraries.
- **Recording**: Full screen capture and high-quality audio recording configured.
- **Consent**: IRB-approved consent form and demographic screening questionnaire prepared.

---

## 2. Session Introduction (5–10 minutes)

### Facilitator Script:
> "Thank you for participating in this study. We are interested in understanding how developers use Differential Privacy libraries in practice. Today, you will work on two data analysis tasks using one or more Differential Privacy libraries.
>
> I want you to think aloud as you work—verbalize your thoughts, questions, and decisions as you would if you were explaining your process to a colleague. There are no right or wrong answers; we are interested in your natural approach to solving these problems.
>
> You can use any resources you normally would: documentation, online search, Stack Overflow, AI coding assistants if that is your normal workflow. Feel free to ask me clarifying questions, but I won't guide your implementation decisions.
>
> The session will be audio and screen recorded for analysis. All data will be anonymized. Do you have any questions before we begin?"

---

## 3. Demographic Questionnaire (5 minutes)

Participants complete a brief pre-study survey collecting:
1. Years of Python programming experience.
2. Years of data science / data engineering experience.
3. Prior experience with Differential Privacy (Novice, Intermediate, Experienced).
4. Familiarity with specific target libraries (DiffPrivLib, PyDP, OpenDP).
5. Primary professional role, sector (Industry / Academia), and region.

---

## 4. Task Instructions (50–60 minutes per task)

### Task A (Counting Query):
> "Your first task is to calculate the number of individuals in the dataset earning more than $50,000 per year using Differential Privacy with $\varepsilon = 1.0$.
>
> You can start with any of the three libraries we've discussed: IBM DiffPrivLib, PyDP, or OpenDP. You're expected to complete the tasks using all three libraries, using one at a time, in the order indicated on your handout. The dataset is already loaded in the session directory as `adult.csv`.
>
> Please think aloud as you work, and let me know when you've completed the task or if you have questions."

### Task B (Grouped Aggregation):
> "Your second task is to calculate the average age of individuals for each unique education level, ensuring Differential Privacy.
>
> Again, you can start with any of the three libraries you prefer (in the order on your handout). Think aloud as you work through this problem."

---

## 5. Facilitation Guidelines

- **Clarification requests**: Answer questions regarding task specifications or dataset schema. Do not suggest API calls or parameter choices.
- **Technical prompts**: If participants ask "How do I do X in this library?", respond with: "What would you normally check or try next?"
- **Error handling**: Allow participants to debug independently. Only intervene if stuck for >5 minutes without progress due to system/environment issues.
- **Time limits**: Maximum 60 minutes per task per library.
- **AI Assistant usage**: Participants may use LLM assistants to summarize docs or check syntax, but may not ask LLMs to generate full task solutions.

---

## 6. Observer Documentation Protocol

The secondary observer logs real-time timestamps and notes for:
- Initial entry points and documentation search queries.
- Encountered runtime error messages and user reactions.
- Verbalized confusion, uncertainty, or privacy mis-perceptions.
- Improvised workarounds (e.g., dropping to low-level mechanisms, writing manual loops over groups, external filtering in pandas).
- AI assistant prompts and evaluation of generated snippets.

---

## 7. Session Conclusion & Debrief (5 minutes)

### Post-Task Interview Questions:
1. Which library or libraries did you find easiest to use, and why?
2. What was the most challenging aspect of completing these tasks?
3. Did you feel confident that your implementations were correct and privacy-preserving?
4. Is there anything you would have done differently if this were a real production project?

---

## 8. Post-Session Data Processing & Anonymization

1. Recordings backed up to access-controlled storage.
2. Audio transcribed and de-identified (names, affiliations, and incidental personal details redacted).
3. Participant IDs assigned (`P1`–`P22`).
4. Final executed code artifacts collected and de-identified.
