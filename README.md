# NTU-FYP-Streaming-Diarization
### Name: Melisa Lee
### FYP ID: CCDS26-0157
### Project Title: Streaming: Who speak when task (Diarization)
### Supervisor: Prof Chng Eng Siong

### Start Date: 10 August 2026
### End Date: 12 May 2027



## Overview

Speaker diarization is the task of partitioning an audio stream by speaker identity, determining **"who spoke when"** without necessarily knowing in advance who the speakers are or how many there will be. It is a foundational component of meeting transcription, minute-taking and conversational AI, where knowing who said what is as important as knowing what was said.

Offline systems process an entire recording before producing output. **Streaming (online) systems** must instead produce speaker labels incrementally as audio arrives, under a bounded latency budget. They decide causally, from only what has already been heard, whether the current speech belongs to a known speaker or a new one, and they must disentangle overlapping speech without listening ahead.

**Problem.** State-of-the-art streaming models such as NVIDIA's Streaming Sortformer represent speakers with a fixed number of output tracks and support at most **4 simultaneous speakers**. Once more speakers are active, the extra speech is either missed or misattributed to an existing track, and accuracy degrades sharply. This project treats that fixed track capacity as the central problem: how to reliably support four or more simultaneous speakers while keeping the low-latency, causal properties needed for streaming.

**Objectives.**
1. Review the architecture, methodology and results of the team's existing sub-systems (`benchmarking`, `sortformer_dynamic_memory`, `lseend_streaming`, `sortformer_clustering`).
2. Complete `sortformer_dynamic_memory`'s missing evaluation stages (embedding quality, matcher training, end-to-end DER/JER) to establish a trustworthy baseline.
3. Characterise new-speaker detection and overlap-handling weaknesses across varying noise and speaker-count conditions.
4. Design, implement and evaluate a targeted improvement, such as overlap-conditioned segment handling or capacity-exceeded detection.
5. Compare the result against Sortformer v2.1, LS-EEND and the baseline `sortformer_dynamic_memory`.



## Video Updates

[Video](https://youtube.com/playlist?list=PLH0Ig-prwpK4&si=teOMpD4uJXqVFcUo)


## Roadmap / Milestones

| Period | Phase | Key Activities |
|---|---|---|
| Aug – Sep 2026 | **Phase 0:** Onboarding, Review & Reproduction | Access the repositories and meet the team; review the diarization literature and all inherited sub-systems; set up environments and reproduce a representative subset of benchmark results |
| Oct 2026 | **Phase 1:** Baseline Pipeline Completion | Run the missing embedding-quality evaluation and matcher training (rule-based and learned variants) for the dynamic-memory system |
| Nov 2026 | **Phase 2:** End-to-End Baseline Evaluation | Run end-to-end streaming inference and DER/JER evaluation across the integrated datasets |
| Dec 2026 | **Phase 3:** Stress-Test Analysis | Vary background noise and number of concurrent speakers to break down baseline performance; finalise the weakness to target |
| Jan 2027 | **Phase 4:** Interim Report | Consolidate the review, reproduced baselines and chosen direction into the Interim Report |
| Feb 2027 | **Phase 5:** Design & Implementation | Design and implement the improvement to new-speaker detection and/or overlap handling, with unit tests |
| Early Mar 2027 | **Phase 6:** Evaluation & Ablation | Evaluate the improved system against all baselines under the Phase 3 conditions; run ablations |
| Mar 2027 | **Phase 7:** Final Report & Presentation | Write the Final Report; prepare presentation slides and a working demo |


## Contact
* **Email**: [melisakomputer@gmail.com](mailto:melisakomputer@gmail.com)
* **LinkedIn**: [linkedin.com/in/melisa-lee](https://www.linkedin.com/in/melisa-lee-2a7409283/)

## References
