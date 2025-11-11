
# EX 3E Generate Permutations using Backtracking  Approach.
## DATE:
## AIM:
To write a Java program to for given constraints.
Given an array nums of distinct integers, return all the possible Permutation. You can return the answer in any order.
Example 1:
Input: nums = [1,2,3]
Output: [[1,2,3],[1,3,2],[2,1,3],[2,3,1],[3,1,2],[3,2,1]]
For example:
## Algorithm
```
1. Input Processing:
Read the array elements from user input, remove brackets ([]), split by commas, and store them in an integer array nums.
2. Start Permutation Generation:
Initialize an empty list ans to store all permutations and call the recursive backtrack() function with an initially empty list curr.
3. Recursive Backtracking Logic:
If curr (the current permutation) has the same length as nums, add a copy of curr to ans.
Otherwise, iterate through each number in nums.
4.  Build and Explore Permutations:
For each number not already in curr, add it to curr, recursively call backtrack() to build further, and then remove it (backtrack) to explore other possibilities.
5.  Output Result:
After recursion completes, print all generated permutations stored in ans. 
```   

## Program:
```
/*
Program to implement Reverse a String
Developed by: SARANYA S
Register Number:  212223110044
*/
```
```
import java.util.*;

public class Solution {

    public List<List<Integer>> permute(int[] nums) {
        //add your code here
        List<List<Integer>> ans=new ArrayList<>();
        backtrack(new ArrayList<>(),ans,nums);
        return ans;
        
    }

    public void backtrack(List<Integer> curr, List<List<Integer>> ans, int[] nums) {
        //Add your code here
        if(curr.size()==nums.length){
            ans.add(new ArrayList<>(curr));
        }
        for(int num:nums){
            if(!curr.contains(num)){
            curr.add(num);
            backtrack(curr,ans,nums);
            curr.remove(curr.size()-1);
            
        }
        }
    }

    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        String inputLine = scanner.nextLine().trim();
        inputLine = inputLine.replaceAll(".*\\[|\\].*", ""); 
        String[] parts = inputLine.split(",");

        int[] nums = new int[parts.length];
        for (int i = 0; i < parts.length; i++) {
            nums[i] = Integer.parseInt(parts[i].trim());
        }
        Solution solution = new Solution();
        List<List<Integer>> permutations = solution.permute(nums);
        System.out.println(permutations);
        scanner.close();
    }
}

```

## Output:

<img width="1290" height="220" alt="image" src="https://github.com/user-attachments/assets/7dcb4c78-bbc2-427d-a576-29dc5edcc424" />


## Result:
The program successfully implemented and the expected output is verified.
