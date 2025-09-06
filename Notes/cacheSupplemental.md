To find the # of bits required to represent a specific part of the address in a cache follow the following

One Way cache
---
___
Given:
Cache Size: S
Block Size: B

Calculate
# of Lines = S / B = L

Address Breakdown
Offset = log_2(B) = O
Index = log_2(L) - I
Tag = S - I - O = T

N Way cache

Given:
Cache Size = S
Block Size = B
Associativity = N
Address size = A (e.g., 32 bits)

# Lines = S / B = L
# Sets = L / N

Offset bits = log2(B)
Index bits  = log2(Sets)
Tag bits    = A - Index - Offset

In plain text (no variables)

# of lines = Cache Size / Block Size
# of sets = num of lines / the number of ways

offset bits = log2(block size)
index bits = log2(number of sets)
tag bits = address size - number of offset bits - number of index bits

once you've calculated this they go in the order of

[Tag | Index | offset]





Class Examples

Core i7 L1 Cache

Cache size = 32 KB bytes per block or 2^15
block size = 2^6
8 ways

Calculate:
lines = 2^15/2^6 = 2^9
sets = 2^9 / 2^3(8) = 2^6

Offset bits = log2(2^6) = 6
index bits = log2(2^6) = 6
tag = 32 - 6 - 6 = 20


<img width="885" height="330" alt="image" src="https://github.com/user-attachments/assets/ad947d56-b378-4ccb-a9fd-eb0e10b0bbe9" />


To git the # of bits for each part of the address using a table:

index bits = log2(# of indexes) in this example it would be log2(8)
offset bits = log2(# of bytes in one way) in this case it is log2(4)
tag is whatever bits remain (you can add zeros to the front)


Types of misses
---
___

Cold start miss
- first time a block is accessed it is empty

Capacity miss
- 0 cache cant hold alll blocks so you have to remove some even though you will probably use it later

Conflict miss
- multiple blocks compete for the same cache set even if the cache as a whole has space
  - addresses 0x1000 and 0x2000 map to the same line so one overwrites another
 
Summary of misses

Compulsory (first-time access)

Capacity (cache too small overall)

Conflict (mapping collision)


