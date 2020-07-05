# Sort Descending
```java
class Scratch {
    public static void main(String[] args) {
        CompareService<Integer> service = new CompareService<Integer>() {
            @Override
            boolean isALessThenB(Integer a, Integer b) {
                return a < b;
            }
        };
        Integer[] array = new Integer[]{4, 6, 5, 4, 12, 6, 34, 42};
        service.sortAscending(array);
        for (Integer integer : array) {
            System.out.println(integer);
        }
    }
}

abstract class  CompareService<T>{
    public T[] sortAscending(T [] array){
        if(array == null) return null;
        if(array.length <=1) return array;
        int step = 1;
        int i = 1;
        T temp;
        while (i < array.length) {
            if(isALessThenB(array[i-1], array[i])){
                temp = array[i-1];
                array[i-1] = array[i];
                array[i] = temp;
                if(i > 1) i--;
            }
            else
                i = ++step;
        }
        return array;
    }
    abstract boolean isALessThenB(T a, T b);
}
```