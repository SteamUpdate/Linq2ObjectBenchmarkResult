# `Where().Where().Where()`

## Code
```csharp
public List<Entity> Common()
{
    return list
        .Where(q => !string.IsNullOrEmpty(q.SomeStr))
        .Where(q => q.SomeStr == "456")
        .Where(q => q.SomeInt == 456)
        .ToList();
}

public List<Entity> Optimized_1()
{
    return list
        .Where(q => !string.IsNullOrEmpty(q.SomeStr) && q.SomeStr == "456" && q.SomeInt == 456)
        .ToList();
}

public List<Entity> Optimized_2()
{
    var result = new List<Entity>();
    foreach (var item in list)
    {
        if (string.IsNullOrEmpty(item.SomeStr))
        {
            continue;
        }

        if (item.SomeStr != "456")
        {
            continue;
        }

        if (item.SomeInt != 456)
        {
            continue;
        }

        result.Add(item);
    }
    return result;
}
```

## Framework
|      Method |    N |         Mean |      Error |     StdDev |       Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|------------ |----- |-------------:|-----------:|-----------:|-------------:|-------:|------:|------:|----------:|
|      Common |   10 |    268.72 ns |  0.3618 ns |  0.3385 ns |    268.63 ns | 0.0949 |     - |     - |     448 B |
| Optimized_1 |   10 |    159.57 ns |  0.1071 ns |  0.1002 ns |    159.54 ns | 0.0236 |     - |     - |     112 B |
| Optimized_2 |   10 |     63.66 ns |  0.0644 ns |  0.0602 ns |     63.66 ns | 0.0085 |     - |     - |      40 B |
|      **Common** |  **100** |  **1,355.25 ns** |  **1.4957 ns** |  **1.2490 ns** |  **1,355.64 ns** | **0.0935** |     **-** |     **-** |     **448 B** |
| **Optimized_1** |  **100** |    **876.94 ns** |  **0.3427 ns** |  **0.3206 ns** |    **877.00 ns** | **0.0229** |     **-** |     **-** |     **112 B** |
| **Optimized_2** |  **100** |    **488.02 ns** |  **0.1690 ns** |  **0.1581 ns** |    **487.97 ns** | **0.0076** |     **-** |     **-** |      **40 B** |
|      Common | 1000 | 14,078.89 ns | 20.8514 ns | 19.5044 ns | 14,078.98 ns | 0.0916 |     - |     - |     448 B |
| Optimized_1 | 1000 |  9,986.52 ns | 19.6071 ns | 18.3405 ns |  9,989.58 ns | 0.0153 |     - |     - |     112 B |
| Optimized_2 | 1000 |  6,363.19 ns |  4.8572 ns |  4.5435 ns |  6,361.60 ns | 0.0076 |     - |     - |      40 B |

## Core
|      Method |    N |         Mean |      Error |     StdDev |       Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|------------ |----- |-------------:|-----------:|-----------:|-------------:|-------:|------:|------:|----------:|
|      Common |   10 |    439.89 ns |  0.4575 ns |  0.4280 ns |    439.82 ns | 0.0949 |     - |     - |     448 B |
| Optimized_1 |   10 |    208.02 ns |  0.2193 ns |  0.2051 ns |    207.99 ns | 0.0236 |     - |     - |     112 B |
| Optimized_2 |   10 |     79.62 ns |  0.1172 ns |  0.1096 ns |     79.65 ns | 0.0085 |     - |     - |      40 B |
|      **Common** |  **100** |  **1,844.59 ns** |  **3.5650 ns** |  **3.3347 ns** |  **1,844.14 ns** | **0.0935** |     **-** |     **-** |     **448 B** |
| **Optimized_1** |  **100** |  **1,095.61 ns** |  **0.6318 ns** |  **0.5910 ns** |  **1,095.38 ns** | **0.0229** |     **-** |     **-** |     **112 B** |
| **Optimized_2** |  **100** |    **523.51 ns** |  **2.8304 ns** |  **2.6475 ns** |    **523.24 ns** | **0.0076** |     **-** |     **-** |      **40 B** |
|      Common | 1000 | 18,655.93 ns | 14.1385 ns | 13.2251 ns | 18,652.63 ns | 0.0916 |     - |     - |     448 B |
| Optimized_1 | 1000 | 12,840.22 ns |  9.1539 ns |  8.1147 ns | 12,838.40 ns | 0.0153 |     - |     - |     112 B |
| Optimized_2 | 1000 |  7,904.85 ns | 14.7953 ns | 13.1156 ns |  7,902.47 ns |      - |     - |     - |      40 B |
