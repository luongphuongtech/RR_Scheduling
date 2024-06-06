# Priority-Based Round Robin Scheduling Algorithm

This project implements a Priority-Based Round Robin Scheduling Algorithm in C++ on a Linux system. The scheduler handles exactly 5 processes, each with specific CPU and I/O bursts, and is managed based on their priorities. A higher numerical priority value indicates a lower relative priority.

## Features

- **Round-Robin Scheduling with Priorities**: Processes are scheduled based on a round-robin mechanism, taking into account their priorities.
- **Time Quantum**: The user can set the time quantum to either 4 or 7 units. No other values are accepted.
- **Idle Task**: An idle task (`Pidle`) is scheduled when no other processes are available to run.
- **Strict Scheduling Rules**: Scheduling decisions are made only after the expiry of the current time quantum, and no running process is preempted until its time quantum expires.

## Scheduling Rules

1. **Ready Queue**: Every process first enters the ready queue. The highest priority process will always be at the head of the queue.
2. **Time Quantum Expiry**: The process at the head of the queue will run on the CPU for the set time quantum.
3. **Rejoining Ready Queue**: Every running process will join the ready queue when the quantum expires.
4. **Scheduling Decision**: A scheduling decision is made only after the expiry of the quantum, giving the highest priority process the CPU.
5. **No Preemption**: No running process is preempted until its time quantum expires, even if a higher priority process enters the system during this time.
6. **I/O Handling**: Processes proceed for I/O only after completing their first CPU burst. They rejoin the ready queue after I/O completion and terminate after completing the second CPU burst.
7. **Equal Priority Processes**: For processes arriving at the same time with equal priorities, they are scheduled in the order listed in the input file.
8. **FCFS Tie-Breaking**: First-Come-First-Serve (FCFS) is used to break any other ties encountered during scheduling.

