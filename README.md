# OS502

This document is used to demonstrate some basic ideas of implement the core of OS502. The code of this project will not be put online because doing so could bring huge inconvenience to WPI CS502 class of following years. 

## Feature List:
A set of system calls

• Process related system calls;


• Disk related system calls;

• File system related system calls;

A set of interrupts handlers

• Timeout handler;

• Disk interrupt handler;

A process management and schedule system:

• PCB definition;

• Queue definition;

• One process list;

• One ready queue;

• One timer queue;

• 8 disk queues;

• Semaphores for process list and queues;

• Synchronization;

• Dispatcher;

• Auxiliary functions;

A file system:

• Data block definition;

• Block 0 definition;

• Header definition;

• Index block definition;

• Node definition;

• Disk definition;

• Data read/write procedures;

• File/Directory operation procedures;

• Auxiliary functions;

OS initialization operation

• Initialization of first process;

• Initialization of queues;

• Initialization of process list;

• Initialization of file system;

• Test kick off;

Memory Management

• Page Fault Handling;

• LRU approximation for page replacement;

• Frame table mamangement and tracking;

• Mapping of virtual memory and physical memory;

• Swap area managemnt;


## Process Schedule

![process](img/process.png)

## Memory Management

![mm](img/Project2 Memory Management.png)

![fc](img/project2 flowchart large.png)


## Test Output


A test output is shown as below:



This is Simulation Version 4.30 and Hardware Version 4.20.



Program called with 2 arguments: ./z502 test1

Calling with argument 'sample' executes the sample program.

Calling with 'test' plus a number in 1-16 or 21-28 executes the specified test.

Simulation is running as a UniProcessor

Add an 'M' to the command line to invoke multiprocessor operation.



Test 1 is running.

This is Release 4.30:  Test 1

SVC handler: get_time 

Arg 0: Contents = (Decimal) 123145312513712,  (Hex) 7000009BAEB0

SVC handler: sleep    

Arg 0: Contents = (Decimal)      100,  (Hex)       64

Interrupt_handler: Found device ID 4 with status 0

SVC handler: get_time 

Arg 0: Contents = (Decimal) 123145312513704,  (Hex) 7000009BAEA8

Sleep Time = 100, elapsed time= 138

SVC handler: get_pid  

Arg 0: Contents = (Decimal) 4558878139,  (Hex) 10FBAF5BB

Arg 1: Contents = (Decimal) 123145312513728,  (Hex) 7000009BAEC0

Arg 2: Contents = (Decimal) 123145312513736,  (Hex) 7000009BAEC8

Program correctly returned success.

The PID of this process is 1

SVC handler: term_proc

Arg 0: Contents = (Decimal)       -1,  (Hex) FFFFFFFFFFFFFFFF

Arg 1: Contents = (Decimal) 123145312513736,  (Hex) 7000009BAEC8


Hardware Statistics during the Simulation

Context Switches =     1:  Mean Number Running Threads =   1.00   CALLS =    39

The Z502 halts execution and Ends at Time 205

Exiting the program


## Disk Format

0000 01 04 00 00 00 08 01 00 11 04 11 00 00 00 00 00 

0001 FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 

0002 FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 

0003 FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 

0004 FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 

0005 FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 

0006 FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 

0007 FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 

0008 FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF FF 

0009 FF FF FF 07 00 00 00 00 00 00 00 00 00 00 00 00 

0411 1F 72 6F 6F 74 00 00 00 03 67 00 00 12 04 00 00 

0413 1E 54 65 73 74 31 30 00 FB 0B 09 00 14 04 00 00 

0415 1D 66 69 6C 65 31 00 00 FA 4B 11 00 16 04 00 00 

0417 1C 66 69 6C 65 32 00 00 FA 94 19 00 18 04 00 00 

0419 1B 66 69 6C 65 31 00 00 F2 CA 21 00 1A 04 00 00 

