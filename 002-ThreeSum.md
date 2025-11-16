```JAVA
class Solution {
    public List<List<Integer>> threeSum(int[] nums) {
      //泛型集合 使用new来 赋予
        List<List<Integer>> result = new ArrayList<>();
        //排序
      Arrays.sort(nums);
        int n =nums.length;
     //对所有的前面几项全都选好 
     for(int i=0;i<n-2;i++){
         //判断是否是一样的数值,并且需要考虑下标
        if(i>0&&nums[i]==nums[i-1]) continue;
         //双指针移动
        int left=i+1;
        int right=n-1;
         //出口是判断整个后面的一条都看过
        while(left<right){
            int sum=nums[i]+nums[left]+nums[right];
            if(sum<0)left++;
            else if(sum>0)right--;
            //把list放到输出里面,并且要注意下标问题
            else if(sum==0){
                List<Integer> list = new ArrayList<>();
                list.add(nums[i]);
                list.add(nums[left]);
                list.add(nums[right]);
                result.add(list);
                left++;
                right--;
                while(left<right&&nums[left]==nums[left-1])left++;
                while(left<right&&nums[right]==nums[right+1])right--;
             
            }
        }
      }
        return result;
    }
}	
```

