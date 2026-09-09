# PoPETS-differential-privacy-dataset

This repository contains the complete open research artifacts, task briefings, study materials, and 22 de-identified think-aloud session transcripts collected and analyzed for the PoPETs 2027 paper titled:
**"Working around rather than using it as intended: A think-aloud study of Differential Privacy library usability"**

**Authors:** Ravi Kiran Mahankali and Gretchen Hallett (*University of Bristol*)  
**Venue:** Proceedings on Privacy Enhancing Technologies (PoPETs), Volume 2027

---

## Abstract

Differential Privacy guarantees privacy-preserving data analysis, yet adoption remains limited. We conducted a think-aloud study with 22 Python developers of varied experience—they attempted two standard Differential Privacy analytics tasks across IBM DiffPrivLib, PyDP, and OpenDP. We found developers resorted to undocumented workarounds—using low-level mechanisms directly, manually implementing functionality the library should provide, or relying on external tools for basic operations—as high-level APIs failed to address common use cases; suggesting a fundamental gap between how libraries are designed and how developers actually intend to use them. Our primary contribution is an empirically grounded taxonomy of workaround strategies: alternative procedures that developers improvise when intended library workflows do not fit their task. We trace these recurring workaround strategies each to specific, Differential Privacy-relevant library design and documentation gaps. We suggest actionable recommendations for library maintainers seeking to make Differential Privacy usable without forcing developers into privacy-compromising solution patterns.

### Citation

Please cite this work as follows:

```bibtex
@article{mahankali2027working,
  author    = {Mahankali, Ravi Kiran and Hallett, Gretchen},
  title     = {Working around rather than using it as intended: A think-aloud study of Differential Privacy library usability},
  journal   = {Proceedings on Privacy Enhancing Technologies},
  volume    = {2027},
  year      = {2027}
}
```

---

## Research Overview

Despite the growing importance of embedding privacy-preserving analytics into data science workflows, operationalizing Differential Privacy (DP) remains challenging for software practitioners. Differential Privacy libraries—such as IBM DiffPrivLib, PyDP, and OpenDP—seek to democratize access to DP mechanisms. However, gaps between high-level DataFrame abstractions and low-level DP mechanism requirements frequently force developers off-script.

When intended library workflows fail to fit developers' everyday programming idioms, developers improvise alternative procedures ("workarounds"). In Differential Privacy, workaround behavior is particularly consequential: bypassing high-level abstractions, deriving data bounds without budget tracking, or manually re-implementing composition can silently undermine formal privacy guarantees.

To investigate how developers interact with open-source Differential Privacy libraries during active implementation, our study addresses three primary research questions:

* **RQ1:** What usability challenges do developers encounter when using Differential Privacy libraries for common data analysis tasks?
* **RQ2:** How do these usability challenges differ across Differential Privacy libraries with different design philosophies (function-first, mechanism-first, pipeline-oriented)?
* **RQ3:** When library workflows break down, what kinds of undocumented workarounds do developers adopt, and which DP-library factors trigger them?

---

## Study Methodology & Protocol

We conducted concurrent think-aloud programming sessions with 22 Python developers ($P1$ – $P22$) spanning three experience tiers (Novice, Intermediate, Experienced). Participants performed two foundational data analytics tasks using the UCI Adult dataset (`adult.csv`):

1. **Task A (Counting Query):** Calculate the number of individuals in the dataset earning more than $50,000 per year using Differential Privacy with &#949; = 1.0.
2. **Task B (Grouped Aggregation):** Calculate the average age of individuals for each unique education level in the dataset, ensuring Differential Privacy across group estimates.

### Standardized Protocol Structure

The protocol was executed across 8 structured phases:
- **A.1 Pre-Session Setup:** Standardized Python 3.10 virtual environment with pre-installed libraries (DiffPrivLib, PyDP, OpenDP), pre-loaded dataset (`adult.csv`), and documentation bookmarks.
- **A.2 Session Introduction (5–10 min):** Facilitator script introducing the think-aloud protocol and consent parameters.
- **A.3 Demographic Questionnaire (5 min):** Assessing Python experience, Data Science experience, prior DP exposure, and development tools.
- **A.4 Task Introduction (5 min):** Task briefings for Task A (&#949; = 1.0) and Task B (grouped mean age).
- **A.5 Facilitation Guidelines:** Non-interventional prompts, 5-minute debugging rule, and 60-minute time-boxing.
- **A.6 Observer Documentation:** Real-time logging of timestamps, error messages, documentation searches, workaround attempts, and AI assistant invocations.
- **A.7 Session Conclusion (5 min):** Debrief interview evaluating library ease-of-use, major hurdles, correctness confidence, and real-world preferences.
- **A.8 Post-Session Processing:** Secure backup, verbatim audio transcription, complete de-identification ($P1$ – $P22$), and qualitative coding.

---

## Allowed Resources & AI Assistant Policy

Participants were permitted to use their standard development resources:
- Official library documentation and API references.
- General web search engines and Q&A sites (Stack Overflow).
- **AI Coding Assistants & LLMs** (e.g., GitHub Copilot, ChatGPT) under explicit protocol constraints: AI assistants could be used to summarize complex documentation passages, check syntax, or explore isolated API primitives; however, participants were prohibited from prompting AI assistants to generate end-to-end task solutions.

---

## Repository & Dataset Structure

This repository contains the following de-identified research artifacts:

```
artifacts/
├── README.md                           # Master artifact documentation (this file)
├── Participant_Screening.pdf           # Participant Screening questionnaire for the study    
├── Participant_Info_Sheet.pdf          # Participant Information Sheet provided to subjects
├── Consent_Form.pdf                    # Informed Consent Form signed by subjects
├── Task_Briefing.pdf                   # Task briefing sheet provided to participants
├── Server_Connect_Details_DP.pdf       # Technical remote environment specification
├── study_protocol.md                   # Full 8-stage study protocol (Appendix A)
├── coding_scheme.csv                   # 72 thematic codes, definitions, quotes, and counts (Appendix C)
├── participant_demographics.csv        # Demographic breakdown for participants P1–P22 (Table 1)
├── workaround_mapping.md               # Mapping of workaround categories to missing library features
│── developer_transcripts/              # Participant anonymized transcripts (P1–P22)
|── ├── Developer_Studies_P1.txt
|   ├── Developer_Studies_P2.txt
|   └── ... (P1 through P22)
└── developer_codebooks/                # Participant codebooks (P1–P22)
    ├── codebook_Usability_Studies_P1.csv
    ├── codebook_Usability_Studies_P2.csv
    └── ... (P1 through P22)
```

---

## Participant Demographics Summary ($n=22$)

| PID | Primary Role | Region | Py. Yrs | DS Yrs | DP Experience | Sector Context |
|:---|:---|:---:|:---:|:---:|:---|:---|
| P1  | Data Engineer      | UK    | 5  | 1  | Novice        | Industry |
| P2  | Data Engineer      | US    | 10 | 4  | Intermediate  | Industry |
| P3  | Data Analyst       | US    | 6  | 2  | Novice        | Industry |
| P4  | Postdoc Researcher | UK    | 9  | 6  | Intermediate  | Academia |
| P5  | ML Engineer        | India | 5  | 2  | Novice        | Industry |
| P6  | Research Fellow    | UK    | 14 | 3  | Intermediate  | Academia |
| P7  | Software Engineer  | US    | 8  | 5  | Novice        | Industry |
| P8  | DP Specialist      | US    | 10 | 7  | Experienced   | Industry |
| P9  | PhD Student        | UK    | 6  | 4  | Novice        | Academia |
| P10 | Lead Data Engineer | US    | 15 | 12 | Intermediate  | Industry |
| P11 | Research Assistant | UK    | 11 | 6  | Novice        | Academia |
| P12 | Senior Developer   | India | 7  | 5  | Intermediate  | Industry |
| P13 | Applied Scientist  | US    | 12 | 9  | Experienced   | Academia |
| P14 | Data Analyst       | US    | 5  | 3  | Novice        | Industry |
| P15 | Assistant Prof.    | UK    | 13 | 9  | Intermediate  | Academia |
| P16 | Privacy Engineer   | US    | 15 | 13 | Experienced   | Industry |
| P17 | ML Engineer        | India | 6  | 4  | Novice        | Industry |
| P18 | Postdoc Researcher | UK    | 9  | 6  | Intermediate  | Academia |
| P19 | PhD Student        | US    | 8  | 5  | Novice        | Academia |
| P20 | Principal Engineer | US    | 11 | 9  | Experienced   | Industry |
| P21 | Software Developer | India | 6  | 3  | Novice        | Industry |
| P22 | Data Architect     | India | 15 | 12 | Experienced   | Industry |

---

## Statement on Participant Privacy & Open Data Release

Per our institution's Research Ethics Committee approval (University of Bristol REC protocols) and participant informed consent agreements:
- **Raw audio/video recordings are NOT released** to protect participant confidentiality and prevent re-identification via voice signatures or workspace video.
- All transcripts, code snippets, survey answers, and observer logs released in this repository have been **fully anonymized** (pseudonyms $P1$ – $P22$, all institutional and personal identifiers redacted).

---

## License

All research data and documentation artifacts in this repository are released under the [Creative Commons Attribution 4.0 International License (CC-BY 4.0)](https://creativecommons.org/licenses/by/4.0/).
