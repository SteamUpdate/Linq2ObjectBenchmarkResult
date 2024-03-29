# `FirstOrDefault(q => q...)` [Optimized]

## Code
```csharp
public bool TestSet()
{
    Entity entity = null;
    foreach (var item in set)
    {
        if (item.GetType() == typeof(Entity))
        {
            entity = item;
            break;
        }
    }
    return entity != null;
}
```

## Framework
|    Method |    N |       Mean |     Error |    StdDev |     Median |        Min |        Max |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-----------:|----------:|----------:|-----------:|-----------:|-----------:|-------:|------:|------:|----------:|
|      List |   10 | 10.8562 ns | 0.0145 ns | 0.0128 ns | 10.8585 ns | 10.8333 ns | 10.8793 ns |      - |     - |     - |         - |
| HashedSet |   10 | 20.5126 ns | 0.3675 ns | 0.3437 ns | 20.3763 ns | 20.0386 ns | 21.0638 ns | 0.0085 |     - |     - |      40 B |
|     Array |   10 |  0.4059 ns | 0.0156 ns | 0.0146 ns |  0.3984 ns |  0.3921 ns |  0.4405 ns |      - |     - |     - |         - |
|      **List** |  **100** | **11.0362 ns** | **0.0724 ns** | **0.0642 ns** | **11.0434 ns** | **10.9205 ns** | **11.1251 ns** |      **-** |     **-** |     **-** |         **-** |
| **HashedSet** |  **100** | **20.5656 ns** | **0.1988 ns** | **0.1860 ns** | **20.5477 ns** | **20.2920 ns** | **20.9328 ns** | **0.0085** |     **-** |     **-** |      **40 B** |
|     **Array** |  **100** |  **0.3772 ns** | **0.0056 ns** | **0.0052 ns** |  **0.3764 ns** |  **0.3681 ns** |  **0.3875 ns** |      **-** |     **-** |     **-** |         **-** |
|      List | 1000 | 10.9027 ns | 0.0985 ns | 0.0922 ns | 10.8702 ns | 10.8004 ns | 11.0841 ns |      - |     - |     - |         - |
| HashedSet | 1000 | 20.5496 ns | 0.4214 ns | 0.4139 ns | 20.4710 ns | 20.1086 ns | 21.3182 ns | 0.0085 |     - |     - |      40 B |
|     Array | 1000 |  0.3975 ns | 0.0150 ns | 0.0141 ns |  0.3977 ns |  0.3774 ns |  0.4216 ns |      - |     - |     - |         - |

## Core
|    Method |    N |       Mean |     Error |    StdDev |     Median |        Min |        Max |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-----------:|----------:|----------:|-----------:|-----------:|-----------:|-------:|------:|------:|----------:|
|      List |   10 | 10.7888 ns | 0.0273 ns | 0.0242 ns | 10.7902 ns | 10.7521 ns | 10.8298 ns |      - |     - |     - |         - |
| HashedSet |   10 | 17.7502 ns | 0.0173 ns | 0.0153 ns | 17.7506 ns | 17.7189 ns | 17.7763 ns | 0.0085 |     - |     - |      40 B |
|     Array |   10 |  0.4612 ns | 0.0021 ns | 0.0019 ns |  0.4608 ns |  0.4585 ns |  0.4644 ns |      - |     - |     - |         - |
|      **List** |  **100** | **10.7810 ns** | **0.0136 ns** | **0.0128 ns** | **10.7792 ns** | **10.7531 ns** | **10.8011 ns** |      **-** |     **-** |     **-** |         *-* |
| **HashedSet** |  **100** | **18.3316 ns** | **0.3287 ns** | **0.3075 ns** | **18.3851 ns** | **17.8429 ns** | **18.7641 ns** | **0.0085** |     **-** |     **-** |      **40 B** |
|     **Array** |  **100** |  **0.4628 ns** | **0.0023 ns** | **0.0019 ns** |  **0.4621 ns** |  **0.4608 ns** |  **0.4679 ns** |      **-** |     **-** |     **-** |         **-** |
|      List | 1000 | 10.7801 ns | 0.0105 ns | 0.0099 ns | 10.7811 ns | 10.7531 ns | 10.7916 ns |      - |     - |     - |         - |
| HashedSet | 1000 | 17.8532 ns | 0.0620 ns | 0.0580 ns | 17.8487 ns | 17.7401 ns | 17.9445 ns | 0.0085 |     - |     - |      40 B |
|     Array | 1000 |  0.4625 ns | 0.0024 ns | 0.0020 ns |  0.4619 ns |  0.4599 ns |  0.4672 ns |      - |     - |     - |         - |
