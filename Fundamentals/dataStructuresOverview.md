# Data Structures Overview

## Random Access Memory (RAM)

Variables (nums, strings, arrays, etc) stored in `random access memory (RAM)` or 'working memory' or 'memory'. Memory is faster but has less space
(differs from storage which has more space to store files, documents, and programs live but is slower)

RAM is like a bookcase with billions of numbered shelves, numbers designating a shelf's address. A shelf holds `8 bits / 0's and 1's`.

**8 bits === 1 byte**

A processor does all the work within the computer and goes through a `memory controller` which reads and writes to and from the RAM. Has a direct connection to each shelf of RAM. *access the bits at any random address in memory right away*

The processor stores a `cache` where it stores a copy of data read recently from RAM. Cache is faster than reading from RAM, saves time for processor. When a processor asks for data from a given memory address, the memory controller also sends data from nearby memory addresses which is all stored in the cache. Reading from sequential memory is faster than jumping around.

## Binary Numbers

Standard number system uses base 10 (decimal), each digit has 10 possible values(1, 2, 3, ... 9, 0)</br>
vs.</br>
computers use **Base 2** numbers (binary), each digit has 2 possible values (0 & 1)

```
Base 10:
101 (100s - 10s - 1s) = 1 hundred + 0 tens + 1 one = 101
10^0 = 1
10^1 = 10
10^2 = 100
10^3 = 1000
etc...

Base 2:
101 (4s - 2s - 1s) = 1 four + 0 twos + 1 one = 5
2^0 = 1
2^1 = 2
2^2 = 4
2^3 = 16
etc...
```
**unsigned integers:** unsigned = non-negative, integer = whole number, not fractional or decimal. Signed integers reserve the leftmost bit for the sign </br>
`0 = positive, 1 = negative`

## Fixed Width Integers

1 byte = 8 bits</br>
2^8 = 256 numerical possibilities with 8 bits / 255 possibilities in an 8 bit unsigned integer</br>
4 bytes = 32 bits (8 * 4) = 2^4 possibilities</br>
8 bytes = 64 bits (8 * 8) = 2^8 possibilities</br>

**with 'n' bits, 2^n expresses the different numerical possibilities**

Anything higher than the number of possibilities is an `integer overflow`</br>
Integers are `fixed width or fixed length`, number of bits doesn't change.</br>
ex: 64 bit integer - 0 or 193,457 will still take up 64 bits.</br>

**PROS:**
Space Complexity: 0(1) / constant space. Simple operations on fixed witdh integers is 0(1) time (addition, subtraction, division)

**TRADEOFF:**
Values are limited to 2^n possibilities

## [Hash Tables](hashTables.md)

Hash Tables / Hash maps can be thought of as array/table with two columns. Column for `keys` and `values`. Any given number, character, string can be translated into a key / index in the array through a `hashing function`. And the value is stored at that index.

**PROS:**
Time Complexity: 0(1) constant lookup time for values

**CONS:**
Due to hash collisons, if a hash function is not optimal, lookups can take 0(n) time. Collions are rare enough with a good hash function that the average lookup is 0(1). Looking up a key by value is 0(n)
