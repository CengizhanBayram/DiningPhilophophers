# DiningPhilophophers
Dining Philophophers Arbitrator solution
ining Philosophers Problem with Animated Visualization
Overview
The dining philosophers problem is a classic synchronization problem that illustrates the challenges of resource allocation and avoiding deadlock. In this implementation, we use Python's threading module to represent philosophers as threads and forks as shared resources.

Classes
1. Arbitrator
Attributes:

forks: A list of Fork objects representing the forks on the table.
lock: A threading lock for ensuring atomic operations.
Methods:

request_forks(left_fork, right_fork, philosopher): Requests permission from the arbitrator to pick up the left and right forks. It uses a lock to ensure mutual exclusion.
release_forks(left_fork, right_fork): Releases the left and right forks, allowing other philosophers to use them.
2. Fork
Attributes:

index: An integer representing the unique identifier of the fork.
lock: A threading lock for ensuring atomic operations.
picked_up: A boolean indicating whether the fork is currently picked up.
owner: An integer representing the index of the philosopher who currently owns the fork.
Methods:

__enter__(self): Acquires the fork, marking it as picked up.
__call__(self, owner): Sets the owner of the fork and marks it as picked up.
__exit__(self, exc_type, exc_value, traceback): Releases the fork, marking it as not picked up and resetting the owner.
__str__(self): Returns a string representation of the fork.
3. Philosopher
Attributes:

index: An integer representing the unique identifier of the philosopher.
left_fork: A Fork object representing the philosopher's left fork.
right_fork: A Fork object representing the philosopher's right fork.
spaghetti: An integer representing the number of spaghetti plates the philosopher has.
eating: A boolean indicating whether the philosopher is currently eating.
arbitrator: An Arbitrator object for coordinating fork requests.
Methods:

run(): The main execution loop for the philosopher. Philosophers alternate between thinking and eating.
think(): Simulates the philosopher thinking for a random duration.
eat(): Simulates the philosopher eating by requesting forks from the arbitrator, eating, and releasing the forks.
__str__(self): Returns a string representation of the philosopher.
4. animated_table
Parameters:

philosophers: A list of Philosopher objects.
forks: A list of Fork objects.
m: An integer representing the initial number of spaghetti plates for each philosopher.
Description:

Creates an animated visualization using Matplotlib to represent the dining philosophers and forks on the table.
5. table
Parameters:

philosophers: A list of Philosopher objects.
forks: A list of Fork objects.
m: An integer representing the initial number of spaghetti plates for each philosopher.
Description:

Prints a simple text-based representation of the philosophers, forks, and the number of eating philosophers.
6. main()
Description:
Initializes the dining philosophers simulation with a specified number of philosophers (n) and spaghetti plates (m).
Creates threads for each philosopher, starts the table visualization in a separate thread, and initiates the animated visualization.
This documentation provides an overview of the dining philosophers problem implementation, including the classes and their methods, along with example usage. The animated visualization allows for a graphical representation of the dining philosophers and their interactions.
