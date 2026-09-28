---
name: reactor
description: Reactor pattern — run multiple agents on the same task independently, have them challenge each other's solutions, then vote (one-shot) or iterate (multi-shot) until the best solution emerges. Use when a problem benefits from several independent attempts and cross-critique rather than a single agent's possibly biased answer.
---

## reactor pattern
Goal: let multiple agents work on the same problem so that eventually the best solution is found (unlike relying on one agent that might have biases)

Algorithm:
1. Create solution candidates: Multiple agents get the same task and work on solution independently
2. Challenge solution candidates:
    1. Each agent challenges the solutions of other agents. Way of challenging depends heavily on the type of task and usually is given together with task. examples: discussion of the solution, testing it, trying to break etc)
    2. Sometimes the author of solution gets possibility to defend the solution (e.g. answer critical comments) and challenging phase may take multiple iterations
3. (If one-shot reactor) All agents vote for the best solution END. (beware the even in one-shot reactor solution challenge phase is not skipped) 
4. (If multi-shot reactor) All agents create their new version of solution based on all solutions and results of challenging them. Then cycle repeats from point 2.

Input parameters to reactor:
1. Agents config (which harnesses, how to run)
2. Task (including goal and context)
3. Challenge strategy
4. Finish criteria (one-shot vs convergence criteria etc)
