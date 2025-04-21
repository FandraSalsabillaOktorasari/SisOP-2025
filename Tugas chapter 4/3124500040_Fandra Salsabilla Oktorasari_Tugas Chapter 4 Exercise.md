LAPORAN SISTEM OPERASI

**TUGAS CHAPTER 4: EXERCISE**







![](Aspose.Words.3f077cde-b48c-4fea-8917-015ed7ead335.001.jpeg)







Nama	: Fandra Salsabilla Oktorasari

NRP	: 3124500040

Dosen Pengajar	: Dr Ferry Astika Saputra ST, M.Sc


**PROGRAM STUDI D3 TEKNIK INFORMATIKA** 

**POLITEKNIK ELEKTRONIKA NEGERI SURABAYA (PENS)** 

**TAHUN 2024**



1. Provide three programming examples in which multithreading
1. Using Amdahl's Law, calculate the speedup gain of an application that has a 60 percent parallel component for (a) two processing cores and (b) four processing cores
1. Does the multithreaded web server described in Section 4.1 exhibit task or data parallelism?
1. What are two differences between user-level threads and kernel-level threads? Under what circumstances is one type better than the other?
1. Describe the actions taken by a kernel to context-switch between kernel-level threads.
1. What resources are used when a thread is created? How do they differ from those used when a process is created?
1. Assume that an operating system maps user-level threads to the kernel using the many-to-many model and that the mapping is done through LWPs. Furthermore, the system allows developers to create real-time threads for use in real-time systems. Is it necessary to bind a real-time thread to an LWP? Explain.

Answer

1. Three Programming Examples of Multithreading
   1) Web Server
      1. A web server handles multiple client requests simultaneously.
      1. Each thread manages a separate request (e.g., fetching a webpage or processing data).
      1. Improves responsiveness and throughput.
   1) Video Game
      1. One thread handles graphics rendering, another processes physics calculations, and a third manages user input.
      1. Prevents lag by distributing workload.
   1) File Downloader
      1. Multiple threads download different parts of a file simultaneously (e.g., a torrent client).
      1. Speeds up the overall download process.

1. Amdahl's Law Calculation

   Amdahl's Law formula:

Speedup = 11-P+ PN

Where:

P = Parallel portion (60% or 0.6)

N = Number of cores

1) Two processing cores (N = 2)

Speedup = 11-0,6+ 0,63=10,4+0,3= 10,7 ≈1,43 

1) Four processing cores (N = 4)

Speedup = 11-0,6+ 0,64=10,4+0,15= 10,55 ≈1,82 

Interpretation:

With 2 cores → ~43% faster.

With 4 cores → ~82% faster (diminishing returns due to the 40% serial portion).

1. Task Parallelism: Different threads perform different tasks (e.g., one handles requests, another logs data).

   Data Parallelism: Same task is performed on different data (e.g., processing multiple requests identically).

   The web server in Section 4.1 exhibits task parallelism because threads handle different sub-tasks (e.g., listening, processing, sending responses).

1. User-Level Threads (ULT) vs. Kernel-Level Threads (KLT)

   |Difference|User-Level Threads (ULT)|Kernel-Level Threads (KLT)|
   | :- | :- | :- |
   |Management|Managed by user-level libraries.|Managed by the OS kernel.|
   |Blocking|If one thread blocks, all block.|One thread blocking doesn’t affect others.|
   |Speed|Faster (no kernel mode switches).|Slower (requires kernel intervention).|

   When to Use Which?

- ULTs better for fine-grained tasks needing fast creation/switching (e.g., simple apps).
- KLTs better for CPU-bound tasks needing true parallelism (e.g., heavy computation).

1. Kernel Actions for Context-Switching KLTs
   1) Save the current thread’s state (registers, PC, stack pointer) to its PCB.
   1) Schedule the next thread (via the kernel scheduler).
   1) Load the new thread’s state from its PCB.
   1) Switch memory maps if threads belong to different processes.
   1) Resume execution of the new thread.

1. Resources Used for Thread vs. Process Creation

   |Thread Creation|Process Creation|
   | :- | :- |
   |Shares memory, files, and code with parent.|Gets separate memory space, files, and code.|
   |Only needs a stack and registers.|Requires full PCB (memory, descriptors, etc.).|
   |Cheaper/faster to create.|More expensive/slower.|

1. Binding Real-Time Threads to LWPs?
- LWP (Lightweight Process): Acts as a bridge between ULTs and KLTs.
- Real-Time Threads: Must meet strict timing deadlines.

  Yes, binding is necessary because:

1) Real-time threads need direct kernel scheduling (via LWP) to ensure priority enforcement.
1) Without binding, the thread might be delayed by user-level scheduling, violating real-time guarantees.
