# Longest-SubString
In this we have to find maximum length of the substring in the given string
import java.util.HashMap;

class Solution {
    public int lengthOfLongestSubstring(String s) {
        
        int left=0,maxlength=0;

        HashMap<Character,Integer> map= new HashMap<>();

        for(int r=0;r<s.length();r++)
        {
            char c=s.charAt(r);
            map.put(c,map.getOrDefault(c,0)+1);
            while(map.size()>2)
            {
                char leftChar=s.charAt(left);
                map.put(leftChar,map.getOrDefault(leftChar,0)-1);
                if(map.get(leftChar)==0)
                {
                map.remove(s.charAt(left));
                }
                left++;
                
            }
            maxlength=Math.max(maxlength, r-left+1);
                
        }
        return maxlength;
    }
    }
