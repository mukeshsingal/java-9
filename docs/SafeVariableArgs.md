# Variable Arguments Annotations 

> Variable Arguments was introduced in Java 1.7, with Java 1.9 couple of enhancement got introduced. 

Why VarArgs?
Before 1.7 JDK, if you want to use same logic required for variable number of arguments, you have to create function for all combination like below example.
There are some use-cases when you may required to pass variable number of arguments. Now you can use ```...``` operator to pass variable number of arguments.

For eg.  
```java
 public class SafeArgs{
     public static void main(String[] args) {
         System.out.println("Sum of two numbers " + sum(1, 2));
         System.out.println("Sum of three numbers " + sum(1, 2, 3));
     }
 
     public static int sum(int... nums){
         int sum = 0;
         for (int num: nums){
             sum = sum + num;
         }
         return sum;
     }
 }
```
