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
