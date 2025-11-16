两数之和

![image-20251116162526071](C:\Users\chen\AppData\Roaming\Typora\typora-user-images\image-20251116162526071.png)

```java
 class Solution{
	public int [] twoSum(int[] nums,int target){
        //整理清楚输入输出,输入是数组,数值和位置,输出是位置
        //这里是只考虑一对,可能会有重复,以及多对数据
        Map<Integer,Integer> hashmap = new HashMap<Integer,Integer>();
        for(int i=0;i<nums.length;i++){
            if(hashmap.containsKey(target-nums[i])){
                return new int[]{hashmap.get(target-nums[i]),i};
            }
            hashmap.put(nums[i],i);
        }
        return new int[0];
    }    
}
```

假如是多队数据的情况

```java
class Solution{
    public List<List<Integer>> twoSum(int []nums,int target){
        Map<Integer,Integer> hashmap = new HashMap<Integer,Integer>();
        List<List<Integer>> result = new ArrayList<>();
        if (nums == null || nums.length < 2) {
            return result; // 直接返回空列表，无需进入循环
        }
        for(int i=0;i<nums.length;i++){
            if(hashmap.containsKey(target-nums[i])){
                List<Integer>list = new ArrayList<>();
                list.add(hashmap.get(target-nums[i]));
                list.add(i);
                result.add(list);
            }
            hashmap.put(nums[i],i);
        }
 		return result;
    }
}
```