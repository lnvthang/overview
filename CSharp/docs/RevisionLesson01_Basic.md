# REVISION LESSON 01 - BASIC

## Outline
1. Define
2. Console.WriteLine
3. TryParse
4. object, boxing and unboxing, var
5. dynamic
6. goto
7. ref and out
8. Stopwatch
9. Note

---

## Fundamental knowledge

### 1. Define
- C# is build 2 language programming based on foundation knowledge C++ and Java
- Data type: Memory is 2 parts STACK and HEAP
    - Stack: Allocated when the program is compiled (write code).
    - Heap:  Allocated when running a program (start program).
- Reference: [STACK and HEAP](https://www.geeksforgeeks.org/stack-vs-heap-memory-allocation/)

---

### 2. Console.WriteLine
- Syntax:
```csharp
int Result = 7;
Console.WriteLine("Result = {0}", Result);
```

---

### 3. TryParse
- TryParse: **int.TryParse(Data1, out Result);**
    - Syntax:
```csharp
int Result;
bool isSuccess;
string Data1 = "10";

isSuccess = int.TryParse(Data1, out Result);
Console.WriteLine(isSuccess == true ? "Success" : "Failed");
Console.WriteLine("Result = {0}", Result);
```
- Reference:
    - Parse, Convert, (byte)10
    - String to Int, Int to String, ...

---

### 4. object, boxing and unboxing, var
- object
    - Data type
    - It is possible not to set a value when declaring a variable
    - Able to cast, functions return variables

- boxing & unboxing
    - Convert value data type to reference data type and vice versa for unboxing.
    - Syntax
```csharp
Boxing
    int value = 10; || string value = "10";
    object objectValue = value;

Unboxing
    int newValue = (int)objectValue; // Only error when start programming with string type
```
- var
    - keywork
    - Must set value when declaring a variable
    - No type casting
    - Specify the data type when declaring

---

### 5. dynamic
- Keyword
- It is possible not to set value when declaring variable
- Able casting type
- Only specify data type when starting program
- Syntax
```csharp
dynamic str = "CSharp-Dynamic";
str++;
```

---

### 6. goto
- Syntax
```csharp
goto Csharp;
Console.WriteLine("Hello, World!");
Csharp:
Console.WriteLine("Hello, Csharp!");
```

- Ouput:
```csharp
Hello, Csharp!
```

- Example:
```csharp
    int num = 1;
    switch (num)
    {
        case 1:
            Console.WriteLine("Case 1");
            break;
        case 2:
            Console.WriteLine("Case 2");
            goto case 1;
        default:
            break;
    }

=> Output: 
Case 1 
Case 2
```

---

### 7. ref and out
- Passing values: passing value from main function to the other function (void), but the value is not change in main
- Passing references: Using ref - out to get new value from the other function is executed value to main function
- ref:
    - No need initial value in B function, then main function will get the new value from function B executed
- Syntax: 
```csharp
    static void main (string[] args) {
        int value = 10;
        IncreaseValue(ref value);
        Console.WriteLine("Value: {0}", value);
        Console.ReadLine();
    }

    static void IncreaseValue(ref int value) {
        value ++;
    }
```
-  Output:
```csharp
    Value: 11
```
---
- out:
    - Need initial value in B function, then main function will get the new value from function B executed by initial value
- Syntax
```csharp
    static void Main(string[] args)
    {
        int value = 10;
        IncreaseValue(out value);
        Console.WriteLine("Value: {0}", value);
        Console.ReadLine();
    }

    static void IncreaseValue(out int value)
    {
        value = 0;
        value++;
    }
```
-  Output:
```csharp
    Value: 1
```

---

### 8. Stopwatch
- Checking speed argument
- Syntax
```csharp
Stopwatch start = new Stopwatch();
start.Start();
...
start.Stop();
Console.WriteLine(start.Elapsed.Seconds, start.Elapsed.Miliseconds);
```

---

### 9. Note
- Prefer using foreach in array processing than for loop
- Using StringBuilder to insert avaiable string
    - Syntax
    ```csharp
    StringBuilder strBuilder = new StringBuilder("C");
    strBuilder.Append("Sharp");
    ```
- The differences between String and StringBuilder are:
    - String: Initial memories to insert
    - StringBuilder: Open old memories to insert new string into old string

---