# 📝 MY_WORK: Student Information, Development Log, Reflection & Answers

> This is the **only file** your instructor reads to grade Parts 3 and 4 (documentation and video). Everything you write here must be **in your own words**.

---

## 🛑 STOP: Read This Before You Do Anything Else

> ### 1️⃣ Read the whole `README.md` first
> The `README.md` in this repository contains the full instructions: how this assignment continues Assignment 1, the Chapter 5 recap, class descriptions, feature specifications, question prompts and the video script. **If you skip it, you will lose marks.**
>
> ### 2️⃣ Understand the full code before answering any question
> Open `SchedulerSimulationSync.java` and read it **from top to bottom**. You must be able to explain what `SharedStats`, `ReadyQueue`, `CpuWorker`, `RaceWindow.pause()`, `ReentrantLock` and `Semaphore` do **before** you write a single answer in Parts B and C. **Run the original starter first** (it is intentionally broken) and **save its output**: you need it for Question 1 of Part C.
>
> ### 3️⃣ Use only the code of this repository
> Work **only** on `SchedulerSimulationSync.java` from this repository. Do **not** copy or paste code from your previous assignments.
>
> ### 4️⃣ Commit many times, not once
> A single commit, or all commits made in the last hour, costs you **-0.5 mark**. See the [Commit Rules](#-commit-rules-mandatory) below.

**How to use this file:**
1. Fill in your **Student Information** (below) right now.
2. Follow the steps in the **Work Roadmap** in order.
3. Update the **Development Log** *every time* you work on the assignment, not at the end.
4. Do not delete any section header. Replace the `[...]` placeholders with your own text.

---

## 👤 Student Information

> ⚠️ **WARNING:** Fill this in first. Your name and ID must match the student ID you set in `SchedulerSimulationSync.java` (line 304) and the one you say in your video.

| Field | Your Answer |
|-------|-------------|
| **Full Name** | [Omar Mohammed Al-Sahly] |
| **Student ID** | [444050133] |
| **University Email** | [444050133]@std.psau.edu.sa |
| **GitHub Username** | [OmarM66] |
| **Repository Link** | [https://github.com/OmarM66/OS-Assignment3-Omar-AlSahly.git] |
 
---

## 🎥 Video Link

**Video Link**: [https://drive.google.com/file/d/1DScSjjMfozYVgCoLtJwcZ-KvpaAU2LNZ/view?usp=sharing]

> ⚠️ **WARNING:** The video must be **publicly accessible** ("Anyone with the link can view") on **Google Drive**, **YouTube (Unlisted or Public)** or any other cloud file-sharing system. A private, restricted or broken link counts as a **missing video (-1 mark)**.
>
> 💡 **TIP:** Open the link in a **private/incognito window** before you submit. If it asks you to log in or request access, it is not public.
>
> 📌 **NOTE:** The link goes in **this file only** (`MY_WORK.md`), **not** in `README.md`. Name your video file `StudentID_Assignment3_Demo.mp4`. It must last **2 to 3 minutes**.

---

## 🗺️ Work Roadmap (follow in this order)

| Step | What to do | Where | Marks |
|:----:|------------|-------|:-----:|
| 0 | Read `README.md`, read the full code, **run the original starter and save its output** (it fails on purpose) | Your IDE | – |
| 1 | Fork, rename, keep the repo **PUBLIC**, set your student ID (line 304), **commit** | GitHub + code | Part 1 (1) |
| 2 | Feature 1: Mutex lock on the ready queue, **commit** | Code | Part 2 (0.25) |
| 3 | Feature 2: Mutex lock(s) on the shared statistics, **commit** | Code | Part 2 (0.25) |
| 4 | Feature 3: Counting semaphore instead of busy waiting, **commit** | Code | Part 2 (0.5) |
| 5 | Development Log (5+ entries, different dates) | This file, Part A | Part 3 (0.5) |
| 6 | Reflection (4 questions) | This file, Part B | Part 3 (0.5) |
| 7 | Technical Answers (4 questions) | This file, Part C | Part 3 (0.5) |
| 8 | Record the video, upload it, paste the link above | Video + this file | Part 4 (1.5) |
| 9 | Final check, then submit the repo link on Blackboard | Blackboard | – |

> 💡 **TIP:** Tick each step off as you go. Do not leave the log, the reflection or the video for the last day.

---

## 🔁 Commit Rules (MANDATORY)

> ### ⚠️ MANY COMMITS ARE REQUIRED. A single bulk commit is penalized (-0.5 mark).

**Minimum: 4 meaningful commits. Aim for 7 or more.**

| # | Commit | Example message |
|:-:|--------|-----------------|
| 1 | Student ID set | `Set my student ID: 441234567` |
| 2 | Feature 1: Ready queue lock | `Feature 1: Protected the ready queue with a ReentrantLock` |
| 3 | Feature 2: Statistics locks | `Feature 2: Added locks to the shared statistics counters` |
| 4 | Feature 3: Semaphore | `Feature 3: Replaced busy waiting with a counting semaphore` |
| 5 | Development log entries | `Docs: Added development log entries 1-3` |
| 6 | Reflection and answers | `Docs: Completed reflection and technical answers` |
| 7 | Video link | `Docs: Added demo video link` |

**Rules:**
- ✅ **One commit per feature.** Do not put all three features in one commit.
- ✅ **Commit after each work session**, and after each part of this file.
- ✅ **Spread your commits over different dates.** Not all in one day.
- ❌ **Do not make all commits in the last hour** before the deadline (November 14, 2026).
- ❌ **No vague messages** like `done`, `update` or `final version`.

> 💡 **TIP:** Your commit history is checked and you **show it in your video** (at least 4 commits visible). Your development log dates should match your commit dates.
>
> 💡 **TIP:** **Use VS Code** (see *Recommended Development Environment* in `README.md` for the full setup). Sign in to GitHub in VS Code, then commit from the Source Control panel (Ctrl+Shift+G) → stage → write a message → Commit → Sync/Push. You can edit and commit this file the same way. **Pushing** matters: commits that are not pushed to GitHub are invisible to the instructor.

---

# Part A: Development Log (0.5 mark)

> ⚠️ **WARNING:** Minimum **5 entries**, spread over **different dates**. Five entries written on the same day, or written all at once at the end, will lose marks and look like a copy. Entry dates should be **between the start of the assignment and the deadline (November 14, 2026)**.
>
> 💡 **TIP:** Write an entry at the **end of each work session**, while you still remember what happened. It takes 5 minutes.
>
> 💡 **TIP:** Be specific. "Worked on the code" is a weak entry. "Added a `ReentrantLock queueLock` to `ReadyQueue` and wrapped the body of `poll()` in `lock()` / `try` / `finally { unlock() }`" is a strong one.
>
> 📌 **NOTE:** Each entry needs: date and time, what you did, details, challenges, solution, and time spent. Real challenges are fine (and expected). Do not invent fake ones.

## Example Entry (do not copy it, write your own)

### Entry 1 - [November 2, 2026, 4:30 PM]
**What I did**: Forked the repository, set my student ID, and ran the original starter

**Details**:
- Forked the starter repository and renamed it
- Changed student ID on line 304 to my actual ID (441234567)
- Ran the original program: 4 CPUs started, three of them picked `P1`, then `IllegalThreadStateException` and the watchdog stopped the program
- Saved the output in a text file for Question 1
- Committed and pushed: `Set my student ID: 441234567`

**Challenges**: I did not understand why the same process was picked by three CPUs

**Solution**: Read `ReadyQueue.poll()` again and found the `RaceWindow.pause()` between reading the head and removing it

**Time spent**: 45 minutes

---

## Your Development Log

### Entry 1 - [November 13, 2026, 12pm]
**What I did**:
examined the initial synchronization issue and went over the startup code.
**Details**:
Read the main classes, paying particular attention to CpuWorker, SharedStats, and ReadyQueue.

used student ID 444050133 to run the original scheduler.

With two CPUs and a 4000 ms time quantum, the simulation generated eighteen processes.

A NullPointerException occurred in ReadyQueue.snapshot() for both CPU threads.

The original output was saved for use in Part C.
**Challenges**:
I had to figure out why both CPU threads were accessing the same queue because the application broke before any processes were finished.
**Solution**:
I looked at the RaceWindow and the shared RaceWindow.pause() function. I discovered that mutual exclusion was necessary for queue access.
**Time spent**:
45m
---

### Entry 2 - [November 13, 2026, 4pm]
**What I did**:
ReentrantLock was used to implement Feature 1 for the shared ready queue.
**Details**:
Java.util.concurrent.locks was imported.ReentrantLock.

queueLock was declared inside ReadyQueue.

Add(), poll(), processOf(), and snapshot() are protected.

To release the lock, use try/finally.

RaceWindow.pause() was left in the original code.
**Challenges**:
I had to safeguard the queue without altering the Round Robin scheduler's operation.

**Solution**:
I used one `ReentrantLock` named `queueLock` to secure both the `LinkedList` and the process map because they belong to the same shared ready queue. I also used `try/finally` to make sure the lock is always released after each crucial section.
**Time spent**:
1hour
---

### Entry 3 - [ November 13, 2026, 11pm]
**What I did**:
Feature 2 was put into practice to synchronize shared statistics.
**Details**:
ContextLock, completedLock, and serviceLock were added.

safeguarded the three techniques for updating shared statistics.

safeguarded the three matching getter techniques.

retained RaceWindow and the current read-modify-write functions.calls to pause().
**Challenges**:
I needed to choose between one shared lock and three independent locks.
**Solution**:
I used one lock per statistic because the counters are independent and can be updated without unnecessarily blocking each other.
**Time spent**:
1hour
---

### Entry 4 - [November 14, 2026, 3am]
**What I did**:
After modifying Features 1 and 2, Java compilation issues were debugged.
**Details**:
examined the mistakes displayed in Visual Studio Code.

After SharedStats, a missing closure brace was discovered.

A duplicate print statement and an additional brace following ReadyQueue.add() were eliminated.

After ReadyQueue.snapshot(), the missing closing brace was added.

Before proceeding, the class boundaries were reviewed.
**Challenges**:
Even though their locking declarations seemed to be accurate, a number of methods were highlighted in red.
**Solution**:
I discovered that the class structure was off when I looked at the opening and closing braces. The structural issue was fixed by fixing the braces and eliminating the redundant code.
**Time spent**:
40min
---

### Entry 5 - [November 14, 2026,5AM]
**What I did**:
Feature 3 was implemented, and the final synchronization mechanism was examined.
**Details**:
Java.util.concurrent was imported.Semaphore.

Initially, readyCount was set to zero.

After adding a process to the ready queue, release() was added.

used a blocking acquire() in place of the CPU's polling loop.

Release (totalCPUs) was used to add a shutdown signal.

examined each of the four statistics' verification standards.
**Challenges**:
After the last process is finished, a CPU that is waiting on a semaphore may stay blocked indefinitely.
**Solution**:
In order to wake up the CPU workers and allow them to terminate, I introduced a shutdown signal.
**Time spent**:
1hour
---

### Entry 6 - [Optional - Date and Time]
**What I did**:

**Details**:

**Challenges**:

**Solution**:

**Time spent**:

---

## Development Log Summary

> 💡 **TIP:** Fill this in **last**, after all entries are written.

**Total time spent on assignment**: [X hours]
5 hours
**Most challenging part**:
Debugging the Java class hierarchy after implementing synchronization and comprehending how concurrent CPU threads interact.
**Most interesting learning**:
I learned how mutex locks protect shared data and how a counting semaphore allows threads to wait efficiently instead of repeatedly polling an empty queue.
**What I would do differently next time**:
 I would make smaller edits, compile after each change, and keep my development log updated during each work session rather than reconstructing it later.
---

# Part B: Reflection (0.5 mark)

> 🛑 **STOP:** Do **not** start this part until you have read the `README.md`, read the **entire** `SchedulerSimulationSync.java`, run it, and finished the three features.
>
> ⚠️ **WARNING:** Each answer must be **5 to 7 sentences**, in **your own words**. Copied or AI-generated answers without understanding get **0 marks for the whole assignment**. You may be asked to explain them in person.
>
> 💡 **TIP:** Mention concrete things you actually did: a method you wrote, an error you hit, a line of output you saw. Generic answers score low.
>
> 💡 **TIP:** Draft your answer in a few bullet points first, then turn them into sentences.

## Question 1: What did you learn about synchronization?
> 💡 **TIP:** Talk about race conditions (read-modify-write), critical sections, mutual exclusion with `ReentrantLock` and `try/finally`, the role of a counting semaphore, and what surprised you when the starter failed.

**Your Answer:** *(5-7 sentences)*

[I discovered that when several threads access the same shared data, synchronization is crucial. A race issue could result from two CPU threads accessing the ready queue simultaneously in the original scheduler. To safeguard important areas and ensure that only one thread changed the queue at a time, I utilized ReentrantLock. I also discovered the significance of try/finally, which guaranties that the lock is released even in the event of an error. To avoid lost updates, I used different locks for the shared statistics. At last, I discovered that a counting semaphore can effectively stop a CPU until a process is ready.]

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

[The most challenging part was debugging the code after adding the synchronization features. At first, VS Code showed errors under methods such as poll() and processOf(), which made me think the locking code was incorrect. After checking the file structure, I found missing and extra closing braces and a duplicated statement. These mistakes caused some classes to appear inside other classes. I also had to understand how the semaphore would allow the CPUs to stop correctly after all processes finished. This assignment showed me that both Java syntax and thread synchronization need careful attention.]

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

[I started by reviewing the original scheduler and identifying which variables were shared between threads. I then worked on the synchronization features separately instead of changing the entire program at once. When I encountered compilation errors, I checked the affected methods and the opening and closing braces around the classes. I corrected the duplicated code and missing braces before continuing with the semaphore. I also compared the verification results with the expected values generated from my student ID. This approach helped me understand the source of each problem and the purpose of each modification.]

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

[Synchronization is useful in banking applications where several transactions may update the same account balance. A mutex lock can prevent two transactions from changing the same balance at the same time. It is also important in ticket booking systems because two customers should not reserve the same seat. Semaphores can be used in systems where workers wait for new tasks, such as print queues or background job processing. This is similar to my scheduler, where CPU workers wait until processes become available in the ready queue. Synchronization helps these systems maintain correct data and coordinate concurrent operations.]

### Optional: What would you like to learn more about?

[]

### Optional: How confident do you feel about synchronization concepts now?

[Beginner / Intermediate / Confident. What do you understand well? What needs more practice?]

### Optional: Feedback on the assignment

[Any comments? Was it helpful? Too easy or hard? Suggestions?]

---

# Part C: Technical Answers (0.5 mark)

> 🛑 **STOP:** You cannot answer these questions without understanding the code. Re-read `SchedulerSimulationSync.java` and **run it** first. Your answers must reference **your own code and your own output** (your student ID makes your output and your expected values unique).
>
> ⚠️ **WARNING:** Each answer must be **3 to 5 sentences**, with specific examples from your code or output. Use correct terms: race condition, critical section, mutual exclusion, mutex lock, semaphore, busy waiting, deadlock, producer, consumer.
>
> 💡 **TIP:** Keep the output of the **original starter** and the output of your **final version** in text files or screenshots, so you can copy real snippets for Question 1.

## Question 1: Race Condition in Your Own Output

**Question**: Run the **original starter** (before any fix) and paste the **verification block** of that run. Which value was wrong (expected vs observed)? Explain **step by step**, with two named threads/CPUs, how **one lost update** happens on one of the shared variables (read, `RaceWindow.pause()`, write). Why can the same bug happen on a real machine even without `RaceWindow`, and why is it hard to detect?

> ⚠️ **WARNING:** The snippet must come from **your own run** (with your student ID), not from a classmate or from this README.
>
> 💡 **TIP:** Use a small timeline: *CPU-1 reads `contextSwitchCount` = 12 → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13 → one increment is lost.* If your starter run crashed before printing numbers, run it several times (or paste the exception and the watchdog message and explain it).

**Your Answer:** *(3-5 sentences)*

[In my original run, both CPUs crashed with a NullPointerException in ReadyQueue.snapshot() because of a race condition. The expected values were 35 context switches, 18 completed processes, and 100874 ms of service time, but all three observed values were 0. A lost update can happen when two CPUs read the same counter before writing, even without RaceWindow.pause(), making the bug difficult to reproduce.]

Verification block of the **original starter**:
```
[Exception in thread "CPU-2" java.lang.NullPointerException:
Cannot read field "next" because "this.next" is null
    at ReadyQueue.snapshot(SchedulerSimulationSync.java:151)
    at CpuWorker.run(SchedulerSimulationSync.java:280)

Exception in thread "CPU-1" java.lang.NullPointerException:
Cannot read field "next" because "this.next" is null
    at ReadyQueue.snapshot(SchedulerSimulationSync.java:151)
    at CpuWorker.run(SchedulerSimulationSync.java:280)

Context switches (quanta executed)  expected 35      observed 0       MISMATCH
Completed processes                expected 18      observed 0       MISMATCH
Total service time (ms)            expected 100874  observed 0       MISMATCH
Busy-waiting polls (must be 0)     expected 0       observed 0       PASS]
```

Verification block of **my final version**:
```
[Context switches (quanta executed)     expected 35       observed 35       ✔
Completed processes                    expected 18       observed 18       ✔
Total service time (ms)                expected 100874   observed 100874   ✔
Busy-waiting polls (must be 0)         expected 0        observed 0        ✔
✔ All shared values are consistent.]
```

**Explanation of the timeline:**
[CPU-1 reads contextSwitchCount = 12 → RaceWindow.pause() → CPU-2 reads 12 → CPU-1 writes 13 → CPU-2 writes 13. The correct result should be 14, but one increment is lost.]

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

[I used queueLock to protect the ready queue methods and three separate locks (contextLock, completedLock, and serviceLock) to protect the statistics. Separate locks allow independent updates and reduce unnecessary blocking, but they require more careful management; lock() and unlock() provide mutual exclusion and help threads make progress. However, the default ReentrantLock is non-fair, so bounded waiting is not guaranteed.]

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()` | `queueLock` | Protects adding processes to the queue. |
| `ReadyQueue.poll()` | `queueLock` | Prevents multiple CPUs from removing the same process. |
| `ReadyQueue.processOf()` | `queueLock` | Protects access to the shared process map. |
| `ReadyQueue.snapshot()` | `queueLock` | Prevents concurrent changes while reading the queue. |
| `contextSwitchCount` | `contextLock` | Prevents lost updates to context switches. |
| `completedCount` | `completedLock` | Prevents lost updates to completed processes. |
| `totalServiceTime` | `serviceLock` | Prevents lost updates to service time. |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

[The starter repeatedly checked the empty queue and slept for 20 ms, wasting CPU time; my original run showed 0 busy-waiting polls because both CPUs crashed early. I replaced this with Semaphore(0), where permits represent available processes, so after the initial 18 additions the semaphore has 18 permits and CPUs block on acquire() when none are available. Finally, release(totalCPUs) wakes blocked CPUs after completion to prevent them from waiting forever.]

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*
This scheduler represents the producer-consumer problem: the main thread adds processes, and CPU workers consume and sometimes re-enqueue them. For a bounded queue of capacity K, the semaphores are empty = K, full = 0, and mutex = 1. A deadlock could happen if a producer holds mutex while waiting for empty and the consumer cannot acquire mutex, so acquiring empty first breaks the hold-and-wait condition.
**Classical problem and roles**:
[This is the producer-consumer problem. The main thread is the producer, while CPU workers are consumers that can also re-enqueue unfinished processes.]

**Semaphores for a bounded queue (name and initial value)**:
[empty = K

full = 0

mutex = 1]

**Deadlock scenario and prevention**:
[A deadlock can occur if a producer holds mutex while waiting for empty, preventing a consumer from accessing the queue. Acquiring empty before mutex prevents this situation by avoiding hold-and-wait.]

## Summary

**Key concepts I understood through these questions:**
1.Race conditions and lost updates.
2.Mutual exclusion using ReentrantLock.
3.Avoiding busy waiting using semaphores.

**Concepts I need to study more:**
1.Fairness and bounded waiting.
2.Deadlock prevention.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [ ] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [ ] GitHub account uses the university email (`@std.psau.edu.sa`)

**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [ ] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [ ] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [ ] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [ ] **The four verification lines are ✔ in 5 consecutive runs**
- [ ] Every lock is released in a `finally` block
- [ ] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [ ] Each feature has clear comments

**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [ ] **One commit per feature**
- [ ] Commits are spread over **different dates** (not all in the last hour)
- [ ] Everything is **pushed** to GitHub

**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [ ] Development log has **5+ entries** on different dates
- [ ] Reflection: 4 questions, 5-7 sentences each
- [ ] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [ ] No `[...]` placeholders left
- [ ] No section headers deleted

**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository

> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
