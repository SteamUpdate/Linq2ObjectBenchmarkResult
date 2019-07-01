# `OfType<T>().Where()` => `Where().OfType<T>()`

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
        .OfType<Entity>()
        .ToList();
}
```

## Framework
|    Method |    N |        Mean |      Error |     StdDev |      Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|-----------:|------------:|-------:|------:|------:|----------:|
|    Common |   10 |    376.6 ns |   1.758 ns |   1.644 ns |    376.1 ns | 0.0405 |     - |     - |     192 B |
| Optimized |   10 |    197.4 ns |   1.459 ns |   1.364 ns |    196.6 ns | 0.0355 |     - |     - |     168 B |
|    **Common** |  **100** |  **2,714.6 ns** |  **21.248 ns** |  **19.876 ns** |  **2,715.5 ns** | **0.0381** |     **-** |     **-** |     **192 B** |
| **Optimized** |  **100** |    **951.6 ns** |   **4.233 ns** |   **3.960 ns** |    **953.5 ns** | **0.0353** |     **-** |     **-** |     **168 B** |
|    Common | 1000 | 27,683.4 ns | 160.596 ns | 150.222 ns | 27,656.9 ns | 0.0305 |     - |     - |     248 B |
| Optimized | 1000 | 10,486.3 ns |  66.155 ns |  61.881 ns | 10,459.8 ns | 0.0458 |     - |     - |     224 B |

## Core
|    Method |    N |        Mean |      Error |     StdDev |      Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|-----------:|------------:|-------:|------:|------:|----------:|
|    Common |   10 |    434.2 ns |   1.836 ns |   1.717 ns |    433.9 ns | 0.0405 |     - |     - |     192 B |
| Optimized |   10 |    297.5 ns |   2.484 ns |   2.202 ns |    298.4 ns | 0.0353 |     - |     - |     168 B |
|    **Common** |  **100** |  **2,602.0 ns** |  **15.694 ns** |  **14.680 ns** |  **2,597.4 ns** | **0.0381** |     **-** |     **-** |     **192 B** |
| **Optimized** |  **100** |  **1,281.8 ns** |   **8.519 ns** |   **7.968 ns** |  **1,282.7 ns** | **0.0343** |     **-** |     **-** |     **168 B** |
|    Common | 1000 | 27,359.2 ns | 191.447 ns | 179.079 ns | 27,366.4 ns | 0.0305 |     - |     - |     248 B |
| Optimized | 1000 | 14,491.0 ns | 101.251 ns |  94.710 ns | 14,489.5 ns | 0.0458 |     - |     - |     224 B |
