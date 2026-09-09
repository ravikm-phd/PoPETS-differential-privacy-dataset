# Artifact Appendix

Paper title: **Working around rather than using it as intended: A think-aloud study of Differential Privacy library usability**

Requested Badge(s):
  - [X] **Available**

---

## Description

This artifact repository accompanies the PoPETs 2027 research paper titled:
**"Working around rather than using it as intended: A think-aloud study of Differential Privacy library usability"**

- **Authors:** Ravi Kiran Mahankali and Gretchen Hallett (*University of Bristol*)
- **Venue:** Proceedings on Privacy Enhancing Technologies (PoPETs), Volume 2027
- **BibTeX Citation:**

```bibtex
@article{mahankali2027working,
  author    = {Mahankali, Ravi Kiran and Hallett, Gretchen},
  title     = {Working around rather than using it as intended: A think-aloud study of Differential Privacy library usability},
  journal   = {Proceedings on Privacy Enhancing Technologies},
  volume    = {2027},
  year      = {2027}
}
```

### Artifact Overview

The repository contains the complete open research dataset, study protocol, task briefings, qualitative coding schema, and de-identified transcripts collected during our think-aloud study with 22 Python developers ($P1$ – $P22$). Specifically, the artifact includes:

1. **Think-Aloud Transcripts (`artifacts/developer_transcripts/`):** 22 verbatim, fully de-identified transcripts (`Developer_Studies_P1.txt` through `Developer_Studies_P22.txt`) documenting developers' real-time interactions, verbalized intent, confusion, and workaround strategies across IBM DiffPrivLib, PyDP, and OpenDP.
2. **Participant Code Artifacts (`artifacts/developer_codebooks/`):** 22 codebooks representing participants' think-aloud quotes/comments mapped to the codes identified for this study.
3. **Codebook (`artifacts/coding_scheme.csv`):** The complete 72-code scheme organized into 15 axial categories (2,984 total coded instances), including definitions and representative quotes.
4. **Workaround Taxonomy Mapping (`artifacts/workaround_mapping.md`):** Mapping of 412 workaround instances across 5 workaround strategies to specific library-side design triggers and DP-specific safety failure modes.
5. **Participant Demographics Dataset (`artifacts/participant_demographics.csv`):** Complete demographic breakdown ($n=22$) detailing Python experience, Data Science experience, DP experience tier (Novice, Intermediate, Experienced), primary role, region, and sector context.
6. **Study Protocol (`artifacts/study_protocol.md`):** Full 8-stage study protocol, task briefings (Task A and Task B), participant info sheet, consent form, and server environment setup documentation.
7. 
---

### Security/Privacy Issues and Ethical Concerns

#### Ethical Approval & IRB Process
The study protocol, consent procedures, data collection practices, and participant compensation were reviewed and approved by the **University of Bristol Research Ethics Committee** prior to participant recruitment.

#### Informed Consent & Participant Compensation
All 22 participants provided written informed consent prior to participating. Participants were informed that the study evaluated library usability rather than their individual programming skills, that participation was voluntary, and that they could withdraw at any time. Each participant was compensated approximately $150 USD for their time (for a 2–2.5 hour session), in accordance with institutional ethics guidelines.

#### Data De-identification & Privacy Protection
To protect participant confidentiality and prevent re-identification:
- **Raw audio and screen video recordings are NOT released** to protect participant confidentiality and prevent re-identification via voice signatures or workspace video.
- All released transcripts, code snippets, survey answers, and observer logs have undergone rigorous **de-identification**: participants are identified solely by pseudonyms ($P1$ – $P22$), and all institutional, personal, or geographical identifiers spoken during sessions have been redacted.

#### Security & System Risks
This artifact presents no security, system, or machine risks. It does not execute malware, disable firewalls/ASLR, or run vulnerable binaries. All evaluation code operates on standard open-source Python libraries (`diffprivlib`, `pydp`, `opendp`, `pandas`, `numpy`) operating on the public, anonymized UCI Adult dataset.

---

## Environment

### Accessibility

The artifact repository is publicly accessible via Zenodo under a persistent DOI URL:
- **Zenodo DOI:** [https://doi.org/10.5281/zenodo.22552503](https://doi.org/10.5281/zenodo.22552503)
- **License:** All research data and documentation artifacts in this repository are released under the [Creative Commons Attribution 4.0 International License (CC-BY 4.0)](https://creativecommons.org/licenses/by/4.0/).

---

## Notes on Reusability

This artifact provides reusable infrastructure for future empirical research on developer security and usable privacy:
- **Study Protocol (`artifacts/study_protocol.md`):** The 8-phase concurrent think-aloud protocol can be directly adapted for usability evaluations of other privacy-enhancing technologies (e.g., Homomorphic Encryption, Secure Multi-Party Computation, Federated Learning frameworks).
- **72-Code Scheme (`artifacts/coding_scheme.csv`):** The qualitative codebook provides a standardized taxonomy of API friction, mental-model mismatches, and developer workaround behaviors applicable to developer-facing security APIs.
- **De-identified Transcripts and Codebooks Corpus (`artifacts/developer_transcripts/` and `artifacts/developer_codebooks/`):** Serves as an open benchmark dataset of developer reasoning during privacy-preserving data analysis.
