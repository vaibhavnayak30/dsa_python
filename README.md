# DSA Notes


### 🌟 Minimum Size of Subarray Sum
    Question Type:
    - Return the minimal length of a subarray whose sum is greater than or equal to target

     Check:
        - If all elemets are either **positive** or **negative** or **mix**
        - If either all positive or all negative:
            - Sliding window with Two Pointer

          - If mix (positive + negative)
            - Prefix Sum + HashMap

### 🌟 Hash Map + Prefix Sum Concept
    - Prefix Sum Map can include prefix prefix sum with count or indice
        {prefix_sum : count / indice}
    
    - Concepts: 
        - Sum(subarray) = prefix_sum[i] - prefix_sum[j]
            where the subarray is from index j+1 to i and not j to i

        - To find subarray with a sum, 
            - Find value of all prefix sums where key equals prefix_sum[j] - target
            - No need to increment counter, when condition matches

        - To find all subarrays, divisible by a integer
            - Use concept if remainder (a/b) = remainder (c/b), then (a-c) is fully divisible by (b)
            - Keep on calculating remainder for each prefix sums with values as count 
            - Need to increment counter if conditions matches

### 🌟 Sliding Window vs Prefix Sum 
    - Sliding window works when:
        - Array has all positive integers (so window grows/shrinks predictably)
        - When we need exact sum or inequality like (sum >= target), and not preferred for anything related to division

        Point to Note:
            - Sliding window cannot be applied in division / remainder related because the property we’re checking (divisibility) is modular, not monotonic

    - Sliding window fails when:
        - Negative numbers are involved → sum is no longer monotonic (can bounce up and down)
        - The condition is modular (like divisibility, remainder checks)
        - The condition depends on exact matching with multiple possible values

    - Conclusion:
        - Sliding window => good for monotonic, single-threshold problems with positives
        - Prefix sums + hashmap => Good for modular, exact, or XOR-based problems

    - Points to remember:
        - Prefix Sum:
            - {0: -1} represents a virtual prefix sum before the array starts
            - Without it, any subarray starting at index 0 cannot be considered
            - Example: Problems like “shortest subarray to remove” or “subarray sum divisible by k”
            
            - {0: 1} Use when the map stores -> count of occurrences
            - {0: -1} Use when the map stores -> latest index of prefix_sum
            - Example: “Subarray Sums Divisible by K”

### 🌟 Majority Elements
    - There are two categories
        - Number of elements more than (n/2):
            - Set count = 0 and candidate = None
            - Check if count = 0, if yes, set the current element 
            - Increment the count by 1 if same as candidate or decrease by 1
            - Count the candidate in array with condition

        - Number of elements more than (n/3):
            - Set count1, count2= 0 and candidate1, candidate2= None
            - Iterate check if and candidate match the current num 
            - Then check if any count1 or count2 = 0
            - Else: Reduce both count1 and count2 by 1

            - Point to note is, first we need to check mathcing candidate 1 , 2 with iterator and then set the candidate value

### 🌟 DFS 
    - There are 2 ways to solve using DFS 
        - Validate the boundary conditions just after entering dfs and return if not satisfied
        - Create changes list with [(1,0),(-1,0),(0,1),(0,-1)] and loop through them while checking for boundary and extra condition 

