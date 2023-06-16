# Coding-Prac

class Solution {
    public int trap(int[] height) {
        int l=height.length;

        int larr[]= new int[l];
        larr[0]=height[0];
        for(int i=1; i<l; i++){
            larr[i]=Math.max(larr[i-1],height[i]);
        }
        int rarr[]= new int[l];
        rarr[l-1]=height[l-1];
        for(int j=l-2; j>=0; j-- ){
           rarr[j]=Math.max(rarr[j+1],height[j]);
        }
        int cap=0;
        for(int i=0; i<l; i++){
            cap =cap +  Math.min(larr[i],rarr[i])-height[i];
        }
        return cap;
            
        }

    }
