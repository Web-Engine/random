# Random
Consideration about how to get unique random number fastest and unbiased probability.

## Ways
The code below is written in Java.

### 1. Use `HashSet` and check duplicate

    final int max = 1000; // exclude 0~999
    final int count = 1000;
    
    HashSet<Integer> set = new HashSet(max);
    Random random = new Random();
    
    for (int i = 0; i < count;)
    {
      int rand = random.nextInt(max);
      
      if (set.contains(rand)) continue;
      
      set.add(rand);
      i++;
      System.out.println(rand);
    }
