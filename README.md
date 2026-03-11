
#User function Template for python3
class Solution:
    def subarraySum(self, arr, target):
        start = 0
        current_sum = 0

        for end in range(len(arr)):
            current_sum += arr[end]

            # Shrink window if sum becomes greater than target
            while current_sum > target and start <= end:
                current_sum -= arr[start]
                start += 1

            # Check if target sum found
            if current_sum == target:
                return [start + 1, end + 1]   # 1-based index

        return [-1]
    Your Output:
2 
