### java hello world
```java

class Solution{
    static void printHelloWorld(){
        // code here
        System.out.println("Hello World");
    }
}
```
### Precise Format 
```java

class Geeks{
    
    static void printInFormat(float a, float b){
        float result = a/b;
        System.out.print(result);
        System.out.printf(" %.3f",result); 
        
        
    }    
    
}
```
### if-else (Decision Making)

```java

class Solution {
    public static String compareNM(int n, int m) {
        if(n<m){
           return "lesser";
        }
        else if(n==m){
            return "equal";
        }
        else{
            return "greater";
        }
    }

}
```
### start coding
```java


class Geeks{
    
    // Function to print hello
    static void printHello(){
        
        System.out.print("Hello World");
        
    }
    
}
```
### Taking input
```java


class Geeks {

    // Function to take input using Scanner class
    static void IOFunction() {
        Scanner sc = new Scanner(System.in);
        int t = sc.nextInt();

        while (t-- > 0) {
            int a=sc.nextInt();
            float b=sc.nextFloat();
            long c=sc.nextLong();
            byte d=sc.nextByte();
            sc.nextLine();//consume the leftover newline
            String s=sc.nextLine();
            
            System.out.println(a);
            System.out.println(b);
            System.out.println(c);
            System.out.println(d);
            System.out.println(s);
            

            
        }
    }
}
```
### Convert String to LowerCase

```java


class Solution {
    static String toLower(String s) {
       String t=s.toLowerCase();
       return t;
    }
}
```
### The New Line
```java

class Geeks{
    
    // Function to print each word in single line
    static void printIndividualLine(){
        
        System.out.println("Geeks\nfor\nGeeks");
        
    }
    
}
```

