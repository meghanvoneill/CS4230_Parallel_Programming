# CS4230_Parallel_Programming
# P1: Parallelize CNN
# Meghan V. O'Neill

3. Use the collapse clause on two or more adjacent loops that do not carry dependences.

For this strategy, recognizing that the p-loop was parallelizable allowed for a speedup of 1.25 in the first set of data. Including the collapse clause (collapse(2)) allowed us to parallelize the p-loop and the q-loop.

4. Try varying the loop schedules, using static versus dynamic scheduling and different chunk sizes.



Version	 Desciption	       	    	       	   	Performance	  Speedup Over Baseline
Seq	 original sequential code, input 1		.83s		  1.0x
Par1
Par2
Par3	 parallelized p-loop with 4 threads and
	 collapse clause of 2, input 1			.46s		  1.25x
Par4a	 dynamic scheduling on parallelized 		.68s		  1.22x
Par4b	 static scheduling on parallelized		.57s		  1.38x