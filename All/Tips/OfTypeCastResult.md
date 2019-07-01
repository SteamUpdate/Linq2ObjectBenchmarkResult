# `OfType<T>().Where()` => `Where().Cast<T>()`

## Code
```csharp
public List<Entity> Common()
{
    return list
        .OfType<Entity>()
        .Where(q => q.SomeStr == "456")
        .ToList();
}

public List<Entity> Optimized()
{
    return list
        .Where(q => q is Entity entity && entity.SomeStr == "456")
        .Cast<Entity>()
        .ToList();
}
```

## Framework
|    Method |    N |        Mean |      Error |     StdDev |      Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|-----------:|------------:|-------:|------:|------:|----------:|
|    Common |   10 |    378.0 ns |   2.326 ns |   2.176 ns |    378.1 ns | 0.0405 |     - |     - |     192 B |
| Optimized |   10 |    310.0 ns |   1.886 ns |   1.764 ns |    309.0 ns | 0.0353 |     - |     - |     168 B |
|    **Common** |  **100** |  **2,705.9 ns** |  **10.918 ns** |  **10.213 ns** |  **2,704.9 ns** | **0.0381** |     **-** |     **-** |     **192 B** |
| **Optimized** |  **100** |  **1,059.0 ns** |   **6.702 ns** |   **6.269 ns** |  **1,055.5 ns** | **0.0343** |     **-** |     **-** |     **168 B** |
|    Common | 1000 | 27,633.4 ns | 131.480 ns | 122.987 ns | 27,676.9 ns | 0.0305 |     - |     - |     248 B |
| Optimized | 1000 | 10,530.6 ns |  55.195 ns |  51.630 ns | 10,522.2 ns | 0.0458 |     - |     - |     224 B |

## Core
|    Method |    N |        Mean |      Error |     StdDev |      Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|-----------:|------------:|-------:|------:|------:|----------:|
|    Common |   10 |    436.6 ns |   2.285 ns |   2.137 ns |    436.3 ns | 0.0405 |     - |     - |     192 B |
| Optimized |   10 |    378.0 ns |   2.352 ns |   2.200 ns |    376.7 ns | 0.0353 |     - |     - |     168 B |
|    **Common** |  **100** |  **2,593.4 ns** |  **15.877 ns** |  **14.851 ns** |  **2,597.1 ns** | **0.0381** |     **-** |     **-** |     **192 B** |
| **Optimized** |  **100** |  **1,337.4 ns** |   **9.544 ns** |   **8.928 ns** |  **1,334.0 ns** | **0.0343** |     **-** |     **-** |     **168 B** |
|    Common | 1000 | 27,105.1 ns | 108.347 ns |  96.046 ns | 27,102.8 ns | 0.0305 |     - |     - |     248 B |
| Optimized | 1000 | 14,677.5 ns | 135.535 ns | 120.148 ns | 14,660.4 ns | 0.0458 |     - |     - |     224 B |