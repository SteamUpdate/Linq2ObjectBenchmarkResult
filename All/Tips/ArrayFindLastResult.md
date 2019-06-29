# `Array.FindLast(q => q...)`

## Code
```csharp
public Entity Common()
{
    return array.LastOrDefault(q => q.SomeInt == 456);
}

public Entity Optimized()
{
    return Array.FindLast(array, q => q.SomeInt == 456);
}
```

## Framework
|    Method |    N |        Mean |      Error |     StdDev |      Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|-----------:|------------:|-------:|------:|------:|----------:|
|    Common |   10 |    90.76 ns |  0.3682 ns |  0.3444 ns |    90.59 ns | 0.0067 |     - |     - |      32 B |
| Optimized |   10 |    19.02 ns |  0.0425 ns |  0.0397 ns |    19.03 ns |      - |     - |     - |         - |
|    **Common** |  **100** |   **683.83 ns** |  **0.8453 ns** |  **0.7494 ns** |   **683.87 ns** | **0.0067** |     **-** |     **-** |      **32 B** |
| **Optimized** |  **100** |   **187.73 ns** |  **0.0355 ns** |  **0.0296 ns** |   **187.73 ns** |      **-** |     **-** |     **-** |         **-** |
|    Common | 1000 | 6,911.77 ns | 28.1917 ns | 26.3705 ns | 6,922.86 ns |      - |     - |     - |      32 B |
| Optimized | 1000 | 1,007.22 ns |  1.3144 ns |  1.2295 ns | 1,007.58 ns |      - |     - |     - |         - |

## Core
|    Method |    N |        Mean |     Error |    StdDev |      Median | Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|----------:|----------:|------------:|------:|------:|------:|----------:|
|    Common |   10 |    87.58 ns | 0.0996 ns | 0.0832 ns |    87.55 ns |     - |     - |     - |         - |
| Optimized |   10 |    17.32 ns | 0.0732 ns | 0.0649 ns |    17.30 ns |     - |     - |     - |         - |
|    **Common** |  **100** |   **572.09 ns** | **3.0006 ns** | **2.6600 ns** |   **571.15 ns** |     **-** |     **-** |     **-** |         **-** |
| **Optimized** |  **100** |   **160.63 ns** | **0.7327 ns** | **0.6854 ns** |   **160.55 ns** |     **-** |     **-** |     **-** |         **-** |
|    Common | 1000 | 2,957.00 ns | 9.8448 ns | 9.2089 ns | 2,954.64 ns |     - |     - |     - |         - |
| Optimized | 1000 |   855.61 ns | 3.2651 ns | 2.8944 ns |   854.84 ns |     - |     - |     - |         - |
