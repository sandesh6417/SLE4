# Contribution Note

**Student:** Sandesh Tanaji Patil | **PRN:** 25UAM044 | **Division:** A
**Course:** 02AML204 – Introduction to Artificial Intelligence
**Date:** 12 October 2026

## Author Contributions

I am responsible for the following:

- Selected and reviewed the 8-Puzzle setup (start state `1 2 3 / 4 _ 6 / 7 5 8`, goal state `1 2 3 / 4 5 6 / 7 8 _`).
- Compared BFS and DFS using timing, expanded-node counts, path length and `cProfile`.
- Checked the reported results against BFS/DFS concepts.
- Reviewed the responsibilities of each part of the C4 architecture (Input, Search Engine, Memory, Output).
- Made the decision to prefer BFS for the tested case, and I will explain and defend it in the viva.

## AI Tool Usage Disclosure

| Tool | Used for |
| --- | --- |
| **Claude** | Help with the initial implementation and the profiling/report structure (recorded in my SLE-2 report). |
| **ChatGPT** | Organizing and drafting the SLE-4 ADR. |

AI assistance covered:

- Structuring explanations.
- Summarizing the profiling evidence.
- Presenting the architecture decision clearly.

## Responsibility Statement

AI tools were used as assistants. I reviewed the outputs, I understand the code, results and design decisions, and I take responsibility for the final submission.

## Known Limitations

The measurements come from one start/goal setup and three runs, and Greedy Best-First Search was not profiled. These limits are stated in the README and the ADR.
