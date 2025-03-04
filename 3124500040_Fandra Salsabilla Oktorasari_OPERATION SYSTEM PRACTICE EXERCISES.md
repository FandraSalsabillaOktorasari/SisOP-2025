LAPORAN SISTEM OPERASI

**TUGAS KE -- 2 OPERATION SYSTEM: PRACTICE EXERCISES**

![](./image1.jpeg){width="2.2in" height="2.2083333333333335in"}

> Nama : Fandra Salsabilla Oktorasari
>
> NRP : 3124500040
>
> Dosen Pengajar : Dr Ferry Astika Saputra ST, M.Sc

**PROGRAM STUDI D3 TEKNIK INFORMATIKA**

**POLITEKNIK ELEKTRONIKA NEGERI SURABAYA (PENS)**

**TAHUN 2024**

**\
**

PRACTICE EXERCISES

1.  What are the three main purposes of an operating system?

2.  We have stressed the need for an operating system to make efficient
    use of the computing hardware. When is it appropriate for the
    operating system to forsake this principle and to \"waste\"
    resources? Why is such a system not really wasteful?

3.  What is the main difficulty that a programmer must overcome in
    writing an operating system for a real-time environment?

4.  Keeping in mind the various definitions of operating system,
    consider whether the operating system should include applications
    such as web browsers and mail programs. Argue both that it should
    and that it should not, and support your answers.

5.  How does the distinction between kernel mode and user mode function
    as a rudimentary form of protection (security)?

6.  Which of the following instructions should be privileged?

    a.  Set value of timer.

    b.  Read the clock.

    c.  Clear memory.

    d.  Issue a trap instruction.

    e.  Turn off interrupts.

    f.  Modify entries in device-status table.

    g.  Switch from user to kernel mode.

    h.  Access I/O device.

7.  Some early computers protected the operating system by placing it in
    a memory partition that could not be modified by either the user job
    or the operating system itself. Describe two difficulties that you
    think could arise with such a scheme.

8.  Some CPUs provide for more than two modes of operation. What are two
    possible uses of these multiple modes?

9.  Timers could be used to compute the current time. Provide a short
    description of how this could be accomplished.

10. Give two reasons why caches are useful. What problems do they solve?
    What problems do they cause? If a cache can be made as large as the
    device for which it is caching (for instance, a cache as large as a
    disk), why not make it that large and eliminate the device?

11. Distinguish between the client-server and peer-to-peer models of
    distributed systems.

ANSWER

1.  The three main purposes of an operating system are:

```{=html}
<!-- -->
```
a.  **Resource Management**: Managing hardware resources like CPU,
    > memory, and I/O devices to ensure efficient and fair allocation
    > among applications and users.

b.  **User Interface**: Providing an interface for users to interact
    > with the computer system, such as command-line interfaces (CLI) or
    > graphical user interfaces (GUI).

c.  **Program Execution**: Facilitating the execution of application
    > programs by offering services like process management and
    > scheduling.

```{=html}
<!-- -->
```
2.  It is appropriate for an operating system to \"waste\" resources in
    scenarios where enhancing user experience or simplifying system
    design outweighs the need for optimal resource utilization. For
    example:

-   **Graphical User Interfaces (GUIs)**: GUIs consume more memory and
    processing power than command-line interfaces but provide a more
    intuitive and user-friendly experience.

-   **Background Services**: Running background services or daemons may
    use additional resources but can improve system responsiveness and
    functionality.

> In these cases, the perceived \"waste\" of resources leads to benefits
> like improved usability and convenience, making the trade-off
> justifiable.

3.  The primary challenge in developing an operating system for a
    real-time environment is ensuring that the system can meet strict
    timing constraints and deadlines. This requires deterministic
    behavior, where the system\'s responses to inputs are predictable
    and occur within specified time limits. Achieving this involves
    implementing precise scheduling algorithms and efficient interrupt
    handling mechanisms.

4.  **It should** include applications like web browsers and mail
    programs because they are essential tools for most users. Having
    these applications pre-installed ensures that users can immediately
    access the internet and communicate via email without needing to
    install additional software. It also provides a seamless and
    optimized experience, as the operating system can ensure
    compatibility and performance for built-in applications.

**It shouldn\'t** include these applications because not all users need
or want them. Pre-installed applications can take up unnecessary disk
space and system resources, potentially slowing down the system.
Additionally, users may prefer to choose their own applications rather
than being forced to use what comes with the OS. This approach respects
user preference and avoids \"bloatware\" that could clutter the system.

5.  The separation between kernel mode and user mode serves as a
    fundamental security mechanism by controlling access to critical
    system resources:

-   **Kernel Mode**: Allows execution of privileged instructions and
    > direct access to hardware, reserved for the operating system\'s
    > core functions.

-   **User Mode**: Restricts access to critical instructions and
    > hardware, ensuring that user applications cannot directly
    > interfere with system operations.

> This distinction prevents user applications from performing
> unauthorized actions that could compromise system stability and
> security.

6.  **Privileged Instructions:**

-   a\. Set value of timer.

-   c\. Clear memory.

-   e\. Turn off interrupts.

-   f\. Modify entries in device-status table.

-   g\. Switch from user to kernel mode.

-   h\. Access I/O device.

> **Non-Privileged Instructions:**

-   b\. Read the clock.

-   d\. Issue a trap instruction.

> Privileged instructions are those that can affect the system\'s
> operation and stability; therefore, they are restricted to kernel mode
> to prevent unauthorized access and ensure system integrity.

7.  **Lack of Flexibility for Updates and Maintenance**

> If the operating system is placed in a memory partition that cannot be
> modified, updating the system, fixing bugs, or applying security
> patches becomes extremely difficult.

-   Modern operating systems require frequent updates to address
    > security vulnerabilities, improve performance, and add new
    > features.

-   Without the ability to modify the OS, the only way to update it
    > would be to completely replace the system, such as by reinstalling
    > from external media. This process can cause significant downtime
    > and may not be practical for mission-critical systems.

> **Inefficient Memory Utilization**
>
> A fixed partition for the OS can lead to wasted memory or insufficient
> space for system operations.

-   If the allocated partition is too large, a significant portion of
    > memory may remain unused, reducing overall system efficiency.

-   If the partition is too small, the OS may run out of space for logs,
    > temporary files, or updates, potentially leading to system
    > instability or failure.

-   Modern systems dynamically allocate memory based on usage, which is
    > not possible with a fixed, unmodifiable partition.

> While this approach may provide additional protection against
> unauthorized modifications or malware attacks, its lack of flexibility
> and inefficient memory usage make it impractical for modern computing
> systems. Today, operating systems rely on access control mechanisms
> and dynamic memory management instead of rigid partitioning to ensure
> both security and efficiency.

8.  Two possible uses for multiple CPU modes:

```{=html}
<!-- -->
```
a.  **Enhanced Security**: Additional modes allow more granular security
    > policies, differentiating privilege levels among users or
    > processes.

b.  **Support for Virtualization**: Modes like hypervisor mode enable
    > multiple operating systems to run simultaneously through
    > virtualization.

```{=html}
<!-- -->
```
9.  A timer in an operating system can maintain the current time by
    generating interrupts at regular intervals. Each interrupt signals
    that a certain amount of time has passed, allowing the OS to update
    its internal clock. For example, x86 systems use hardware timers
    such as the Programmable Interval Timer (PIT) or Real-Time Clock
    (RTC) to generate periodic interrupts used for timekeeping.

10. Caches play a crucial role in improving system performance by
    providing faster access to frequently used data. Instead of
    retrieving data from slower main memory or storage every time, a
    cache stores recently accessed information, allowing the system to
    access it much more quickly. This significantly reduces latency and
    helps optimize processing speed.

One of the main problems that caches solve is performance bottlenecks.
Without caching, a system would constantly need to fetch data from
slower storage, leading to delays. By keeping frequently accessed data
readily available, caches help ensure smoother and more efficient
operations.

However, caches also come with their own challenges. One major issue is
**data consistency**---ensuring that the cached data remains
synchronized with the main storage can be difficult, especially in
systems with multiple processors accessing and modifying data
simultaneously. Another challenge is **management overhead**, as
implementing and maintaining an effective caching system adds complexity
to system design.

Given the benefits of caching, one might wonder: why not make the cache
as large as the storage device it caches? The answer lies in **cost and
functionality**. Cache memory is built using much faster and more
expensive technology than main storage, making it impractical to create
a cache of the same size as the entire storage device. Additionally,
caches and main storage serve different purposes---caches are meant for
quick access to frequently used data, while main storage is designed for
large-capacity storage. If we were to eliminate main storage in favor of
a large cache, we would lose the advantages of both systems, leading to
inefficiencies rather than improvements.

11. The Difference Between the Client-Server and Peer-to-Peer (P2P)
    Models

```{=html}
<!-- -->
```
a.  **Client-Server Model**

```{=html}
<!-- -->
```
1)  **Centralized Structure**

-   In this model, there is a clear separation between **servers** and
    > **clients**.

-   The **server** is a powerful central machine that provides services
    > or resources.

-   The **clients** are devices (such as computers, smartphones, or web
    > browsers) that request and receive services from the server.

> **Example:** When we visit a website, our web browser (client) sends a
> request to a web server, which then responds by delivering the webpage
> we requested.

2)  **Centralized Management**

-   The server is responsible for managing resources, handling requests,
    > and ensuring smooth operation.

-   Clients have limited control; they can only request and receive data
    > but cannot function as servers themselves.

-   This centralized control makes security, maintenance, and data
    > management easier, but also creates a **single point of
    > failure**---if the server goes down, clients lose access.

3)  **Example Use Cases**

-   **Websites** (Google, Facebook, Amazon) operate on a client-server
    > model.

-   **Email services** (Gmail, Outlook) rely on centralized mail
    > servers.

-   **Online gaming** (Fortnite, Call of Duty) where game servers manage
    > multiplayer sessions.

b.  **Peer-to-Peer (P2P) Model**

```{=html}
<!-- -->
```
1)  **Distributed Structure**

-   In contrast to the client-server model, P2P networks **do not rely
    > on a central server**.

-   Every device (peer) in the network **acts as both a client and a
    > server**, meaning it can request data from other peers and also
    > provide data to them.

> **Example:** When using a file-sharing network like BitTorrent, we can
> download files from multiple users (peers) while also uploading
> portions of the file to others.

2)  **Decentralized Management**

-   Since there is no central server, all peers share equal
    > responsibility for maintaining the network.

-   This makes P2P networks **more resilient**---if one peer goes
    > offline, the system continues to function.

-   However, managing security and data integrity can be more
    > challenging because there is no central authority overseeing
    > operations.

3)  **Example Use Cases**

-   **File-sharing networks** (BitTorrent, eMule) where users download
    > and upload files directly to and from other users.

-   **Cryptocurrency networks** (Bitcoin, Ethereum) where transactions
    > are verified by a distributed network of computers.

-   **Decentralized messaging apps** that do not rely on a central
    > server to relay messages.

  -----------------------------------------------------------------------
  **Feature**             **Client-Server Model** **Peer-to-Peer (P2P)
                                                  Model**
  ----------------------- ----------------------- -----------------------
  Structure               Centralized             Distributed

  Control                 Managed by a single     Shared responsibility
                          server                  among peers

  Scalability             Limited by server       More scalable as more
                          capacity                peers join

  Reliability             Server failure can take More resilient, as
                          down the network        peers can continue
                                                  functioning

  Security                Easier to secure with   Harder to manage, as
                          centralized management  there is no central
                                                  authority
  -----------------------------------------------------------------------
