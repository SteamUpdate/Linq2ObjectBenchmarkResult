# `List<T>.Exists(q => q...)`

## Code
```csharp
public bool Common()
{
    return list.Any(q => q.SomeInt == 456);
}

public bool Optimized()
{
    return list.Exists(q => q.SomeInt == 456);
}
```

## Framework
|    Method |    N |         Mean |      Error |     StdDev |       Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-------------:|-----------:|-----------:|-------------:|-------:|------:|------:|----------:|
|    Common |   10 |    129.16 ns |  0.8728 ns |  0.8165 ns |    128.70 ns | 0.0083 |     - |     - |      40 B |
| Optimized |   10 |     20.28 ns |  0.1016 ns |  0.0950 ns |     20.24 ns |      - |     - |     - |         - |
|    **Common** |  **100** |  **1,048.40 ns** |  **6.2587 ns** |  **5.5482 ns** |  **1,047.68 ns** | **0.0076** |     **-** |     **-** |      **40 B** |
| **Optimized** |  **100** |    **193.30 ns** |  **1.0225 ns** |  **0.9064 ns** |    **192.96 ns** |      **-** |     **-** |     **-** |         **-** |
|    Common | 1000 | 10,254.20 ns | 57.2147 ns | 53.5186 ns | 10,224.16 ns |      - |     - |     - |      40 B |
| Optimized | 1000 |  1,801.20 ns |  8.8114 ns |  8.2422 ns |  1,805.47 ns |      - |     - |     - |         - |

## Core
|    Method |    N |         Mean |      Error |     StdDev |       Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-------------:|-----------:|-----------:|-------------:|-------:|------:|------:|----------:|
|    Common |   10 |    144.63 ns |  0.6020 ns |  0.5631 ns |    144.51 ns | 0.0083 |     - |     - |      40 B |
| Optimized |   10 |     21.52 ns |  0.0999 ns |  0.0935 ns |     21.51 ns |      - |     - |     - |         - |
|    **Common** |  **100** |  **1,191.31 ns** |  **3.6397 ns** |  **3.4046 ns** |  **1,191.10 ns** | **0.0076** |     **-** |     **-** |      **40 B** |
| **Optimized** |  **100** |    **187.82 ns** |  **0.2153 ns** |  **0.1797 ns** |    **187.88 ns** |      **-** |     **-** |     **-** |         **-** |
|    Common | 1000 | 11,564.54 ns | 84.1330 ns | 78.6981 ns | 11,576.83 ns |      - |     - |     - |      40 B |
| Optimized | 1000 |  1,838.30 ns |  8.4396 ns |  7.8944 ns |  1,839.03 ns |      - |     - |     - |         - |