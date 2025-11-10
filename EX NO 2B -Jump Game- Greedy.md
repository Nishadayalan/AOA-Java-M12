
# EX 2B Jump Game using Greedy Algorithm.
## DATE: 01-09-2025

## AIM:
To write a Java program to for given constraints.
You are given an array of integers. Each number represents the maximum number of steps you can jump forward from that position.

You start from the first element (index 0). 
Write a program to find the minimum number of jumps required to reach the last index of the array.

If it is not possible to reach the end, return -1.
## Algorithm:
1. Input: Array nums[] representing maximum jump length from each index.

2. Edge cases: If nums.length <= 1, return 0; if nums[0] == 0, return -1.

3. Initialize: jumps = 0, currentEnd = 0, farthest = 0.

4. Iterate through array: For each index i, update farthest = max(farthest, i + nums[i]); if i == currentEnd, increment jumps and set currentEnd = farthest; if currentEnd reaches end, break; if currentEnd == i, return -1.

5. : If currentEnd >= last index, return jumps; else return -1.


## Program:
```
Developed by: NISHA D
Register Number: 212223230143


import java.util.Scanner;

public class MinJumpToEnd {

    // Function to return minimum jumps to reach end
    public static int minimumJumps(int[] nums) {
        // Type Your Code Here.
        if (nums.length<=1) return 0;
        if(nums[0]==0)return -1;
        int jumps= 0;
        int currentEnd = 0;
        int farthest = 0;
        for(int i =0;i <nums.length-1;i++)
        {
            farthest = Math.max(farthest,i + nums[i]);
            if( i == currentEnd)
            {
                    jumps++;
                    currentEnd = farthest;
                    if(currentEnd  >= nums.length-1)
                    {
                        break;
                    }
                    if(currentEnd == i) return -1;
                }
        }
        return currentEnd >= nums.length - 1? jumps : -1;
    }

    // Main method to handle input and output
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        int n = sc.nextInt(); // Number of elements
        int[] nums = new int[n];

        for (int i = 0; i < n; i++) {
            nums[i] = sc.nextInt();
        }

        System.out.println("Minimum jumps to reach last index: " + minimumJumps(nums));
    }
}

```

## Output:

<img width="1045" height="332" alt="image" src="https://github.com/user-attachments/assets/a7cae152-d9ee-4539-b3a0-11a8700243d3" />



## Result:
The program successfully implemented and the expected output is verified.
