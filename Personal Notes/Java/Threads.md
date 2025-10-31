# Main
```java
public class Main {
	public static void main(String[] args) {
		// Run thread class with run built in
		ThreadClass thread1 = new ThreadClass();
		ThreadClass thread2 = new ThreadClass();
		
		//.start() calls the run method in ThreadClass
		thread1.start();
		thread2.start();
		
		// Use join to wait for a thread to finish
		try {
			thread1.join();
			thread2.join();
			
		}
		catch (InterruptedException e) {
			System.out.println("Counting extends thread interrupted");
			
		}
		
		// Create a thread class that is runnable, cannot be ran without an acutal thread class
		RunnableThreadClass runnable = new RunnableThreadClass(); // Runnable class
		Thread runnableThreads = new Thread(runnable); // Thread to run runnable class
		runnableThreads.start(); // calls the run method in Thread class
		
		try {
			runnableThreads.join();
			
		}
		catch (InterruptedException e) {
			System.out.println("Counting runnable thread interrupted");
			
		}
	}
}
```

# Thread Class with Run

```java
public class ThreadClass extends Thread {
    // Constructor to initialize the 'number' for each thread
    public ThreadClass() {
        // Constructor
        
    }
    
    @Override
    public void run() {
        // Main code to run for Thread class
        
    }
}
```

# Runnable Threads

```java
public class RunnableThreadClass implements Runnable {
    public void run() {
        // Main code to run for Thread class
    }
}
```