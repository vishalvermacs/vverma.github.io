---
Layout: vverma.github.io
Title: Leet Code Solutions in C#
---

## 1. Two Sum
Given an array of integers, return indices of the two numbers such that they add up to a specific target.
You may assume that each input would have exactly one solution, and you may not use the same element twice.

> Given nums = [2, 7, 11, 15], target = 9. Because nums[0] + nums[1] = 2 + 7 = 9,
return [0, 1].

```c#
public static class TwoSum
    {
        public static int[] TwoSumAns(int[] nums, int target)
        {
            var hashMap = new Dictionary<int, int>();
            for (int i = 0; i <= nums.Length; i++)
            {
                var complement = target - nums[i];
                if (hashMap.ContainsKey(complement))
                {
                    return new int[] { hashMap[complement], i };
                }
                hashMap.Add(nums[i], i);
            }
            return new int[] { -1 };
        }
    }
```
