# `List<T>.TrueForAll(q => q...)`

## Code
```csharp
public bool Common()
{
    return list.All(q => q.SomeInt > 0);
}

public bool Optimized()
{
    return list.TrueForAll(q => q.SomeInt > 0);
}
```

## Framework
|    Method |    N |      Mean |     Error |    StdDev |    Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |----------:|----------:|----------:|----------:|-------:|------:|------:|----------:|
|    Common |   10 | 24.043 ns | 0.1390 ns | 0.1232 ns | 23.992 ns | 0.0085 |     - |     - |      40 B |
| Optimized |   10 |  3.056 ns | 0.0258 ns | 0.0241 ns |  3.045 ns |      - |     - |     - |         - |
|    **Common** |  **100** | **24.090 ns** | **0.1531 ns** | **0.1432 ns** | **24.071 ns** | **0.0085** |     **-** |     **-** |      **40 B** |
| **Optimized** |  **100** |  **3.047 ns** | **0.0338 ns** | **0.0316 ns** |  **3.034 ns** |      **-** |     **-** |     **-** |         **-** |
|    Common | 1000 | 24.016 ns | 0.1335 ns | 0.1249 ns | 24.020 ns | 0.0085 |     - |     - |      40 B |
| Optimized | 1000 |  3.052 ns | 0.0279 ns | 0.0261 ns |  3.039 ns |      - |     - |     - |         - |

## Core
|    Method |    N |      Mean |     Error |    StdDev |    Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |----------:|----------:|----------:|----------:|-------:|------:|------:|----------:|
|    Common |   10 | 26.356 ns | 0.2216 ns | 0.2073 ns | 26.356 ns | 0.0085 |     - |     - |      40 B |
| Optimized |   10 |  4.541 ns | 0.0293 ns | 0.0274 ns |  4.542 ns |      - |     - |     - |         - |
|    **Common** |  **100** | **26.545 ns** | **0.2644 ns** | **0.2344 ns** | **26.562 ns** | **0.0085** |     **-** |     **-** |      **40 B** |
| **Optimized** |  **100** |  **4.219 ns** | **0.0315 ns** | **0.0295 ns** |  **4.219 ns** |      **-** |     **-** |     **-** |         **-** |
|    Common | 1000 | 26.777 ns | 0.3522 ns | 0.3294 ns | 26.757 ns | 0.0085 |     - |     - |      40 B |
| Optimized | 1000 |  4.181 ns | 0.0260 ns | 0.0243 ns |  4.180 ns |      - |     - |     - |         - |