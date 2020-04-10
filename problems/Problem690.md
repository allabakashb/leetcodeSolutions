```java

class Solution {
    public int getImportance(List<Employee> employees, int id) {
        
        Map<Integer, Employee> empMap = new HashMap<>();
        
        for (Employee em: employees) {
            
            empMap.put(em.id, em);
        }
                
        return getImpValue(empMap.get(id), empMap);
    }
    
    private int getImpValue(Employee em, Map<Integer, Employee> empMap) {
        
        int imp = em.importance;
        
        for (Integer id: em.subordinates) {
            
            imp += getImpValue(empMap.get(id), empMap);
        }
                
        return imp;
    }
}

/*

Time Complexity - O(N)
Space Complexity - O(N)

*/
```
