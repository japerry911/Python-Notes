# Concurrency Notes

- concurrency - simultaneous occurrence
- thread, task, process
  - same from **only** high level
- concurrency does **not** run things at the same time
  - only multiprocessing does this
  - Threading and asyncio both run on a single processor and therefore only run one at a time
    - find ways to take turns to speed up the overall process
    - still called concurrency
- threading vs asyncio
  - in threading, the OS knows each thread and can interrupt it at any time to start running a different thread
    - pre-emptive multitasking ^
  - in asyncio, it utilizes cooperative multitasking
    - the tasks ust cooperate by announcing when they are ready to be switched out
- what is parallelism?
  - make use of CPU cores on laptop by using multiprocessing
  - in multiprocessing, Python creates new processes
    - broadly speaking, a process is a different program
      - way to think about it: each process runs in its own Python interpreter
    - if running on different core, the processes can run simulanteously
- when is concurrency useful?
  - concurrency can make a difference for 2 types of problems
    1. CPU-bound
       - spends most of time doing CPU operations
         - speeding up involes finding ways to do more computations in the same amount of time
       - significant computation without talking to the network or access a file
    2. I/O-bound
       - spends most of its time talking to a slow device, network connection/hard drive/printer
         - speeding up involves overlapping the times spent waiting for these devices
       - program might slow down due to having to frequently wait for input/output
         - arise frequently when program is working with things that are much slower than its CPU
           - file system and network connections usually
