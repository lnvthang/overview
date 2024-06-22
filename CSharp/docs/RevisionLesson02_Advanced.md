# REVISION LESSON 02 - ADVANCED

## Outline
1. ArrayList and List
2. HashTable
3. BitArray
4. Generic
5. Dictionary
6. Tuple
7. Delegate
8. Threading (Note)
9. Task
10. IEnumerable VS IEnumerator
11. 

---

## Fundamental knowledge

### 1. ArrayList

- ArrayList
    - Add element into ArrayList
    - Be able to add all data type(int, string, float, double, null, ...) into the ArrayList same
    - Syntax:
    ```csharp
    ArrayList MyArr = new ArrayList(10);
    MyArr.Add(new Person("Nguyen Van A", 18));
    ```

    - Copy ArrayList from other ArrayList
    - Syntax:
    ```csharp
    ArrayList MyArrList  = new ArrayList(10);
    ArrayList MyArrList2  = new ArrayList(MyArrList1);
    ArrayList MyArrList3 = MyArrList2; // Difference
    ```

    - Searching faster, should order element in list beforehand using BinarySearch(object Value) method.

- List
    - Combine with: **ArrayList + Generic**
    - Syntax:
```csharp
List<int> myList = new List<int>(10);
```

- Array
```csharp
string[] myStr = new string[10];
```

---

### 2. HashTable

- key - value
- Syntax:
```csharp
HashTable MyHash = new HashTable();
MyHash.Add("C","Sharp");
foreach (DictionaryEntry item in MyHash) {
    Console.Writeline(item.key + "\t" + item.value);
}
```
- If you access hash by key and hash isn't value, hash will not return error, you have to check hash null

---

### 3. BitArray

- Saving memory: BitArray < bool[]
- Return: true  = 1 , false = 0

### 4. Generic

- Generic type: `<`T`>`
- e.g

```csharp
public static void Swap<T>(ref <T> a, ref <T> b) {};

Swap<int>(ref a, ref b);

----------------------------------------------------

public class MyGeneric<T> {
    public T[] items; ...
}

```

---

### 5. Dictionary
- Dictionary: HashTable + Generic
- Syntax

```csharp
Dictionary<string | int, string> MyDic = new Dictionary<string | int, string>(5);
Dictionary<string | int, TValue> MyDic = new Dictionary<string | int, TValue>();
```

---

### 6. Tuple
- Using tuple to return many values for method
- Syntax

```csharp
var MyTuple = new Tuple<int, string, bool>(1, "CSharp", true);
Console.WriteLine(MyTuple.Item1, MyTuple.Item2, MyTuple.Item3);
```

---

### 7. Delegate
- The function is parameter in new MyDelegate() to reference to method, delegate can + or - function
- Syntax

```csharp
class Program {
delegate int MyDelegate (string s)
static void Main(string[] args) {
MyDelegate convertToInt = new MyDelegate(ConvertStringToInt);
int valueConverted = convertToInt("35");
}
static int ConvertStringToInt(string stringValue) {}
}
```
- Reference:
    - Event of delegate

---

### 8. Threading
- Syntax

```csharp
Thread t = new Thread(() => {
    Thread.Sleep(TimeSpan.FromSeconds(1));
});
t.IsBackground = false;
t.Start();

```

---

### 9. Task
- Syntax: