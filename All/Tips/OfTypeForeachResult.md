# `OfType<T>().Where()` => `foreach`

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
    var result = new List<Entity>();
    foreach (var item in list)
    {
        if (item is Entity entity && entity.SomeStr == "456")
        {
            result.Add(entity);
        }
    }
    return result;
}
```

## Framework
|    Method |    N |         Mean |       Error |      StdDev |       Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-------------:|------------:|------------:|-------------:|-------:|------:|------:|----------:|
|    Common |   10 |    376.70 ns |   2.7991 ns |   2.6183 ns |    375.22 ns | 0.0405 |     - |     - |     192 B |
| Optimized |   10 |     80.54 ns |   0.4361 ns |   0.4079 ns |     80.45 ns | 0.0085 |     - |     - |      40 B |
|    **Common** |  **100** |  **2,706.45 ns** |  **13.9446 ns** |  **13.0438 ns** |  **2,702.38 ns** | **0.0381** |     **-** |     **-** |     **192 B** |
| **Optimized** |  **100** |    **655.96 ns** |   **1.9945 ns** |   **1.8657 ns** |    **656.02 ns** | **0.0076** |     **-** |     **-** |      **40 B** |
|    Common | 1000 | 27,589.38 ns | 130.5825 ns | 122.1470 ns | 27,588.12 ns | 0.0305 |     - |     - |     248 B |
| Optimized | 1000 |  7,157.98 ns |  86.1653 ns |  80.5991 ns |  7,170.12 ns | 0.0153 |     - |     - |      96 B |

## Core
|    Method |    N |         Mean |       Error |      StdDev |       Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-------------:|------------:|------------:|-------------:|-------:|------:|------:|----------:|
|    Common |   10 |    429.82 ns |   5.2909 ns |   4.9491 ns |    428.91 ns | 0.0405 |     - |     - |     192 B |
| Optimized |   10 |     83.47 ns |   0.5861 ns |   0.5195 ns |     83.54 ns | 0.0085 |     - |     - |      40 B |
|    **Common** |  **100** |  **2,599.45 ns** |  **15.5876 ns** |  **13.8180 ns** |  **2,598.13 ns** | **0.0381** |     **-** |     **-** |     **192 B** |
| **Optimized** |  **100** |    **614.52 ns** |   **3.6789 ns** |   **3.4412 ns** |    **614.03 ns** | **0.0076** |     **-** |     **-** |      **40 B** |
|    Common | 1000 | 27,016.84 ns | 148.6900 ns | 139.0847 ns | 27,036.66 ns | 0.0305 |     - |     - |     248 B |
| Optimized | 1000 |  8,514.49 ns |  71.7489 ns |  67.1140 ns |  8,488.12 ns | 0.0153 |     - |     - |      96 B |