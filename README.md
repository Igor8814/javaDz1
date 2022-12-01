ДЗ к семинару 1
```java
package java_program;

import java.util.Arrays;
import java.util.Random;
import java.util.stream.Collectors;
```

public class program {
    final static int Min = -1000;
    final static int Max = 1000;

    public static void main(String[] args) {

        //1

        int i = randomNumb(Min, Max);
        System.out.println(i);

        //2

        int n = highestBitNumber(i);
        System.out.println(n);
        
        //3

        int[] m1 = multipleNumb(i, n, Short.MAX_VALUE);
        System.out.println("Массив m1 из " + m1.length + " элементов: " + Arrays.stream(m1).mapToObj(String::valueOf).collect(Collectors.joining(", ")));
        
        //4
        
        int[] m2 = notMultipleArr(i, n, Short.MIN_VALUE);
        System.out.println("Массив m2 из " + m2.length + " элементов: " + Arrays.stream(m2).mapToObj(String::valueOf).collect(Collectors.joining(", ")));

    }    
    public static int randomNumb(int min, int max) {
        return new Random().nextInt(min, max);
        
    }    
    public static int highestBitNumber(int n) {
        int res = 0;
        while (n != 1) {
            n >>= 1;
            res++;
        }
        return res;                                                                  
               
    }
    public static int[] multipleNumb(int i, int n, int limit){
        int arr = 0;
        for (int j = i; j <= limit; j++){
            if(j % n == 0) 
                arr++;
            
        }
        int[] res = new int[arr];
        for (int j = i, k = 0; j <= limit; j++){
            if(j % n == 0){
                res[k] = j;
                k++;
            }
        }
        return res;
    }
    public static int[] notMultipleArr(int i, int n, int limit){
        int arr = 0;
        for (int j = i; j <= limit; j++){
            if(j % n != 0) 
                arr++;
            
        }
        int[] res = new int[arr];
        for (int j = i, k = 0; j <= limit; j++){
            if(j % n != 0){
                res[k] = j;
                k++;
            }
        }
        return res;

    }
}    
    
~~~
