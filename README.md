# 8-Puzzle Solver: BFS vs DFS

**Course:** 02AML204 – Introduction to Artificial Intelligence
**Student:** Sandesh Tanaji Patil | **PRN:** 25UAM044 | **Division:** A
**Repository:** https://github.com/sandesh6417/AI-Agent.git

## Overview

This project solves the classic **8-Puzzle** by searching for a path from a start board to a goal board. It implements **Breadth-First Search (BFS)** and **Depth-First Search (DFS)**, both with visited-state tracking, and compares them on the same puzzle using timing, expanded-node counts, path length and `cProfile`.

**Tested puzzle** (`_` = blank):

| Start | Goal |
| --- | --- |
| 1 2 3 | 1 2 3 |
| 4 _ 6 | 4 5 6 |
| 7 5 8 | 7 8 _ |

## Key Decision (ADR): BFS is preferred

BFS is the preferred algorithm for the tested case because it returns the shortest path with far less work. BFS is optimal for unweighted problems where every move costs the same.

| Metric | BFS | DFS |
| --- | --- | --- |
| Average time (3 runs) | 0.017 ms | 19.38 ms |
| Nodes expanded | 3 | 17,742 |
| Path length | 2 moves (optimal) | 22 moves |
| Function calls (cProfile) | 42 | 114,082 |

In this test DFS took about 1,140x as long as BFS.

## Architecture (C4 summary)

The design separates input, search processing, memory and output.

- **Input:** start state and goal state.
- **Search Engine** (core container):
  - **Algorithm Controller:** selects BFS or DFS.
  - **Visited Set Manager:** prevents repeated exploration.
  - **Goal Test:** checks whether a state is the goal.
  - **Path Reconstructor:** builds the move sequence for output.
- **Memory:** puzzle state and visited set.
- **Output:** solution path and statistics.

Because the algorithm is selected in one place, BFS and DFS can be compared or swapped without redesigning the system.

## Usage

> Adjust the file names below to match your repository.

```bash
git clone https://github.com/sandesh6417/AI-Agent.git
cd AI-Agent
python main.py
```

Requires Python 3.x. Profiling uses only the standard library (`time`, `cProfile`).

## Limitations

- Results come from **one start/goal pair and three runs**. They do not guarantee BFS is faster on every puzzle.
- BFS stores the frontier, so memory can grow quickly on larger search spaces.
- Greedy Best-First Search was considered but **not profiled** in the submitted results.

## Future Work

- Profile more start states and measure memory as well as time.
- Add and benchmark Greedy Best-First Search (and A* with a heuristic).

## Documentation

- **SLE-1:** AI-agent/search code, README and contribution notes.
- **SLE-2:** BFS vs DFS profiling.
- **SLE-3:** Full C4 architecture.
- **SLE-4:** Architecture Decision Record and viva notes.

See [CONTRIBUTION.md](CONTRIBUTION.md) for authorship and AI-use disclosure.
