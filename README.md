# Random
Consideration about how to get unique random number fastest and unbiased probability.

## Ways to get unique random number
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

This code can takes time infinity.
also, It takes time longer when `max` and `count` are similar.
    
### 2. Use `ArrayList`

    final int max = 1000;
    final int count = 1000;
    
    ArrayList<Integer> list = new ArrayList(max);
    for (int i = 0; i < max; i++)
    {
        list.add(i);
    }
    
    for (int i = 0; i < count; i++)
    {
        int index = random.nextInt(list.length);
        int rand = list.remove(index);
        
        System.out.println(rand);
    }
    
This code can takes time longer when `max` is big. (for create array list)


### Compare Way 1(HashSet) and Way 2(ArrayList)

#### Think before the test
I think way2(ArrayList) is faster in most situations because it never occur duplicate.

#### Test Code

#### Test Result

#### After the test
but It's not. The creating array list and remove element is very slow.
