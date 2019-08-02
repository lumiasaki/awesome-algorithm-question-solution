# Fibonacci （斐波那契数列实现）



## From

《剑指offer》Question No.9



## Question

Code implementation of fibonacci.



## Solution  



### C++

```c++
long long Fibonacci(unsigned n)
{
    int result[2] = {0, 1};
    
    if(n < 2){
        return result[n];
    }
    
    long long  fibNMinusOne = 1;
    long long  fibNMinusTwo = 0;
    
    long long  fibN = 0;
    
    for(unsigned int i = 2; i <= n; ++ i){
        
        fibN = fibNMinusOne + fibNMinusTwo;
        
        fibNMinusTwo = fibNMinusOne;
        fibNMinusOne = fibN;
    }
    
    return fibN;
}
```

### Java

```java
public static int Fibonacci( int n ){

    if( n==0 || n==1 ){
         return 1;
    }
    else if(n>1){

        return Fibonacci(n-1)+Fibonacci(n-2);
    }
    else{
    
        return 0;
    }
}
```

### Swift

#### 递归

```swift
func fib(i: Int) -> Int {
    if i == 0 {
        return 0
    }

    if i == 1 {
        return 1
    }

    return fib(i - 1) + fib(i - 2)
}
```

#### 非递归

```swift
func fib(i: Int) -> Int {
    if i == 0 {
        return 0
    }

    if i == 1 {
        return 1
    }

    var array: [Int] = Array.init(repeating: 0, count: i)

    array[0] = 1
    array[1] = 1

    for index in 2 ..< i {
        array[index] = array[index - 1] + array[index - 2]
    }

    return array[i - 1]
}
```


