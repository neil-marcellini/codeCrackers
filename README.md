# Code Crackers
For the final project of Computer Organization and Architecture I had to pick a programming challenge to do with a partner.
Richard Zins (@RIZY101) and I chose to do the "Code Crackers" challenge. Our task was to write a C program that read a list of
semi-primes from the file "Semiprimes.txt", factored each semi-prime into its prime factors, and created a file in "/Outputs"
with the semi-prime and the two factors. We were also required to speed up our program using OpenMP to implement 
multi-threading. The team who could factor the most semi-primes in 30 seconds was the winner of the class competition.

## Prerequisites
You will need to [install OpenMP](https://www.geeksforgeeks.org/openmp-introduction-with-installation-guide/) and a C compiler for your machine.

## Getting Started
Open the directory in terminal and type the following commands to compile:

Mac:

`clang -Xpreprocessor -fopenmp -lomp main.c codeCrackers`

Linux:

`gcc -fopenmp main.c -l m -o codeCrackers`

After compilation type the following command to run:

`./codeCrackers`

After about 9 seconds the program will print the time it took to complete. You can look in the outputs 
folder while the program is running to see the files being output in real time.

## What I Learned
We chose to implement our progam with a table of primes hard coded as an array. We chose to process the semi-primes in batches and skip primes larger than a certain size, so that the program would actually finish. We did not know how many semi-primes we would be given, and they could be as large as 2^64. 

Two major take aways are:

We should have divided each semi-prime by each prime in the table to find both factors, rather than iterating through the table in nested for loops and finding two factors that multiply to equal the semi-prime. The approach with division would be faster and allow us to handle larger semi-primes. 

Parallelize super-tasks before sub-tasks. It is much better to start by factoring multiple semi-primes at once rather than parallelize the factoring of one semi-prime first. Eventually we implemented both for maximum speed.

## Acknowledgments
Written by Neil Marcellini and Richard Zins for COMP 262 - Computer Organization and Architecture at CSU Channel Islands.
Links to references are included as comments in the source code.
