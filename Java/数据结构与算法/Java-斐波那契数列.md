# 斐波那契数列

```java
斐波那契数列指的是这样一个数列 0, 1, 1, 2, 3, 5, 8, 13, 21, 34, 55, 89, 144, 233，377，610，987，1597，2584，4181，6765，10946，17711，28657，46368。
这个数列从第3项开始，每一项都等于前两项之和。
```

程序实现

```java
 /**
     * 斐波那契数列的实现
     * 0,1,1,2,3,5,8,13,21......
     * @param 
     */
  //递归方式
    public long fib1(int n){
        if(n==0){ 
            return 0;
        }else if (n==1||n==2){
            return 1;
        }else {
           return fib(n-1)+fib(n-2); 
        }
        
    //采用递推的方式
public  int fib2(int n){
   if (n == 0) {
       return 0;
   }
  int a=0,b=1,c=1;
   for (int i = 0; i < n - 1; i++) {
       c= a+b;//第n天=第n-1天+第n-2天
       a = b; 	//第n-2天=第n-1天
       b = c;		//第n-1天=第n天
   }
   return c;
}
//采用数组方式
 public  int fib3(int n){
   if (n == 0) { //0特殊处理
       return 0;
   }
    int arr[] = new int[n];  
     if(n<2){	//1特殊处理
         arr[0]=arr[1]=2;
     }else{
         arr[0]=1;
     } 
        for (int i = 2; i < arr.length; i++) {  
            arr[i] = arr[i - 1] + arr[i - 2];  
        }  
   return arr[n-1];
}
```