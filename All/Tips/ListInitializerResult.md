# `List<T>` Initializer

## Code
```csharp
public void Common()
{
    list = new List<long>
    {
        0, 1, 2, 3, 4, 5, 6, 7, 8, 9
    };
}

public void Optimized()
{
    list = new List<long>(10)
    {
        0, 1, 2, 3, 4, 5, 6, 7, 8, 9
    };
}
```

## Framework
|    Method |     Mean |     Error |    StdDev |   Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |---------:|----------:|----------:|---------:|-------:|------:|------:|----------:|
|    Common | 97.93 ns | 0.0428 ns | 0.0358 ns | 97.92 ns | 0.0712 |     - |     - |     336 B |
| Optimized | 30.56 ns | 0.1047 ns | 0.0979 ns | 30.56 ns | 0.0305 |     - |     - |     144 B |

## Core
|    Method |     Mean |     Error |    StdDev |   Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |---------:|----------:|----------:|---------:|-------:|------:|------:|----------:|
|    Common | 74.67 ns | 0.2148 ns | 0.2009 ns | 74.65 ns | 0.0712 |     - |     - |     336 B |
| Optimized | 24.93 ns | 0.0744 ns | 0.0696 ns | 24.93 ns | 0.0305 |     - |     - |     144 B |