# `Select().Select().Select()`

## Code
```csharp
public List<string> Common()
{
    return list
        .Select(q => q.SomeInt)
        .Select(q => new Entity { SomeStr = q.ToString() })
        .Select(q => q.SomeStr)
        .ToList();
}

public List<string> Optimized_1()
{
    return list
        .Select(q => {
            var entity = new Entity { SomeStr = q.SomeInt.ToString() };
            return entity.SomeStr;
        })
        .ToList();
}

public List<string> Optimized_2()
{
    var result = new List<string>();
    foreach (var item in list)
    {
        var entity = new Entity { SomeStr = item.SomeInt.ToString() };
        result.Add(entity.SomeStr);
    }
    return result;
}
```

## Framework
|      Method |    N |        Mean |       Error |      StdDev |      Median |   Gen 0 |  Gen 1 | Gen 2 | Allocated |
|------------ |----- |------------:|------------:|------------:|------------:|--------:|-------:|------:|----------:|
|      Common |   10 |  1,100.6 ns |   0.9584 ns |   0.8496 ns |  1,100.1 ns |  0.2975 |      - |     - |    1408 B |
| Optimized_1 |   10 |    884.7 ns |   0.6388 ns |   0.5975 ns |    884.8 ns |  0.2232 |      - |     - |    1056 B |
| Optimized_2 |   10 |    712.2 ns |   0.6960 ns |   0.6510 ns |    712.1 ns |  0.2060 |      - |     - |     976 B |
|      **Common** |  **100** |  **8,237.0 ns** |  **21.6301 ns** |  **20.2328 ns** |  **8,233.0 ns** |  **1.9073** |      **-** |     **-** |    **9032 B** |
| **Optimized_1** |  **100** |  **7,121.9 ns** |   **7.2675 ns** |   **6.7980 ns** |  **7,122.3 ns** |  **1.8387** |      **-** |     **-** |    **8680 B** |
| **Optimized_2** |  **100** |  **6,076.8 ns** |   **8.0789 ns** |   **7.5570 ns** |  **6,074.9 ns** |  **1.8158** |      **-** |     **-** |    **8600 B** |
|      Common | 1000 | 79,910.5 ns | 134.0582 ns | 125.3982 ns | 79,877.6 ns | 17.0898 | 0.1221 |     - |   81041 B |
| Optimized_1 | 1000 | 70,828.4 ns |  53.8872 ns |  50.4061 ns | 70,830.2 ns | 17.0898 | 0.1221 |     - |   80689 B |
| Optimized_2 | 1000 | 60,297.9 ns |  95.9103 ns |  89.7146 ns | 60,319.5 ns | 17.0288 |      - |     - |   80609 B |

## Core
|      Method |    N |        Mean |      Error |     StdDev |      Median |   Gen 0 |  Gen 1 | Gen 2 | Allocated |
|------------ |----- |------------:|-----------:|-----------:|------------:|--------:|-------:|------:|----------:|
|      Common |   10 |    600.7 ns |  1.2453 ns |  1.1648 ns |    601.0 ns |  0.2518 |      - |     - |    1192 B |
| Optimized_1 |   10 |    449.0 ns |  0.7847 ns |  0.6553 ns |    449.1 ns |  0.1812 |      - |     - |     856 B |
| Optimized_2 |   10 |    363.1 ns |  0.4879 ns |  0.4564 ns |    363.2 ns |  0.2065 |      - |     - |     976 B |
|      **Common** |  **100** |  **3,925.5 ns** |  **7.2315 ns** |  **6.7644 ns** |  **3,924.1 ns** |  **1.6251** |      **-** |     **-** |    **7672 B** |
| **Optimized_1** |  **100** |  **3,338.5 ns** |  **6.4674 ns** |  **6.0496 ns** |  **3,339.4 ns** |  **1.5526** |      **-** |     **-** |    **7336 B** |
| **Optimized_2** |  **100** |  **3,003.1 ns** |  **3.9206 ns** |  **3.6674 ns** |  **3,002.9 ns** |  **1.8196** |      **-** |     **-** |    **8600 B** |
|      Common | 1000 | 38,439.4 ns | 81.5673 ns | 72.3073 ns | 38,435.6 ns | 15.3198 | 0.0610 |     - |   72472 B |
| Optimized_1 | 1000 | 33,691.0 ns | 65.5696 ns | 61.3339 ns | 33,705.8 ns | 15.2588 | 0.0610 |     - |   72136 B |
| Optimized_2 | 1000 | 29,504.5 ns | 72.0618 ns | 67.4066 ns | 29,485.4 ns | 17.0593 |      - |     - |   80608 B |
