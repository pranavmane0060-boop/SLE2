# SLE2
SLE-2: BFS vs DFS Profiling on a Maze

Course: 02AML204 – Introduction to Artificial Intelligence Name: (fill in) PRN: (fill in) Division: A / B Date: 22 September 2026

Overview

This project profiles two uninformed search algorithms, Breadth-First Search (BFS) and Depth-First Search (DFS), on the same maze and compares them on running time, nodes expanded and path length.

Problem Setup
Maze: 15×15 grid (225 cells), generated with a randomized recursive-backtracker
Type: "perfect" maze (exactly one simple path between any two cells)
Query: solve from cell (0,0) to cell (14,14)
The maze is generated once and kept fixed for all runs
Profiling Method
Wall-clock timing with time.perf_counter(), cross-checked with cProfile
50 runs per algorithm on the identical start-to-goal query
Nodes expanded (cells popped from the frontier) counted on one representative run of each
py-spy was attempted but could not be installed in the offline sandbox, so perf_counter + cProfile were used instead
Results
Metric	BFS	DFS	Better?
Best Time (ms)	0.1036	0.0879	DFS
Avg. Time (ms)	0.1142	0.0946	DFS
Worst Time (ms)	0.1846	0.1160	DFS
Nodes Expanded	212	174	DFS
Path Length (moves)	122	122	Tie (unique path)
Key Findings
Both algorithms return the same 122-move path because the maze has only one possible route.
DFS expanded fewer nodes (174 vs 212) and was about 1.21× faster on average.
BFS's shortest-path guarantee gives no benefit on a perfect maze, but its level-by-level expansion still costs time.
On a maze or graph with loops or multiple routes, BFS would be the right choice, since DFS could return a much longer path.
Files
SLE2_PRN_YourName.docx – the full profiling report (method, results table, chart, analysis, AI contribution note, conclusion)
README.md – this file
Usage

The report documents the experiment. If you include your script in the repository, add run instructions here, for example:

bash
python maze_profile.py
AI Contribution

Claude (Anthropic) was used to help write the maze generator, the BFS/DFS implementations, the timing harness and the report draft. See section 5 of the report for details.

Content
SLE2_PRN_YourName (1).docx

DOCX

PDF
