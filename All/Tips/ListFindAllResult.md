# `List<T>.FindAll(q => q...)`

## Code
```csharp
public List<Entity> Common()
{
    return list.Where(q => q.SomeInt == 456).ToList();
}

public List<Entity> Optimized()
{
    return list.FindAll(q => q.SomeInt == 456);
}
```

## Framework
|    Method |    N |        Mean |      Error |     StdDev |      Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|-----------:|------------:|-------:|------:|------:|----------:|
|    Common |   10 |   144.30 ns |  0.0694 ns |  0.0649 ns |   144.30 ns | 0.0236 |     - |     - |     112 B |
| Optimized |   10 |    34.88 ns |  0.0419 ns |  0.0372 ns |    34.88 ns | 0.0085 |     - |     - |      40 B |
|    **Common** |  **100** |   **694.25 ns** |  **0.2950 ns** |  **0.2759 ns** |   **694.24 ns** | **0.0229** |     **-** |     **-** |     **112 B** |
| **Optimized** |  **100** |   **248.97 ns** |  **0.1148 ns** |  **0.1017 ns** |   **248.96 ns** | **0.0081** |     **-** |     **-** |      **40 B** |
|    Common | 1000 | 6,256.96 ns | 16.0592 ns | 15.0218 ns | 6,251.43 ns | 0.0229 |     - |     - |     112 B |
| Optimized | 1000 | 2,405.55 ns |  1.4936 ns |  1.2472 ns | 2,405.46 ns | 0.0076 |     - |     - |      40 B |

## Core
|    Method |    N |        Mean |     Error |    StdDev |      Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|----------:|----------:|------------:|-------:|------:|------:|----------:|
|    Common |   10 |   182.91 ns | 0.2799 ns | 0.2618 ns |   182.82 ns | 0.0236 |     - |     - |     112 B |
| Optimized |   10 |    34.24 ns | 0.0628 ns | 0.0557 ns |    34.24 ns | 0.0085 |     - |     - |      40 B |
|    **Common** |  **100** |   **889.69 ns** | **1.4375 ns** | **1.3446 ns** |   **889.70 ns** | **0.0229** |     **-** |     **-** |     **112 B** |
| **Optimized** |  **100** |   **225.77 ns** | **0.3804 ns** | **0.3559 ns** |   **225.64 ns** | **0.0083** |     **-** |     **-** |      **40 B** |
|    Common | 1000 | 7,940.10 ns | 8.7399 ns | 8.1753 ns | 7,937.98 ns | 0.0153 |     - |     - |     112 B |
| Optimized | 1000 | 2,120.80 ns | 6.5099 ns | 6.0894 ns | 2,120.51 ns | 0.0076 |     - |     - |      40 B |
