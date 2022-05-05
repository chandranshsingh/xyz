# xyz
Given n number of sorted files, the task is to find the minimum computations done to reach the Optimal Merge Pattern.  When two or more sorted files are to be merged altogether to form a single file, the minimum computations are done to reach this file are known as Optimal Merge Pattern.
If more than 2 files need to be merged then it can be done in pairs. For example, if need to merge 4 files A, B, C, D. First Merge A with B to get X1, merge X1 with C to get X2, merge X2 with D to get X3 as the output file.
If we have two files of sizes m and n, the total computation time will be m+n. Here, we use the greedy strategy by merging the two smallest size files among all the files present.
Node represents a file with a given size also given nodes are greater than 2 
APPROACH
Add all the nodes in a priority queue (Min Heap).{node.weight = file size}
Initialize count = 0 // variable to store file computations.
Repeat while (size of priority Queue is greater than 1) 
create a new node
new node = pq.poll().weight+pq.poll().weight;//pq denotes priority queue, remove 1st smallest and 2nd smallest element and add their weights to get a new node
count += node.weight
add this new node to priority queue;  
count is the final answer
If more than 2 files need to be merged then it can be done in pairs. For example, if need to merge 4 files A, B, C, D. First Merge A with B to get X1, merge X1 with C to get X2, merge X2 with D to get X3 as the output file.
If we have two files of sizes m and n, the total computation time will be m+n. Here, we use the greedy strategy by merging the two smallest size files among all the files present.
 Example-
 (F1, F2, F3, F4, F5)= (20, 30, 10, 5, 30).
M1= F1 & F2 Þ 20+30 = 50
M2= M1 & F3 Þ 50+10 = 60
M3= M2 & F4 Þ 60+5 = 65
M4= M3 & F5 Þ 65+30 = 95
                     270

Optimal merge pattern: Greedy method. Sort the list of files:
(5,10, 20, 30, 30)= (F4, F3, F1, F2, F5)
Merge file using 2-way merge
Merge two file at a time.
Add merge file into the list of files in sorted order.

Merge first two files
(5,10, 20, 30, 30)=> (15, 20, 30, 30)
Merge next two files
(15, 20, 30, 30)=> (30, 30, 35)
Merge next two files
(30, 30, 35) => (35, 60)
Merge next two files
(35, 60)=> (95)
Total time=15+35+60+95=205.


Problem:
Input: Given n sorted files
Output: Merge n files in a minimum amount of time.

Working of algorithm with example: Consider a pool of file L which contain n files. Step 1: find first two min fil
Step-3 : repeat step-1 & 2 until no file remain in the pool L for merging. e.g.

L (F1, F2, F3, F4, F5)= (20, 30, 10, 5, 30).

Find first two min files which are F4 and F3



    	
       Next merge them & add new file M1 to pool L

F4                  	F3
L (F1, F2, M1, F5)= (20, 30, 15, 30).

Now find next two min files(which are F1 and M1) , merge them and add new merge file M2 to L.



F4	F3
L (F2, M2, F5)= ( 30, 35, 30).
 
merge file M3 to L. L ( M2, M3)= ( 35, 60).






F2	F5

F4	F3


Now merge next two min file. L(M4)={95}


F4	F3
![https://github.com/chandranshsingh/xyz/blob/main/python-logo@2x.png?raw=true]



Analysis:
 
Case 1 L is not sorted.
O (find minimum)= O (n).---we can use first 2 pass of selection sort will give first two minimum which require 2n cost.(O(n))
O (cost for insertion in L)= O (1)	L is not sorted so we can insert in last
in array.
Time complexity :T= O (n2)
Case 2 L is sorted. Case 2.1
O (find minimum)= O (1)	because L is sorted we get 2 minimum in
fist two place.
O (cost for insertion in L)= O (n)	L is sorted so after merge new file
will be added to specific location so that the L remain sorted. Time complexity: T= O (n2)
Case 2.2
L is represented as a min-heap. Value in the root is less then or equal to the values of its children.
O (find minimum)= O (log n)	cost for deletion of minimum in min
heap
O (cost for insertion in L)= O (log n)--cost for insertion of minimum in min heap
Time complexity: T= O (n log n).
