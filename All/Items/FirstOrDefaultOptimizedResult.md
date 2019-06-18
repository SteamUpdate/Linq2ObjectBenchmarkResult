# `FirstOrDefault()` [Optimized]

## Code
```csharp
public bool TestSet()
{
    Entity entity = null;
    foreach (var item in set)
    {
        entity = item;
        break;
    }
    return entity != null;
}
```

## todo check framework with HashedSet

## Framework
|    Method |    N |       Mean |     Error |    StdDev |     Median |        Min |        Max | Rank | Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-----------:|----------:|----------:|-----------:|-----------:|-----------:|-----:|------------:|------------:|------------:|--------------------:|
|      List |   10 | 10.6053 ns | 0.0187 ns | 0.0166 ns | 10.5974 ns | 10.5903 ns | 10.6465 ns |    2 |           - |           - |           - |                   - |
| HashedSet |   10 | 11.4007 ns | 0.0194 ns | 0.0172 ns | 11.3956 ns | 11.3776 ns | 11.4347 ns |    3 |           - |           - |           - |                   - |
|     Array |   10 |  0.1697 ns | 0.0010 ns | 0.0009 ns |  0.1694 ns |  0.1684 ns |  0.1712 ns |    1 |           - |           - |           - |                   - |
|      List |  100 | 10.6012 ns | 0.0131 ns | 0.0116 ns | 10.5999 ns | 10.5830 ns | 10.6244 ns |    2 |           - |           - |           - |                   - |
| HashedSet |  100 | 11.3813 ns | 0.0281 ns | 0.0263 ns | 11.3678 ns | 11.3541 ns | 11.4269 ns |    3 |           - |           - |           - |                   - |
|     Array |  100 |  0.1673 ns | 0.0014 ns | 0.0013 ns |  0.1672 ns |  0.1645 ns |  0.1695 ns |    1 |           - |           - |           - |                   - |
|      List | 1000 | 10.6007 ns | 0.0104 ns | 0.0092 ns | 10.5968 ns | 10.5876 ns | 10.6212 ns |    2 |           - |           - |           - |                   - |
| HashedSet | 1000 | 11.8772 ns | 0.0520 ns | 0.0486 ns | 11.8806 ns | 11.8038 ns | 11.9480 ns |    4 |           - |           - |           - |                   - |
|     Array | 1000 |  0.1689 ns | 0.0007 ns | 0.0006 ns |  0.1690 ns |  0.1677 ns |  0.1698 ns |    1 |           - |           - |           - |                   - |


## Core
|    Method |    N |       Mean |     Error |    StdDev |     Median |        Min |        Max | Rank |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-----------:|----------:|----------:|-----------:|-----------:|-----------:|-----:|-------:|------:|------:|----------:|
|      List |   10 | 10.6033 ns | 0.0091 ns | 0.0085 ns | 10.6055 ns | 10.5873 ns | 10.6131 ns |    3 |      - |     - |     - |         - |
| HashedSet |   10 | 17.4554 ns | 0.0291 ns | 0.0258 ns | 17.4647 ns | 17.4050 ns | 17.4839 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array |   10 |  0.2024 ns | 0.0020 ns | 0.0018 ns |  0.2030 ns |  0.1997 ns |  0.2054 ns |    2 |      - |     - |     - |         - |
|      List |  100 | 10.6039 ns | 0.0089 ns | 0.0079 ns | 10.6024 ns | 10.5918 ns | 10.6213 ns |    3 |      - |     - |     - |         - |
| HashedSet |  100 | 17.4471 ns | 0.0274 ns | 0.0256 ns | 17.4489 ns | 17.4014 ns | 17.4802 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array |  100 |  0.1870 ns | 0.0008 ns | 0.0007 ns |  0.1871 ns |  0.1859 ns |  0.1885 ns |    1 |      - |     - |     - |         - |
|      List | 1000 | 10.6140 ns | 0.0118 ns | 0.0111 ns | 10.6140 ns | 10.5976 ns | 10.6376 ns |    3 |      - |     - |     - |         - |
| HashedSet | 1000 | 17.3667 ns | 0.0306 ns | 0.0286 ns | 17.3641 ns | 17.3071 ns | 17.4144 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array | 1000 |  0.2001 ns | 0.0017 ns | 0.0015 ns |  0.1997 ns |  0.1983 ns |  0.2039 ns |    2 |      - |     - |     - |         - |