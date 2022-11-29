```java
public class Fibonacci {

//n est le sixième nombre dans la série fibonacci
private static long[] fibonacciCache;
public static void main(String[] args) {
		int n = 92; 
		fibonacciCache = new long[n + 1];
		
		for(int i = 0; i<= n; i++) {
		System.out.println(fibonacciOp(i) + " " + i);
		}
	}

private static long fibonacci(int n) {
		//base case de fonction recursive :
		if(n <= 1) {
			return n;
		}
		return (fibonacci(n - 1) + fibonacci(n - 2));
	}	
	```
	cet algo est très lent, pour trouver le 5eme : f(5) = f4 + f3
f4 = f3 + f2 .. etc -> base case (0
Solution => [[mémoïsation]] ! pour ne pas avoir à recalculer le nb calculé précédemment 

```java
private static long fibonacciOp(int n) {
		//base case de fonction recursive :
		if(n <= 1) {
			return n;
		}		
		if(fibonacciCache[n] != 0 )  { //primitive long jamais null
			return fibonacciCache[n];			
		} 		
		long nthFibonacciNumber = (fibonacciOp(n - 1) + fibonacciOp(n - 2));
		fibonacciCache[n] = nthFibonacciNumber;
		return nthFibonacciNumber;
	}
}
```
#mémoïsation
#recursive 
#cache