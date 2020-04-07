```java


class Solution {
    
    class Job {
        int startTime;
        int endTime;
        int profit;
        int maxProfit;
        
        Job(int startTime,int endTime, int profit) {
            
            this.startTime = startTime;
            this.endTime = endTime;
            this.profit = profit;
            this.maxProfit = profit;
        }
    }
    
    
    public int jobScheduling(int[] startTime, int[] endTime, int[] profit) {
        
        Job[] jobs = new Job[startTime.length];
        
        for (int i  = 0; i < startTime.length; i++) {
            
            jobs[i] = new Job(startTime[i], endTime[i], profit[i]);
        }
        
        Arrays.sort(jobs, new Comparator<Job>(){
            
            @Override
			public int compare(Job o1, Job o2) {
				
				return o1.endTime <= o2.endTime ? -1 : 1;
			}
        });
        
        
        int maxProfit = 0;
        for (int j = 1; j < jobs.length; j++) {
            
            jobs[j].maxProfit = Math.max(jobs[j].profit, jobs[j-1].maxProfit);
            
            int i = j-1;
            while (i >= 0) {
                
                if (!overlap(jobs[i], jobs[j])) {
                    
                    jobs[j].maxProfit = Math.max(jobs[j].maxProfit, 
                                              jobs[i].maxProfit+ jobs[j].profit);
                    
                    maxProfit = Math.max(maxProfit, jobs[j].maxProfit);
                    
                    break;
                }
                
                maxProfit = Math.max(maxProfit, jobs[j].maxProfit);
                --i;
            }
        }
        
        return maxProfit;
    }
    
    private boolean overlap(Job job1, Job job2) {
        
        return job1.endTime > job2.startTime;
    }
}


/*

Time Complexity - O(NlogN)
Space Complexity - O(N)

*/

```
