# `ELMA8120`

## Code 
```csharp
public IEntity Common()
{
    if (collection.Any())
    {
        var first = collection.First();
        return first;
    }

    return null;
}

public IEntity Optimized()
{
    var first = collection.FirstOrDefault();
    if (first != null)
    {
        return first;
    }

    return null;
}
```

## Framework
|    Method |    N |     Mean |     Error |    StdDev |   Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |---------:|----------:|----------:|---------:|-------:|------:|------:|----------:|
|    Common |   10 | 34.32 ns | 0.1000 ns | 0.0887 ns | 34.32 ns | 0.0085 |     - |     - |      40 B |
| Optimized |   10 | 13.58 ns | 0.0090 ns | 0.0070 ns | 13.59 ns |      - |     - |     - |         - |
|    **Common** |  **100** | **34.21 ns** | **0.0382 ns** | **0.0319 ns** | **34.20 ns** | **0.0085** |     **-** |     **-** |      **40 B** |
| **Optimized** |  **100** | **13.59 ns** | **0.0096 ns** | **0.0085 ns** | **13.59 ns** |      **-** |     **-** |     **-** |         **-** |
|    Common | 1000 | 33.19 ns | 0.1031 ns | 0.0964 ns | 33.21 ns | 0.0085 |     - |     - |      40 B |
| Optimized | 1000 | 13.89 ns | 0.0105 ns | 0.0088 ns | 13.89 ns |      - |     - |     - |         - |

## Core
|    Method |    N |     Mean |     Error |    StdDev |   Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |---------:|----------:|----------:|---------:|-------:|------:|------:|----------:|
|    Common |   10 | 51.42 ns | 0.3819 ns | 0.3572 ns | 51.46 ns | 0.0085 |     - |     - |      40 B |
| Optimized |   10 | 30.03 ns | 0.2325 ns | 0.2175 ns | 29.93 ns |      - |     - |     - |         - |
|    **Common** |  **100** | **51.48 ns** | **0.3346 ns** | **0.3130 ns** | **51.44 ns** | **0.0085** |     **-** |     **-** |      **40 B** |
| **Optimized** |  **100** | **30.10 ns** | **0.1700 ns** | **0.1590 ns** | **30.09 ns** |      **-** |     **-** |     **-** |         **-** |
|    Common | 1000 | 51.29 ns | 0.3036 ns | 0.2692 ns | 51.25 ns | 0.0085 |     - |     - |      40 B |
| Optimized | 1000 | 28.88 ns | 0.1643 ns | 0.1536 ns | 28.86 ns |      - |     - |     - |         - |