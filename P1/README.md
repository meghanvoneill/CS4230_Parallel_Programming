# CS4230_Parallel_Programming
# P1: Parallelize CNN
# Meghan V. O'Neill


1. Parallelize a single loop.

Parallelizing where it will have the most impact, or coarse granularity, means looking at the outer-most loop.

2. Parallelize multiple loops. 

Keeping with the idea that we want broad impact, if we are to parallelize multiple loops, the next outer-most loop would be the most ideal to parallelize.

3. Use the collapse clause on two or more adjacent loops that do not carry dependences.

For this strategy, recognizing that the p-loop was parallelizable allowed for a speedup of 1.25 in the first set of data. Including the collapse clause (collapse(2)) allowed us to parallelize the p-loop and the q-loop.

4. Try varying the loop schedules, using static versus dynamic scheduling and different chunk sizes.

I have two different sets of code to try addressing this variation. The first used dynamic scheduling with an explicit chunk size of 8. The second used static scheduling, and I saw the best times with no explicit chunk specified.


Version	 Desciption	       	    	       	   	Performance	  Speedup Over Baseline
Seq	 original sequential code, input 1		.83s		  1.0x
Par1
Par2
Par3	 parallelized p-loop with 4 threads and
	 collapse clause of 2, input 1			.46s		  1.25x
Par4a	 dynamic scheduling on parallelized 		.68s		  1.22x
Par4b	 static scheduling on parallelized		.57s		  1.38x