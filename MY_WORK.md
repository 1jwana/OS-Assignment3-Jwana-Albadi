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
| **Full Name** | Jwana Albadi |
| **Student ID** | 445052167 |
| **University Email** | 445052167@std.psau.edu.sa |
| **GitHub Username** | 1jwana |
| **Repository Link** | https://github.com/1jwana/OS-Assignment3-Jwana-Albadi |
 
---

## 🎥 Video Link

**Video Link**: [Paste your video link here]

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

### Entry 1 - [November 03, 2026, 11:20 AM]
**What I did**: Set my student ID and checked the original program.

**Details**:
- Forked the instructor's starter repository for my own assignment.
- Set `studentID` to `445052167`, so the simulation uses the values linked to my ID.
- Saved the original run showing 11 processes, four CPUs, and a 4000 ms time quantum.
- The starter stopped with a `NullPointerException` inside `ReadyQueue.snapshot()` and did not complete the processes.
- Committed the change as `Set my student ID: 445052167`.

**Challenges**: The program started four CPU threads but failed before any process finished. I needed to understand whether the problem came from the ready queue or from the process code.

**Solution**: I kept the original output and checked the queue methods in the starter code. The shared `list` and `map` did not have a lock, so I planned to protect those operations in Feature 1.

**Time spent**: 30 minutes

---

### Entry 2 - [November 03, 2026, 03:47 PM]
**What I did**: Added a mutex lock to the ready queue.

**Details**:
- Added `queueLock` to `ReadyQueue` using `ReentrantLock`.
- Protected `add()`, `poll()`, `processOf()`, and `snapshot()` with `lock()` and `try/finally`.
- In the Feature 1 run, the simulation completed 11 processes, but only 18 of 22 expected context switches were recorded, and busy-waiting polls reached 96.
- Committed the work as `Feature 1: Protect the shared ready queue`.

**Challenges**: The queue has both a list and a map, so protecting only the removal step would not be enough. The result also showed that fixing the queue did not fix the shared counters or busy waiting.

**Solution**: I used the same queue lock around every method that reads or changes those collections. I left the other synchronization problems for their own features.

**Time spent**: 40 mintues

---

### Entry 3 - [November 04, 2026, 06:17 PM]
**What I did**: Protected the shared statistics.

**Details**:
- Declared one `statsLock` for `contextSwitchCount`, `completedProcessCount`, and `totalServiceTime`.
- Used this lock in all three update methods and their three getters.
- The  Feature 2 run showed 22/22 context switches, 11/11 completed processes, and 66,646/66,646 ms of service time, but it still recorded 85 busy-waiting polls.
- Committed the work as `Feature 2: Lock the shared statistics`.

**Challenges**: Several process threads update the same counters. I also needed to protect the getters because they read values that other threads might be changing.

**Solution**: I chose one statistics lock because it is simple to follow and protects each complete read or update. I checked the verification output and confirmed that the three statistics matched their expected values.

**Time spent**: 40 minutes

---

### Entry 4 - [November 07, 2026, 10:25 PM]
**What I did**: Replaced busy waiting with a counting semaphore.

**Details**:
- Added `readyCount` as `new Semaphore(0)` in `ReadyQueue`.
- Called `release()` after a process was added and `acquire()` before a CPU tried to take a process.
- Added the final wake-up in `wakeWaitingCPUs()` so blocked CPUs can stop after all work is finished.
- The  final run reached 22/22 context switches, 11/11 completed processes, 66,646/66,646 ms of service time, and zero busy-waiting polls.
- Committed the work as `Feature 3: Replace busy waiting with semaphore`.

**Challenges**: Waiting on a semaphore solves repeated polling, but a CPU may remain blocked when the queue becomes empty at the end of the simulation.

**Solution**: The last finishing CPU releases enough permits to wake the waiting workers. Each worker checks the completed-process count before trying to remove another item.

**Time spent**: 40 minutes

---

### Entry 5 - [November 09, 2026, 05:24 PM]
**What I did**: Reviewed my saved runs and completed the written explanation.

**Details**:
- Compared the original, Feature 1, Feature 2, and final verification results.
- Explained the original queue failure.
- Updated the MY_WORK.md file and added some comments to the code.

**Challenges**: The original run crashed before any context switches were counted, so it could not show a measured lost-counter update.
Some questions needed more understanding fomromm me to be answerd correctly.
**Solution**: I used the recorded failure values for the evidence and explained the possible lost update as an example, without treating it as a measured result.
used intenet sonline resources to learn moreand  and sanswer the quesitons.
**Time spent**: [Enter the actual time for this session.]
1100 minutes
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

**Total time spent on assignment**: [Add the total after confirming the actual time for all work sessions.]
 250 minutes that is 4.2 hours
**Most challenging part**: Understanding the ready-queue error and making sure all four queue operations used the same lock.

**Most interesting learning**: A program can fix its shared values and still waste time checking an empty queue, so the semaphore is needed as well.

**What I would do differently next time**: I would compare the expected and observed values after every small change and keep notes during each session.

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

Before this assignment, I did not fully understand what could go wrong when several CPUs share one queue. In the original run, the program stopped with a `NullPointerException` because the queue operations were not protected. I learned that a race condition can happen when two threads read or change shared data at almost the same time. A `ReentrantLock` protects a critical section so only one thread can use it at a time. I used `try/finally` because the lock must be released even if the method has a problem. I also learned that a semaphore lets a CPU wait for an available process without checking the empty queue again and again.

## Question 2: What was the most challenging part of this assignment?

> 💡 **TIP:** Pick **one** specific challenge (understanding why the starter failed, choosing the lock granularity, the initial value of the semaphore, the shutdown of the CPUs, Git, the video) and say *why* it was hard.

**Your Answer:** *(5-7 sentences)*

The hardest part for me was understanding why the ready queue failed in the first run. I saw the error message, but it did not clearly tell me which shared operation caused the problem. The `poll()` method reads and removes the first item, while other CPUs can use the queue at the same time. I also needed to remember that `snapshot()` reads the same shared collections. If only `poll()` had a lock, another method could still access the list during a change. This helped me understand why all four ready-queue methods needed the same lock.

## Question 3: How did you overcome the challenges you faced?

> 💡 **TIP:** Describe your method: reading the slides and the documentation, adding `System.out.println` to debug, running the program many times, re-reading the README, testing after each small change, asking for help.

**Your Answer:** *(5-7 sentences)*

I worked on the three features in order instead of changing the whole program at once. I saved the output after each stage and compared the observed values with the expected values. After Feature 1, the program completed all 11 processes, but the context-switch count and service-time total were still wrong. I added `statsLock` to the counter methods, and the next output showed that all three statistics were correct. There were still 85 busy-waiting polls, so I changed the CPU loop to use `readyCount.acquire()`. In the final output, all four checks matched, including zero busy-waiting polls.

## Question 4: Where can synchronization concepts be applied in real-world applications?

> 💡 **TIP:** Use real applications you know (banking and money transfers, ticket or seat booking, a shared counter on a website, a print queue, a database) and connect each one to what you built here (shared data, critical section, lock or semaphore).

**Your Answer:** *(5-7 sentences)*

Synchronization is useful in online ticket booking systems where many people may request the same seat. If two users try to reserve the last available seat, the system must not confirm both bookings. A lock can protect the step that checks and updates seat availability. It is also useful in a print service where several workers take jobs from one shared queue. Each print job should be taken by only one worker, just like a process in this scheduler. A semaphore can make a worker wait until a new print job is available instead of checking the queue repeatedly.

### Optional: What would you like to learn more about?

I would like to learn more about fair locks and how a waiting thread gets its turn.

### Optional: How confident do you feel about synchronization concepts now?

Intermediate. I understand basic mutex locks and semaphores, but I need more practice with deadlock and bounded waiting.

### Optional: Feedback on the assignment

The different verification results were useful because I could see what each feature fixed. The first queue error was difficult, but checking the methods and output helped.

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

My original starter run stopped with a `NullPointerException` in `ReadyQueue.snapshot()`, and the verification showed 0 observed context switches instead of 22, 0 completed processes instead of 11, and 0 service-time milliseconds instead of 66,646. These numbers show that the program failed before normal execution, rather than proving a lost counter update in that specific run. As an example of a possible lost update, CPU-1 can read `contextSwitchCount = 7`, and CPU-2 can read the same value during `RaceWindow.pause()`. If both CPUs write 8, the correct value of 9 is lost because the read-and-write steps were not protected. This race can also happen without the added pause because the operating system can switch threads at an unexpected time, so the error may not happen in every run.

Verification block of the **original starter**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 22       observed 0        ? MISMATCH
  Completed processes                    expected 11       observed 0        ? MISMATCH
  Total service time (ms)                expected 66646    observed 0        ? MISMATCH
  Busy-waiting polls (must be 0)         expected 0        observed 0        ?
  ? At least one check failed (see the ? lines above): a race condition or busy waiting is still present.
```

Verification block of **my final version**:
```
═══ VERIFICATION (expected values are computed from YOUR seed) ═══
  Context switches (quanta executed)     expected 22       observed 22       ?
  Completed processes                    expected 11       observed 11       ?
  Total service time (ms)                expected 66646    observed 66646    ?
  Busy-waiting polls (must be 0)         expected 0        observed 0        ?
  ? All shared values are consistent.
```

**Explanation of the timeline:**
Possible timeline for `contextSwitchCount` (illustrative example, not a recorded value):
:
1. CPU-1 reads `7` from the counter.
2. CPU-1 reaches `RaceWindow.pause()` and CPU-2 also reads `7`.
3. CPU-1 writes `8`, then CPU-2 also writes `8`.
4. Two increments should have produced `9`, but the counter stays at `8`.

## Question 2: Critical Sections and Lock Granularity

**Question**: List the **critical sections** you protected (variables and methods) and the lock(s) you used. **Lock granularity:** did you use **one lock** for the three statistics or **one lock per variable**? Why, and what is the trade-off? Why is the **ready queue** protected by a **different** lock than the statistics? Explain how your solution provides **mutual exclusion**, and discuss **progress** and **bounded waiting** (a default `ReentrantLock` is not fair: what does that imply?).

> 💡 **TIP:** The three counters are independent: does updating `contextSwitchCount` need to block an update of `totalServiceTime`? Also think about what could go wrong (deadlock, or long waiting) if the queue lock and the statistics lock were the **same** lock and a thread held it while doing something slow.

**Your Answer:** *(3-5 sentences)*

I used `queueLock` in `ReadyQueue.add()`, `poll()`, `processOf()`, and `snapshot()` to protect the shared list and map. I used one `statsLock` for the three counters and all their update and getter methods, because it is easy to manage and keeps each read or update safe, although independent counters may have to wait for each other. The queue has a different lock so a thread using the queue does not block every statistics operation. Calling `unlock()` in `finally` gives other threads a chance to continue and the locks provide mutual exclusion, helping the program make progress. However, the default `ReentrantLock` is not fair, so a waiting thread is not promised a turn within a fixed time and bounded waiting is not guaranteed.

| Critical section (variable / method) | Lock used | Why it needs protection |
|---|---|---|
| `ReadyQueue.add()` and `ReadyQueue.poll()` | `queueLock` | A process must be inserted or removed without another CPU changing the queue at the same time. |
| `ReadyQueue.processOf()` and `ReadyQueue.snapshot()` | `queueLock` | Read the shared map and list safely while other CPUs may be using them. |
| `incrementContextSwitch()` / `getContextSwitchCount()` | `statsLock` | Protect the context-switch count during updates and reads. |
| `incrementCompletedProcess()` / `getCompletedProcessCount()` | `statsLock` | Avoid lost completion updates and protect reads. |
| `addServiceTime()` / `getTotalServiceTime()` | `statsLock` | Keep the total executed service time correct. |

## Question 3: Busy Waiting vs Semaphore

**Question**: Describe the **busy waiting** of the starter and its cost (give the `Busy-waiting polls` number from your **starter** run). What does the **value of your semaphore** represent? What is its **initial value** and why? What is its value right after the `numProcesses` initial `add()` calls? Why does the last CPU call `release(totalCPUs)` at the end, and what would happen if it did not?

> 💡 **TIP:** Think about what a CPU does when the queue is empty in the starter, and what a CPU does in your final version (is it running, ready or blocked?). Also check what happens to a CPU blocked in `acquire()` when no process will ever be added again.

**Your Answer:** *(3-5 sentences)*

The starter crashed before it could poll the queue again, so that run showed 0 busy-waiting polls, but the Feature 1 and Feature 2 runs recorded 96 and 85 polls, which means CPUs were still checking for work repeatedly. The `readyCount` semaphore starts at 0 because no processes have been added, and after the first 11 calls to `add()` it has 11 permits before any CPU begins taking them. Each new queued process calls `release()`, while a CPU calls `acquire()` to block until a permit is available rather than wasting time on repeated checks. When the last process finishes, `wakeWaitingCPUs()` releases `totalCPUs` permits so waiting CPUs can wake up and check that all work is done. Without those final permits, some CPUs could stay blocked in `acquire()` and the simulation might fail to terminate.

## Question 4: Classical Problems and Deadlock

**Question**: The CPUs and the ready queue look like a classical synchronization problem of Chapter 5. **Name it**, and say who plays the **producer** and the **consumer** roles (careful: here the CPUs also re-enqueue processes). If the ready queue were **bounded** (capacity `K`), name the **three semaphores** you would need and their **initial values**. Describe a **deadlock scenario** that appears if a thread acquired the **mutex before** waiting on the semaphore (or if two locks were acquired in different orders), and say **which of the four necessary conditions** you would break to prevent it.

> 💡 **TIP:** Recall the bounded-buffer solution of the slides (`empty`, `full`, `mutex`) and the order of `wait()` calls in the producer and the consumer. For the deadlock, think about a producer that holds the mutex while waiting for a free slot that only a consumer (who needs the mutex) can create.

**Your Answer:** *(3-5 sentences)*

**Classical problem and roles**:
The program follows the **producer-consumer problem**, because processes are placed in a shared ready queue and CPU workers take them for execution. The main thread is the first producer, the CPU workers are consumers, and a CPU also acts as a producer when it puts an unfinished process back into the queue.

**Semaphores for a bounded queue (name and initial value)**:
For a ready queue with capacity `K`, the three semaphores would be `empty = K` for free spaces, `full = 0` for waiting processes, and `mutex = 1` for exclusive queue access.

**Deadlock scenario and prevention**:
Deadlock could happen if a CPU takes `mutex` and then waits on `full` while the queue is empty, because the producer cannot take `mutex` to add a process and signal `full`. To prevent this, the CPU must wait on `full` before taking `mutex`, which prevents it from **holding one resource while waiting** for another and breaks the **hold-and-wait** condition in this example.

## Summary

**Key concepts I understood through these questions:**
1. Protecting the ready queue with a mutex lock.
2. Preventing lost updates in the shared statistics.
3. Using a semaphore to wait for processes and to stop CPU workers safely.

**Concepts I need to study more:**
1. Fair locks and bounded waiting.
2. More examples of deadlock prevention.

---

# ✅ Final Checklist (complete before submitting)

> ⚠️ **WARNING:** Go through every line. Blackboard does not accept submissions after the deadline, which is **November 14, 2026**.

**Repository**
- [ ] Repository is **PUBLIC** (Settings → Danger Zone → Visibility)
- [x] Repository is renamed to `OS-Assignment3-YourFirstName-YourLastName`
- [x] GitHub account uses the university email (`@std.psau.edu.sa`)
x
**Code**
- [ ] Student ID is set in `SchedulerSimulationSync.java` (line 304)
- [x] My code is based **only** on the starter of this repository (nothing copied from previous assignments)
- [x] Code compiles and runs with no errors, and terminates by itself (no `⛔ WATCHDOG`)
- [x] Feature 1 (ready queue lock), Feature 2 (statistics locks) and Feature 3 (semaphore, no busy waiting) all work
- [x] **The four verification lines are ✔ in 5 consecutive runs**
- [x] Every lock is released in a `finally` block
- [x] `RaceWindow`, `Config`, the verification block and the watchdog are **unchanged**
- [x] Each feature has clear comments
x
**Commits**
- [ ] **At least 4 meaningful commits, ideally 7 or more**
- [x] **One commit per feature**
- [x] Commits are spread over **different dates** (not all in the last hour)
- [x] Everything is **pushed** to GitHub
x
**This file (`MY_WORK.md`)**
- [ ] Full name and student ID filled in at the top
- [x] Development log has **5+ entries** on different dates
- [x] Reflection: 4 questions, 5-7 sentences each
- [x] Technical answers: 4 questions, 3-5 sentences each, with examples from **your** output (starter output **and** final output pasted in Question 1)
- [x] No `[...]` placeholders left
- [x] No section headers deleted
x
**Video**
- [ ] 2-3 minutes long, named `StudentID_Assignment3_Demo.mp4`
- [ ] Shows your name, ID, repository, 3 features (and your lock granularity choice), IDE execution with the verification block, one synchronization concept, and commit history
- [ ] Link is **public** (tested in an incognito window) and pasted in the **Video Link** section above

**Blackboard**
- [ ] Submit **only** the link to your public GitHub repository
x 
> 🎯 **Good luck!** Start early, commit regularly, and make sure you can explain every line you submit.
