# `Empty Collection`

## Code
```csharp
public IEnumerable<Entity> CreateEmptyList()
{
    return new List<Entity>();
}

public IEnumerable<Entity> CreateEmptyArray()
{
    return new Entity[0];
}

public IEnumerable<Entity> CreateEmptyEnumerable()
{
    return Enumerable.Empty<Entity>();
}
```

## Framework
| Method |     Mean |     Error |    StdDev |   Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|------- |---------:|----------:|----------:|---------:|-------:|------:|------:|----------:|
|   List | 6.638 ns | 0.0179 ns | 0.0167 ns | 6.637 ns | 0.0085 |     - |     - |      40 B |
|  Array | 2.455 ns | 0.0223 ns | 0.0209 ns | 2.458 ns | 0.0051 |     - |     - |      24 B |
|   Linq | 2.357 ns | 0.0005 ns | 0.0005 ns | 2.357 ns |      - |     - |     - |         - |

## Core
| Method |     Mean |     Error |    StdDev |   Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|------- |---------:|----------:|----------:|---------:|-------:|------:|------:|----------:|
|   List | 6.508 ns | 0.0245 ns | 0.0229 ns | 6.508 ns | 0.0085 |     - |     - |      40 B |
|  Array | 2.230 ns | 0.0063 ns | 0.0055 ns | 2.229 ns | 0.0051 |     - |     - |      24 B |
|   Linq | 2.053 ns | 0.0034 ns | 0.0031 ns | 2.053 ns |      - |     - |     - |         - |
