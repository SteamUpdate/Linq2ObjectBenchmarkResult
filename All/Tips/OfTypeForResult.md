# `OfType<T>().Where()` => `for`

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
    for (var i = 0; i < list.Count; i++)
    {
        if (list[i] is Entity entity && entity.SomeStr == "456")
        {
            result.Add(entity);
        }
    }
    return result;
}
```

## Framework
|    Method |    N |         Mean |      Error |     StdDev |       Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-------------:|-----------:|-----------:|-------------:|-------:|------:|------:|----------:|
|    Common |   10 |    383.98 ns |  0.1034 ns |  0.0967 ns |    383.99 ns | 0.0405 |     - |     - |     192 B |
| Optimized |   10 |     56.44 ns |  0.0489 ns |  0.0458 ns |     56.45 ns | 0.0085 |     - |     - |      40 B |
|    **Common** |  **100** |  **2,750.19 ns** |  **4.8462 ns** |  **4.5331 ns** |  **2,749.79 ns** | **0.0381** |     **-** |     **-** |     **192 B** |
| **Optimized** |  **100** |    **378.41 ns** |  **0.3634 ns** |  **0.3399 ns** |    **378.40 ns** | **0.0081** |     **-** |     **-** |      **40 B** |
|    Common | 1000 | 28,102.01 ns | 28.0920 ns | 26.2772 ns | 28,106.91 ns | 0.0305 |     - |     - |     248 B |
| Optimized | 1000 |  5,455.08 ns | 21.0360 ns | 19.6771 ns |  5,463.29 ns | 0.0153 |     - |     - |      96 B |

## Core
|    Method |    N |         Mean |      Error |     StdDev |       Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-------------:|-----------:|-----------:|-------------:|-------:|------:|------:|----------:|
|    Common |   10 |    434.02 ns |  0.8373 ns |  0.7833 ns |    433.95 ns | 0.0405 |     - |     - |     192 B |
| Optimized |   10 |     50.79 ns |  0.0862 ns |  0.0807 ns |     50.78 ns | 0.0085 |     - |     - |      40 B |
|    **Common** |  **100** |  **2,599.63 ns** |  **4.7691 ns** |  **4.2277 ns** |  **2,598.52 ns** | **0.0381** |     **-** |     **-** |     **192 B** |
| **Optimized** |  **100** |    **325.28 ns** |  **0.2726 ns** |  **0.2416 ns** |    **325.24 ns** | **0.0081** |     **-** |     **-** |      **40 B** |
|    Common | 1000 | 27,277.88 ns | 81.6082 ns | 76.3363 ns | 27,274.63 ns | 0.0305 |     - |     - |     248 B |
| Optimized | 1000 |  6,544.98 ns | 38.7707 ns | 36.2662 ns |  6,558.83 ns | 0.0153 |     - |     - |      96 B |
