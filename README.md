# Luigi-and-Uniformity

Luigi has an array A of N positive integers. He wants to make all elements of the array equal.
In one move, he can
Choose an index i (1 ≤ i ≤ N) and divide the element Ai​ by any one of its divisors. In other words, he can choose a positive integer X such that X | Ai​ and set Ai​ = Ai​ ​/ X.
Find the minimum number of moves required to make all the elements of the array equal.

import math

def gcd_of_array(arr):

    gcd_result = arr[0]
    for num in arr[1:]:
        gcd_result = math.gcd(gcd_result, num)
        if gcd_result == 1:  
            break
    return gcd_result

T = int(input())

for _ in range(T):

    N = int(input())
    A = list(map(int, input().split()))    
    gcd_value = gcd_of_array(A)    
    moves = sum(1 for x in A if x != gcd_value)    
    print(moves)
