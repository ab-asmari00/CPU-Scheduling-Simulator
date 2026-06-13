# Java Operating System Simulator

A Java-based operating system simulator that models process lifecycle management, memory allocation, and CPU scheduling. The system implements multiple scheduling algorithms, simulates operating system system calls, and visualizes execution timelines through Gantt charts while measuring scheduling performance using waiting and turnaround time metrics.

---

## Academic Context

This project was developed as part of the **Operating Systems** course.

The objective was to simulate key operating system concepts including process management, CPU scheduling, memory allocation, multithreading, and system call execution in a controlled environment.

---

## Features

* Process lifecycle simulation with custom operating system system calls
* CPU scheduling using FCFS, Round Robin, and Priority Scheduling algorithms
* Memory-aware process loading and ready queue management
* Multi-threaded architecture for concurrent job loading and scheduling
* Gantt chart generation for execution timeline visualization
* Scheduling performance analysis using waiting time and turnaround time metrics
* Interactive command-line interface for algorithm selection and comparison

---

## Scheduling Algorithms

### First-Come, First-Serve (FCFS)

Processes are executed in the order they arrive in the ready queue.

### Round Robin (RR)

Processes receive fixed CPU time slices (7ms quantum) to ensure fair CPU allocation.

### Priority Scheduling

Processes are scheduled based on priority values with an aging mechanism to reduce starvation.

---

## Operating System Concepts Demonstrated

* CPU Scheduling
* Process Lifecycle Management
* Process States (NEW, READY, RUNNING, WAITING, TERMINATED)
* Memory Management
* Ready Queue and Job Queue Handling
* System Call Simulation
* Process Scheduling Metrics
* Gantt Chart Visualization
* Concurrent Programming
* Object-Oriented Design

---

## Technologies & Tools

### Languages

* Java

### Core Concepts

* Multithreading
* CPU Scheduling Algorithms
* Memory Management
* Process Management
* Object-Oriented Programming (OOP)

### Data Structures

* Queue
* Linked List
* Priority Queue

---

## System Architecture

The simulator consists of several core components:

| Component             | Responsibility                                                    |
| --------------------- | ----------------------------------------------------------------- |
| Job Reader            | Reads process definitions and populates the job queue             |
| Memory Loader         | Loads processes into memory and manages the ready queue           |
| Scheduler             | Executes scheduling algorithms and calculates performance metrics |
| System Call Layer     | Simulates operating system process-related system calls           |
| Process Model         | Represents process attributes and execution state                 |
| Gantt Chart Generator | Visualizes execution timelines                                    |

---

## Simulated System Calls

The project implements simplified operating system system calls including:

* `createProcess()`
* `terminateProcess()`
* `setProcessState()`
* `getProcessInfo()`
* `loadMemory()`

---

## Project Structure

```text
.
├── Main.java
├── Scheduler.java
├── Process.java
├── MemoryLoader.java
├── JobReader.java
├── SystemCall.java
├── State.java
├── Results.java
├── GanttEntry.java
└── job.txt
```

---

## Running the Project

### Prerequisites

* Java JDK 8+

### Compile

```bash
javac *.java
```

### Run

```bash
java Main
```

### Available Options

```
========================================
      CPU Scheduling Simulator
========================================
Select Scheduling Algorithm:
[1] First-Come-First-Serve (FCFS)
[2] Round Robin (RR) - Quantum 7ms
[3] Priority Scheduling (Preemptive)
[4] Run All & Compare Results
[5] Exit
```

1. First-Come-First-Serve (FCFS)
2. Round Robin (RR)
3. Priority Scheduling
4. Run All Algorithms & Compare Results
5. Exit

---

## Sample Output

```
[ JOB QUEUE ] Number of processes: 15
Process ID: 1, Burst Time: 25, Priority: 4, Memory: 500
Process ID: 2, Burst Time: 13, Priority: 3, Memory: 700
Process ID: 3, Burst Time: 20, Priority: 3, Memory: 100
Process ID: 4, Burst Time: 7, Priority: 8, Memory: 300
Process ID: 5, Burst Time: 15, Priority: 2, Memory: 600
Process ID: 6, Burst Time: 10, Priority: 6, Memory: 400
Process ID: 7, Burst Time: 30, Priority: 1, Memory: 900
Process ID: 8, Burst Time: 18, Priority: 5, Memory: 350
Process ID: 9, Burst Time: 12, Priority: 7, Memory: 250
Process ID: 10, Burst Time: 22, Priority: 2, Memory: 800
Process ID: 11, Burst Time: 16, Priority: 8, Memory: 450
Process ID: 12, Burst Time: 9, Priority: 1, Memory: 550
Process ID: 13, Burst Time: 28, Priority: 6, Memory: 320
Process ID: 14, Burst Time: 14, Priority: 4, Memory: 680
Process ID: 15, Burst Time: 19, Priority: 3, Memory: 420
========================================================
```

```
========================================
      CPU Scheduling Simulator
========================================
Select Scheduling Algorithm:
[1] First-Come-First-Serve (FCFS)
[2] Round Robin (RR) - Quantum 7ms
[3] Priority Scheduling (Preemptive)
[4] Run All & Compare Results
[5] Exit
Choice: 1
```
### First-Come-First-Serve (FCFS)
```
Loading next batch of processes...
[ READY QUEUE ] ; Used memory: 2000 / 2048 MB
Process ID: 1, Burst Time: 25, Priority: 4, Memory: 500
Process ID: 2, Burst Time: 13, Priority: 3, Memory: 700
Process ID: 3, Burst Time: 20, Priority: 3, Memory: 100
Process ID: 4, Burst Time: 7, Priority: 8, Memory: 300
Process ID: 6, Burst Time: 10, Priority: 6, Memory: 400
=======================================================

[Running FCFS Scheduler]
========================================
     First-Come-First-Serve (FCFS)
========================================
Process Execution Order:
P1 -> P2 -> P3 -> P4 -> P6
Execution Timeline:
Time | Process | Start Burst | Stop Burst
-----------------------------------------
0    | P1      | 0           | 25       
25   | P2      | 25          | 38       
38   | P3      | 38          | 58       
58   | P4      | 58          | 65       
65   | P6      | 65          | 75       
Gantt Chart:
| P1  | P2  | P3  | P4  | P6  |
0     25    38    58    65    75
Average Waiting Time: 37.2 ms
Average Turnaround Time: 52.2 ms
========================================
```
```
Loading next batch of processes...
[ READY QUEUE ] ; Used memory: 1850 / 2048 MB
Process ID: 5, Burst Time: 15, Priority: 2, Memory: 600
Process ID: 7, Burst Time: 30, Priority: 1, Memory: 900
Process ID: 8, Burst Time: 18, Priority: 5, Memory: 350
=======================================================

[Running FCFS Scheduler]
========================================
     First-Come-First-Serve (FCFS)
========================================
Process Execution Order:
P5 -> P7 -> P8
Execution Timeline:
Time | Process | Start Burst | Stop Burst
-----------------------------------------
0    | P5      | 0           | 15       
15   | P7      | 15          | 45       
45   | P8      | 45          | 63       
Gantt Chart:
| P5  | P7  | P8  |
0     15    45    63
Average Waiting Time: 20.0 ms
Average Turnaround Time: 41.0 ms
========================================
```
```
Loading next batch of processes...
[ READY QUEUE ] ; Used memory: 1820 / 2048 MB
Process ID: 9, Burst Time: 12, Priority: 7, Memory: 250
Process ID: 10, Burst Time: 22, Priority: 2, Memory: 800
Process ID: 11, Burst Time: 16, Priority: 8, Memory: 450
Process ID: 13, Burst Time: 28, Priority: 6, Memory: 320
=======================================================

[Running FCFS Scheduler]
========================================
     First-Come-First-Serve (FCFS)
========================================
Process Execution Order:
P9 -> P10 -> P11 -> P13
Execution Timeline:
Time | Process | Start Burst | Stop Burst
-----------------------------------------
0    | P9      | 0           | 12       
12   | P10     | 12          | 34       
34   | P11     | 34          | 50       
50   | P13     | 50          | 78       
Gantt Chart:
| P9  | P10 | P11 | P13 |
0     12    34    50    78
Average Waiting Time: 24.0 ms
Average Turnaround Time: 43.5 ms
========================================
```
```
Loading next batch of processes...
[ READY QUEUE ] ; Used memory: 1650 / 2048 MB
Process ID: 12, Burst Time: 9, Priority: 1, Memory: 550
Process ID: 14, Burst Time: 14, Priority: 4, Memory: 680
Process ID: 15, Burst Time: 19, Priority: 3, Memory: 420
=======================================================

[Running FCFS Scheduler]
========================================
     First-Come-First-Serve (FCFS)
========================================
Process Execution Order:
P12 -> P14 -> P15
Execution Timeline:
Time | Process | Start Burst | Stop Burst
-----------------------------------------
0    | P12     | 0           | 9        
9    | P14     | 9           | 23       
23   | P15     | 23          | 42       
Gantt Chart:
| P12 | P14 | P15 |
0     9     23    42
Average Waiting Time: 10.7 ms
Average Turnaround Time: 24.7 ms
========================================

All processes have been executed successfully!
[1] Return to main menu
[2] Exit
Choice:
```
### Round Robin (Quantum = 7ms)
```
[Running Round Robin Scheduler (Quantum: 7ms)]
========================================
     Round Robin (Quantum = 7ms)
========================================
Process Execution Order:
P1 -> P2 -> P3 -> P4 -> P6 -> P1 -> P2 -> P3 -> P6 -> P1 -> P3 -> P1
Execution Timeline:
Time | Process | Start Burst | Stop Burst
-----------------------------------------
0    | P1      | 0           | 7        
7    | P2      | 7           | 14       
14   | P3      | 14          | 21       
21   | P4      | 21          | 28       
28   | P6      | 28          | 35       
35   | P1      | 35          | 42       
42   | P2      | 42          | 48       
48   | P3      | 48          | 55       
55   | P6      | 55          | 58       
58   | P1      | 58          | 65       
65   | P3      | 65          | 71       
71   | P1      | 71          | 75       
Gantt Chart:
| P1  | P2  | P3  | P4  | P6  | P1  | P2  | P3  | P6  | P1  | P3  | P1  |
0     7     14    21    28    35    42    48    55    58    65    71    75
Average Waiting Time: 55.8 ms
Average Turnaround Time: 60.8 ms
========================================
```
```
Loading next batch of processes...
[ READY QUEUE ] ; Used memory: 1850 / 2048 MB
Process ID: 5, Burst Time: 15, Priority: 2, Memory: 600
Process ID: 7, Burst Time: 30, Priority: 1, Memory: 900
Process ID: 8, Burst Time: 18, Priority: 5, Memory: 350
====================================================

[Running Round Robin Scheduler (Quantum: 7ms)]
========================================
     Round Robin (Quantum = 7ms)
========================================
Process Execution Order:
P5 -> P7 -> P8 -> P5 -> P7 -> P8 -> P5 -> P7 -> P8 -> P7 -> P7
Execution Timeline:
Time | Process | Start Burst | Stop Burst
-----------------------------------------
0    | P5      | 0           | 7        
7    | P7      | 7           | 14       
14   | P8      | 14          | 21       
21   | P5      | 21          | 28       
28   | P7      | 28          | 35       
35   | P8      | 35          | 42       
42   | P5      | 42          | 43       
43   | P7      | 43          | 50       
50   | P8      | 50          | 54       
54   | P7      | 54          | 61       
61   | P7      | 61          | 63       
Gantt Chart:
| P5  | P7  | P8  | P5  | P7  | P8  | P5  | P7  | P8  | P7  | P7  |
0     7     14    21    28    35    42    43    50    54    61    63
Average Waiting Time: 52.4 ms
Average Turnaround Time: 54.7 ms
========================================
```
```
Loading next batch of processes...
[ READY QUEUE ] ; Used memory: 1820 / 2048 MB
Process ID: 9, Burst Time: 12, Priority: 7, Memory: 250
Process ID: 10, Burst Time: 22, Priority: 2, Memory: 800
Process ID: 11, Burst Time: 16, Priority: 8, Memory: 450
Process ID: 13, Burst Time: 28, Priority: 6, Memory: 320
====================================================

[Running Round Robin Scheduler (Quantum: 7ms)]
========================================
     Round Robin (Quantum = 7ms)
========================================
Process Execution Order:
P9 -> P10 -> P11 -> P13 -> P9 -> P10 -> P11 -> P13 -> P10 -> P11 -> P13 -> P10 -> P13
Execution Timeline:
Time | Process | Start Burst | Stop Burst
-----------------------------------------
0    | P9      | 0           | 7        
7    | P10     | 7           | 14       
14   | P11     | 14          | 21       
21   | P13     | 21          | 28       
28   | P9      | 28          | 33       
33   | P10     | 33          | 40       
40   | P11     | 40          | 47       
47   | P13     | 47          | 54       
54   | P10     | 54          | 61       
61   | P11     | 61          | 63       
63   | P13     | 63          | 70       
70   | P10     | 70          | 71       
71   | P13     | 71          | 78       
Gantt Chart:
| P9  | P10 | P11 | P13 | P9  | P10 | P11 | P13 | P10 | P11 | P13 | P10 | P13 |
0     7     14    21    28    33    40    47    54    61    63    70    71    78
Average Waiting Time: 60.8 ms
Average Turnaround Time: 64.5 ms
========================================
```
```
Loading next batch of processes...
[ READY QUEUE ] ; Used memory: 1650 / 2048 MB
Process ID: 12, Burst Time: 9, Priority: 1, Memory: 550
Process ID: 14, Burst Time: 14, Priority: 4, Memory: 680
Process ID: 15, Burst Time: 19, Priority: 3, Memory: 420
====================================================

[Running Round Robin Scheduler (Quantum: 7ms)]
========================================
     Round Robin (Quantum = 7ms)
========================================
Process Execution Order:
P12 -> P14 -> P15 -> P12 -> P14 -> P15 -> P15
Execution Timeline:
Time | Process | Start Burst | Stop Burst
-----------------------------------------
0    | P12     | 0           | 7        
7    | P14     | 7           | 14       
14   | P15     | 14          | 21       
21   | P12     | 21          | 23       
23   | P14     | 23          | 30       
30   | P15     | 30          | 37       
37   | P15     | 37          | 42       
Gantt Chart:
| P12 | P14 | P15 | P12 | P14 | P15 | P15 |
0     7     14    21    23    30    37    42
Average Waiting Time: 28.0 ms
Average Turnaround Time: 32.7 ms
========================================

All processes have been executed successfully!

```
###  Priority Queue (Preemptive with Aging)
```
[Running Priority Scheduler]
========================================
     Priority Queue (Preemptive with Aging)
========================================
Process Execution Order:
P4 -> P6 -> P1 -> P3 -> P2
Execution Timeline:
Time | Process | Start Burst | Stop Burst
-----------------------------------------
0    | P4      | 0           | 7        
7    | P6      | 7           | 17       
17   | P1      | 17          | 42       
42   | P3      | 42          | 62       
62   | P2      | 62          | 75       
Gantt Chart:
| P4  | P6  | P1  | P3  | P2  |
0     7     17    42    62    75
Average Waiting Time: 25.6 ms
Average Turnaround Time: 40.6 ms
========================================
```
```
Loading next batch of processes...
[ READY QUEUE ] ; Used memory: 1850 / 2048 MB
Process ID: 5, Burst Time: 15, Priority: 2, Memory: 600
Process ID: 7, Burst Time: 30, Priority: 1, Memory: 900
Process ID: 8, Burst Time: 18, Priority: 5, Memory: 350
====================================================

[Running Priority Scheduler]
========================================
     Priority Queue (Preemptive with Aging)
========================================
Process Execution Order:
P8 -> P5 -> P7
Execution Timeline:
Time | Process | Start Burst | Stop Burst
-----------------------------------------
0    | P8      | 0           | 18       
18   | P5      | 18          | 33       
33   | P7      | 33          | 63       
Gantt Chart:
| P8  | P5  | P7  |
0     18    33    63
Average Waiting Time: 17.0 ms
Average Turnaround Time: 38.0 ms
========================================
```
```
Loading next batch of processes...
[ READY QUEUE ] ; Used memory: 1820 / 2048 MB
Process ID: 9, Burst Time: 12, Priority: 7, Memory: 250
Process ID: 10, Burst Time: 22, Priority: 2, Memory: 800
Process ID: 11, Burst Time: 16, Priority: 8, Memory: 450
Process ID: 13, Burst Time: 28, Priority: 6, Memory: 320
====================================================

[Running Priority Scheduler]
========================================
     Priority Queue (Preemptive with Aging)
========================================
Process Execution Order:
P11 -> P9 -> P13 -> P10
Execution Timeline:
Time | Process | Start Burst | Stop Burst
-----------------------------------------
0    | P11     | 0           | 16       
16   | P9      | 16          | 28       
28   | P13     | 28          | 56       
56   | P10     | 56          | 78       
Gantt Chart:
| P11 | P9  | P13 | P10 |
0     16    28    56    78
Average Waiting Time: 25.0 ms
Average Turnaround Time: 44.5 ms
========================================
```
```
Loading next batch of processes...
[ READY QUEUE ] ; Used memory: 1650 / 2048 MB
Process ID: 12, Burst Time: 9, Priority: 1, Memory: 550
Process ID: 14, Burst Time: 14, Priority: 4, Memory: 680
Process ID: 15, Burst Time: 19, Priority: 3, Memory: 420
====================================================

[Running Priority Scheduler]
========================================
     Priority Queue (Preemptive with Aging)
========================================
Process Execution Order:
P14 -> P15 -> P12
Execution Timeline:
Time | Process | Start Burst | Stop Burst
-----------------------------------------
0    | P14     | 0           | 14       
14   | P15     | 14          | 33       
33   | P12     | 33          | 42       
Gantt Chart:
| P14 | P15 | P12 |
0     14    33    42
Average Waiting Time: 15.7 ms
Average Turnaround Time: 29.7 ms
========================================

All processes have been executed successfully!
```

---

## Learning Outcomes

This project provided practical experience with:

* Operating system design principles
* CPU scheduling algorithms
* Process management
* Memory allocation strategies
* Concurrent programming with threads
* Software architecture and modular design
* Performance analysis and scheduling evaluation
* Collaborative development using Git and GitHub
