# DSA Notes


### 🌟 Minimum Size of Subarray Sum
    Question Type:
    - Return the minimal length of a subarray whose sum is greater than or equal to target

     **Check**:
        - If all elemets are either **positive** or **negative** or **mix**
        - If either all positive or all negative:
            - Sliding window with Two Pointer

          - If mix (positive + negative)
               - Prefix Sum + HashMap

### 🌟 Hash Map + Prefix Sum
    - Prefix Sum Map can include prefix prefix sum with count or indice
        {prefix_sum : count / indice}
    
    - Concepts: 
        - sum(subarray) = prefix_sum[i] - prefix_sum[j]
            where the subarray is from index j+1 to i and not j to i

        - To find subarray with a sum, 
            - Find value of all prefix sums where key equals prefix_sum[j] - target
            - No need to increment counter, when condition matches

        - To find all subarrays, divisible by a integer
            - Use concept if remainder (a/b) = remainder (c/b), then (a-c) is fully divisible by (b)
            - Keep on calculating remainder for each prefix sums with values as count 
            - Need to increment counter if conditions matches