In [Java](https://www.tpointtech.com/java-tutorial), a reentrant monitor is a synchronization technique that permits a thread to repeatedly enter the same synchronized region without stopping itself. Java uses both explicit locks like ReentrantLock and intrinsic locks (monitors) to accomplish this functionality. Reentrant refers to the ability of a thread to reacquire a lock without creating a [deadlock](https://www.tpointtech.com/deadlock-in-java).

Every object in Java serves as an implicit monitor, and additional locking tools like ReentrantLock or the [synchronized keyword](https://www.tpointtech.com/synchronized-keyword-in-java) are used to enforce [synchronization](https://www.tpointtech.com/synchronization-in-java). ReentrantLock is superior to intrinsic monitors in terms of flexibility, control, and fairness.

## Why It Is Called Reentrant?

A lock is reentrant because:

- As the same thread can obtain the same lock more than once, a lock is reentrant.
- A hold count rises with each acquisition.
- Only when the hold counts drops to zero is the lock unlocked.

When a synchronized method calls another synchronized method that utilizes the same lock internally, this feature is essential.

## Reentrant Monitor Vs. ReentrantLock

|Aspect|Intrinsic Monitor (synchronized)|ReentrantLock|
|---|---|---|
|**Lock type**|Implicit|Explicit|
|**Reentrancy**|Yes|Yes|
|**Fairness**|No control|Can be fair/unfair|
|**Lock timeout**|No|Yes (tryLock)|
|**Interruptible**|No|Yes|
|**Hold count access**|No|Yes (getHoldCount)|

## Working of Reentrant Monitor

A Reentrant Monitor works by tracking ownership and re-entries, allowing the same thread to repeatedly acquire a lock while blocking others until the lock is fully released.

**Lock Ownership:** In a reentrant monitor, a lock can only be owned by one thread at a time. A thread becomes the monitor owner and has exclusive access to the vital part when it obtains the lock.

**Re-entry Capability:** The monitor does not prevent the same thread from attempting to obtain the lock once more. Rather, the lock increments a hold count internally and permits re-entry.

**Hold Count Tracking:** The hold count is increased with each successful lock() call made by the owning thread. The number of times the thread has entered the monitor is indicated by this count.

**Mutual Exclusion:** All other threads are prohibited from accessing the monitor while one thread is the owner.

- Other threads either use tryLock() to fail instantly or lock() to wait.

**Fairness Control:** The monitor may be either fair or unfair by default. Fair mode ensures predictable scheduling by giving the lock to the thread that has been waiting the longest.

**Conditional Access:** A thread can try to enter the monitor without being blocked by using tryLock(). The thread keeps running without stopping if the monitor is busy.

**Monitor Exit:** The hold count is decreased by one for every unlock() call.

- Only when the hold count reaches 0 is the monitor released.

**Step 8- Lock Handover:** The monitor becomes accessible after it is released. In order to gain ownership, waiting threads either compete or are scheduled (depending on fairness).

**Internal Safety Guarantee:** The reentrant monitor ensures:

- No self-deadlock
- Safe nested method calls
- Controlled access to shared resources

## Mechanisms for Reentrant Monitors

Reentrant monitors operate internally through a series of synchronized procedures that guarantee proper lock release, preserve exclusive access, and enable a thread to securely re-enter a locked area. These features are implemented by Java in both explicit monitors (ReentrantLock) and intrinsic monitors (synchronized).

### Lock Ownership Tracking

**Fundamental Mechanism:** Each reentrant monitor keeps track of which thread is currently in possession of the lock. When a thread obtains the monitor, it is noted as the sole owner; until the lock is completely released, no other thread is permitted to access it.

**Why this is important?**

Ownership monitoring makes sure that only the owning thread is permitted to re-enter; all other threads are either blocked or denied.

### Hold Count Management

**Reentrancy-Enabling Mechanism:** The monitor increases an internal hold count each time the owning thread re-acquires the same lock. The number of times the thread has entered the protected area is indicated by this count.

**Key behaviour**

- First lock() → hold count = 1
- Every re-entry → hold count increases
- Lock is released only when count reaches zero

This mechanism prevents premature release of the monitor.

### Self-Reentry Validation

[**Deadlock Prevention**](https://www.tpointtech.com/os-deadlock-prevention) **Mechanism**

Before blocking a thread, the monitor checks:

Is the current thread already the owner?

- If yes, the monitor allows immediate re-entry instead of forcing the thread to wait.

**Why this is important?**

Self-deadlock happens when a thread tries to obtain a lock it already has, is avoided by this check.

## Mutual Exclusion Enforcement

### Concurrency Control Mechanism

While a thread owns the reentrant monitor:

- All other threads are denied access to the critical section
- The owner thread is the only one that can resume or continue running.

By doing this, shared resources are ensured to be thread-safe even when nested method calls are made.

### Queueing and Thread Suspension

**Contention Handling Mechanism**

When the same monitor is requested by several threads:

- A waiting queue is created for threads that are unable to obtain the lock.
- When a waiting thread can try acquisition again is determined by the monitor.

Contention is handled by this method without infringing on exclusive ownership.

### Fairness Policy Handling

**Scheduling Mechanism**

Reentrant monitors may operate in:

- Unfair mode - threads may acquire the lock out of order.
- Fair mode - longest-waiting thread is granted access first.

Fairness is implemented by managing the waiting queue in FIFO order.

## Lock Release Coordination

### Controlled Exit Mechanism

**Each unlock() call**

- Decrements the hold count by one
- Checks whether the count has reached zero

Only when the hold count becomes zero does the monitor

- Clear ownership
- Allow another waiting thread to acquire the lock

It ensures a clean and predictable handover.

### Condition Management (Advanced Mechanism)

**Thread Coordination Mechanism**

Reentrant monitors support condition variables that allow threads to:

- Release the lock for a little time.
- Wait for specific conditions
- Obtain the lock again after being informed

Advanced thread coordination is made possible in this way without compromising reentrancy.

### Memory Visibility Guarantees

**Consistency Mechanism:**

Reentrant monitors enforce happens-before relationships, ensuring that:

- Changes made by the owning thread are visible
- State is consistent when the lock is released and re-acquired

It prevents stale data access in concurrent execution.

### Interrupt and Timeout Awareness

**Responsiveness Mechanism**

Reentrant monitors that are explicit support:

- Lock acquisition that is interruptible
- Timed lock attempts

While waiting for the monitor, threads might continue to respond thanks to these techniques.

### Example: Basic Reentrant Behaviour (Same Thread Acquires Lock Multiple Times)

The same thread can obtain the same lock more than once without blocking, a phenomenon known as reentrancy. The internal hold count is increased with each lock() operation and may be seen with getHoldCount(). The monitor makes sure that the thread maintains ownership throughout calls to nested methods. Only when all relevant unlock() calls have been made is the lock fully freed.

### Example

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. import java.util.concurrent.locks.ReentrantLock;  
2. class Main {  
3.     // Explicit reentrant monitor  
4.     private static ReentrantLock lock = new ReentrantLock();  
5.     static void methodA() {  
6.         lock.lock(); // first acquisition  
7.         try {  
8.             System.out.println("Inside methodA");  
9.             methodB(); // same thread re-enters the lock  
10.         } finally {  
11.             lock.unlock(); // releases one hold  
12.         }  
13.     }  
14.     static void methodB() {  
15.         lock.lock(); // reentrant acquisition  
16.         try {  
17.             System.out.println("Inside methodB");  
18.             System.out.println("Hold Count: " + lock.getHoldCount());  
19.         } finally {  
20.             lock.unlock(); // releases second hold  
21.         }  
22.     }  
23.     public static void main(String[] args) {  
24.         methodA();  
25.     }  
26. }  

**Output:**

Inside methodA
Inside methodB
Hold Count: 2

### Example: tryLock() with Conditional Execution (Non-Blocking Monitor Access)

In this case, tryLock() makes the reentrant monitor accessible without blocking. In the event that the lock is already held, the thread proceeds straight to the alternate path without waiting. This keeps threads from suspending and is helpful in areas where performance is crucial. Using unlock(), the ownership of the monitor is explicitly handled and released.

### Example

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. import java.util.concurrent.locks.ReentrantLock;  
2. lass Main {  
3.    private static ReentrantLock lock = new ReentrantLock();  
4.    static void operation() {  
5.        // Attempts immediate lock acquisition  
6.        if (lock.tryLock()) {  
7.            try {  
8.                System.out.println("Lock acquired by thread");  
9.            } finally {  
10.                lock.unlock(); // mandatory release  
11.            }  
12.        } else {  
13.            System.out.println("Lock not acquired, skipping operation");  
14.        }  
15.    }  
16.    public static void main(String[] args) {  
17.        new Thread(Main::operation).start();  
18.        new Thread(Main::operation).start();  
19.    }  

**Output:**

Lock acquired by thread
Lock not acquired, skipping operation

### Example: Fair Reentrant Monitor (FIFO Lock Acquisition)

As this code use a fair reentrant monitor, threads are ensured to obtain the lock in FIFO order. By choosing the thread that has been waiting the longest, the fairness policy keeps people from going starved. Fairness ensures predictable scheduling even though it somewhat affects throughput. The owning thread still has complete reentrant access to the monitor.

### Example

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. import java.util.concurrent.locks.ReentrantLock;  
2. class Main {  
3.     // Fair monitor: threads acquire lock in waiting order  
4.     private static ReentrantLock lock = new ReentrantLock(true);  
5.     static void task() {  
6.         lock.lock(); // fair lock acquisition  
7.         try {  
8.             System.out.println(Thread.currentThread().getName() + " acquired lock");  
9.         } finally {  
10.             lock.unlock(); // release monitor  
11.         }  
12.     }  
13.     public static void main(String[] args) {  
14.         new Thread(Main::task, "Thread-1").start();  
15.         new Thread(Main::task, "Thread-2").start();  
16.         new Thread(Main::task, "Thread-3").start();  
17.         new Thread(Main::task, "Thread-4").start();  
18.         new Thread(Main::task, "Thread-5").start();  
19.     }  
20. }  

**Output:**

Thread-1 acquired lock
Thread-2 acquired lock
Thread-3 acquired lock
Thread-4 acquired lock
Thread-5 acquired lock

### Example: Hold Count and Ownership Check

The tracking of monitor ownership is the main topic of this example. The number of times the current thread has entered the reentrant monitor is shown by getHoldCount(). Exclusive ownership has been verified by isHeldByCurrentThread(). Until all reentrant acquisitions are matched with matching unlock() operations, the lock is still in effect.

### Example

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. import java.util.concurrent.locks.ReentrantLock;  
2. class Main {  
3.     private static ReentrantLock lock = new ReentrantLock();  
4.     static void execute() {  
5.         lock.lock(); // first lock  
6.         lock.lock(); // reentrant lock  
7.         try {  
8.             // Displays number of times current thread holds the monitor  
9.             System.out.println("Hold Count: " + lock.getHoldCount());  
10.             System.out.println("Is Held By Current Thread: " + lock.isHeldByCurrentThread());  
11.         } finally {  
12.             lock.unlock(); // reduces hold count  
13.             lock.unlock(); // completely releases lock  
14.         }  
15.     }  
16.     public static void main(String[] args) {  
17.         execute();  
18.     }  
19. }  

**Output:**

Hold Count: 2
Is Held By Current Thread: true

## Importance of Reentrancy

### Safe Nested Method Calls

A thread can safely call a synchronized method from another synchronized method using the same lock thanks to reentrancy.

The thread would block itself and result in a deadlock in the absence of reentrancy.

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. lock.lock();  
2. methodA();   // calls methodB() internally  
3. lock.unlock();  

Here, the same thread re-enters the lock while already holding it, which is safely permitted.

### Prevention of Self-Deadlock

When a thread already has a lock, it should never wait for it. Even when execution passes through several protected ways, self-deadlock is prevented thanks to reentrancy.

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. void methodA() {  
2.     lock.lock();  
3.     methodB();  // same lock used again  
4.     lock.unlock();  
5. }  

The thread continues execution instead of blocking itself.

## Clean and Natural Object-Oriented Design

Methods in object-oriented applications frequently rely on other methods within the same class. Synchronization can continue to be method-centric rather than call-context-centric thanks to reentrancy.

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. lock.lock();  
2. updateAccount();   // internally calls validateAccount()  
3. lock.unlock();  

Each method can independently ensure [thread safety](https://www.tpointtech.com/what-is-thread-safety-in-java) without knowing the caller's state.

### Reliable Inheritance and Method Overriding

In [inheritance](https://www.tpointtech.com/inheritance-in-java) hierarchies, parent class methods are frequently called by child class methods. Both approaches can be synchronized thanks to reentrancy, which eliminates the need to change the locking logic.

**Example**

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. class Parent {  
2.     synchronized void process() { }  
3. }  
4. class Child extends Parent {  
5.     synchronized void execute() {  
6.         process(); // safe due to reentrancy  
7.     }  
8. }  

The same thread can enter both synchronized methods safely.

### Accurate Lock State Management

Reentrant locks provide exact control over lock ownership by keeping track of the hold count. By doing this, locks are guaranteed to be released only after all nested entries have been exited.

**Example:**

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. lock.lock();  // count = 1  
2. lock.lock();  // count = 2  
3. lock.unlock(); // count = 1  
4. lock.unlock(); // count = 0 (released)  

This prevents premature unlocking and data inconsistency.

### Simplified Developer Responsibility:

It is not necessary for developers to check if a lock is already in place before going into a crucial area. Error-prone logic is decreased via reentrancy, which transfers this duty to the Java concurrency framework.

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. lock.lock();  
2. performTask(); // no need to check lock ownership  
3. lock.unlock();  

Code becomes cleaner, safer, and easier to maintain.

## Advantages of Reentrant Monitor

**Supports Safe Re-entry:** The same thread can obtain the same lock more than once without blocking itself thanks to a reentrant monitor. This guarantees seamless execution throughout nested method calls and prevents self-deadlock.

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. lock.lock();  
2. methodA();   // internally calls another locked method  
3. lock.unlock();  

**Prevents Self-Deadlock:** In the absence of reentrancy, a thread would have to wait indefinitely for a lock it already has. Reentrant monitors identify who owns the property and permit re-entry right away. As a result, synchronization in practical applications is safer and more dependable.

**Enables Clean Object-Oriented Design:** Without verifying the lock status of the caller, each method is capable of autonomously managing its own synchronization. This facilitates readable and modular code.

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. lock.lock();  
2. update();  
3. validate();   // both safely synchronized  
4. lock.unlock();  

**Accurate Lock State Management:** Reentrant monitors keep track of the number of times a lock is obtained by keeping a hold count. Only when every re-entry has been completed is the lock unlocked. Prevents inconsistent data and early unlocking.

**Advanced Synchronization Features:** Reentrant monitors (via ReentrantLock) support:

- Fair and unfair locking
- Interruptible locking
- Timed lock attempts
- Condition variables

These features provide greater control than intrinsic monitors.

**Reliable Inheritance and Method Overriding:**

Parent and child class methods can both be synchronized safely. Reentrancy ensures smooth execution across inheritance hierarchies.

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. class Child extends Parent {  
2.     synchronized void execute() {  
3.         super.process();  
4.     }  
5. }  

## Disadvantages of Reentrant Monitor

**Increased Complexity:** It is necessary to manually manage lock() and unlock() for explicit reentrant monitors. Serious concurrency flaws may result from improper use. It could result in deadlock if an unlock() is absent.

**Risk of Lock Mismanagement:** If unlock() calls do not match the number of lock() calls, the monitor may never be released.

[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)[](https://www.tpointtech.com/reentrant-monitor-in-java#)

1. lock.lock();  
2. // missing unlock → lock leak  

**Performance Overhead:** Hold counts, waiting lines, and ownership data are all kept up to date via reentrant monitors. When compared to more straightforward synchronization, this adds a little performance overhead.

**Fair Locks Reduce Throughput:** Due to scheduling overhead, fair locking lowers speed but ensures ordering.

**Harder Debugging:** It can be challenging to track down problems like incorrect hold counts or lock leakage. Concurrency bugs are frequently random in appearance.

**Overuse Can Reduce Scalability:**

Excessive locking can:

- Reduce parallelism
- Increase thread contention
- Lower system throughput

## Conclusion

In order to provide secure nested method calls and avoid self-deadlock, a Java Reentrant Monitor offers a potent synchronization mechanism that permits a thread to obtain the same lock repeatedly without stopping itself. It supports clean object-oriented architecture and retains exclusive access to shared resources by monitoring lock ownership and hold count.

Fairness, timed locking, and interruptible waits are examples of advanced concurrency characteristics made possible by reentrant monitors. They are necessary for creating dependable and scalable multithreaded Java applications, despite the fact that they increase some complexity and overhead.