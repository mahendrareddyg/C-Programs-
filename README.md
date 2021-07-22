# C-Programs- This space is intended to post solutions to some frequntly asked interview programming questions. I will be solving questions in various platforms like leetcode and will post the answers here with complete question description.

Problem:
Given an array of integers nums and an integer target, return indices of the two numbers such that they add up to target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

You can return the answer in any order.

 

Example 1:

Input: nums = [2,7,11,15], target = 9
Output: [0,1]
Output: Because nums[0] + nums[1] == 9, we return [0, 1].
Example 2:

Input: nums = [3,2,4], target = 6
Output: [1,2]
Example 3:

Input: nums = [3,3], target = 6
Output: [0,1]
 

Constraints:

2 <= nums.length <= 104
-109 <= nums[i] <= 109
-109 <= target <= 109
Only one valid answer exists.
 




/**
 * Note: The returned array must be malloced, assume caller calls free().
 */
#include <stdio.h>
int* twoSum(int* nums, int numsSize, int target, int* returnSize){
    if(2 > numsSize > pow(10,4)){
        printf("Invalid parameters");
        return 0;
    }
    
    
    
    int * output  =  malloc( 2 * sizeof(int) );
    
    for(int i=0; i < numsSize; i++)
    {
        if(pow(10,-9) > nums[i] > pow(10,9))
        {
            printf("Invalid parameters");
            return 0;
        }
        for(int j=i+1; j < numsSize; j++)
        {
            if(pow(10,-9) > nums[j] > pow(10,9))
            {
                printf("Invalid parameters");
                return 0;
            }
        
            if ((nums[i] + nums[j]) == target)
            {   
                output[0] = i;
                output[1] = j;
                break;
            }
        }
    }
    printf(" the return indices are %d, %d", output[0], output[1]);
    *returnSize = 2;
    return output;
}
