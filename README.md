# Dining philosophers

It represents a problem in parallel programming. Each philosopher needs two forks to eat. Now, the problem is that there is a fork between each two of them.
A naive solution is:
* each one pick two forks then eat 
* put the left down 
* put the right down
This problem can lead to deadlock, livelock, resource contention. 
A resource starvation is happening to the ones with no forks while, others hold them. 

This solution is a part of Introduction to Concurrent Programming with GPUs course. it consists of 5 Phillies with 5 forks. Must have two forks to eat.

Deadlock is avoided by never waiting for a fork while holding a fork (locked)
Procedure is to do block while waiting to get first fork, and a nonblocking acquire of second fork.  
If failed to get second fork, release first fork, swap which fork is first and which is second and retry until getting both.