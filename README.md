Download Link: https://assignmentchef.com/product/solved-solvedprogramming-assignment-5-solution
<br>
This assignment requires you to write a multi-processed program that works with a memory-mapped file. With the help of virtual memory, memory mapping approach allows a disk file to be initially mapped into memory through demand paging and then to be manipulated subsequently via memory accesses rather than disk file I/O. This can lead to improved performance (refer to pp. 430-433 of the textbook for details). Your C program will spawn two child processes that manipulate a memory-mapped file. Make sure that your submitted program compiles and runs on Athena. 1. In your program, the parent process takes a file name from the command line, creates a file with read/write permissions using the given file name, and initializes the file with the following lower-case string: with the mmap call, a disk file gets mapped into memory through demand
 paging, i.e., a page sized portion of the file is initially read into
 memory through a page fault. subsequent reads and writes to that portion
 of the file are handled as routine memory accesses. this improves file
 processing performance. in this assignment, the parent process memory maps
 this disk file first, and then creates two child processes that each make
 some changes to this file. when both child processes are done, changes
 made in memory are synch’ed to the disk file.
 The parent process then memory maps the file into the memory using the mmap() system call in the following manner (for more information on mmap() call, please refer to the on-line manual via “man mmap”). Afterwards, the parent creates two child processes, waits for the child processes to finish before it exits. #include <stdio.h #include <unistd.h <stdlib.h <sys types.h mman.h <fcntl.h stat.h <signal.h <string.h struct stat buf; char *mm_file, …… fstat(fd, &#038;buf); used to determine the size of file if ((mm_file="mmap(0," (size_t) buf.st_size, prot_read|prot_write, map_shared, fd, 0))="=" (caddr_t) - 1) { fprintf(stderr, mmap call fails
);…… } 2. first child process converts content its uppercase equivalence through string manipulation, and then uses msync system synchronize mapped memory with physical storage (disk) before exiting (for more information on msync() call, please refer on-line manual via “man msync”). following printf statements must be included in child-1 process. printf(child 1 %d reads: 
 %s
, getpid(), mm_file); {convert string}; msync(0, ms_sync); reads again: 3. second process, again makes changes after converted into equivalence: • use a hyphen replace space between “page” “sized” (page-sized); occurrence “mapped” “loaded”. sleep(1); so that 2 will perform task finishes {use “sized”}; {replace “loaded”}; above two child-2 4. submission requirements. your program include adequate commenting (points deduction for programs inadequate comments). compile program: gcc prog5.c -o prog5 submit source code 5 sacct.< p>


 </stdio.h>