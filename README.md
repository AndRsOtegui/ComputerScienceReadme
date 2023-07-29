# ComputerScienceReadme
https://leetcode.com/AndresCastellanos/

I have been learning java to solve the easy challenge, today i found i have a mistake in the code which makes the code dont compare all the elements in the prefix so the sum prefix is given the wrong values, here i attach the code i have been using to solve case number 1, i will use the remaining time to fix thix and optmize the final code i get.

import java.util.Arrays;
import java.util.*;

class Solution {
    public int[] distinctDifferenceArray(int[] nums) {
       int n =nums.length;
	    int diff[]=new int[n];
	    int prefix=1;
	    int suffix=1;
	    int x = 0;
	    //int i = 0;
	     
	     for(int i=0;i<n;i++){
	         
	     do{
	     	    x++;
	     	 
	     	//prefix count
	       if(i==0){
	               prefix=1; 
	            }
	             
	             else if(nums[i]!=nums[i-x]){
	               prefix++;
	             }
	   
	     	}while(i-x>0);
	     	x=0;
	     	do{
	     	    x++;
	            if(i==n-2){
	             suffix=1;
	            }
	            else if(i==n-1){
	                suffix=0;
	            }
	                else if(nums[i+1]!=nums[i+x+1]){
	               suffix++;
	            }
	           
	     	}while(x<n-2-i);
	      System.out.println(prefix+"-"+suffix);
	        diff[i]=prefix-suffix;
	        prefix =1;
	        suffix=1;
	        x=0;
	     }
	      
	     
	        System.out.print(Arrays.toString(diff));
	    
       return diff; 
    }
}
