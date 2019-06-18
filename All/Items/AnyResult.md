# `Any()`

## Code
```csharp
public bool TestSet()
{
    return set.Any();
}
```

## Framework
|    Method |    N |     Mean |     Error |    StdDev |   Median |      Min |      Max | Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |---------:|----------:|----------:|---------:|---------:|---------:|------------:|------------:|------------:|--------------------:|
|      List |   10 | 16.47 ns | 0.0193 ns | 0.0180 ns | 16.47 ns | 16.44 ns | 16.51 ns |      0.0085 |           - |           - |                40 B |
| HashedSet |   10 | 18.36 ns | 0.0485 ns | 0.0454 ns | 18.36 ns | 18.30 ns | 18.45 ns |      0.0085 |           - |           - |                40 B |
|     Array |   10 | 13.08 ns | 0.0241 ns | 0.0226 ns | 13.08 ns | 13.04 ns | 13.12 ns |      0.0068 |           - |           - |                32 B |
|      **List** |  **100** | **16.41 ns** | **0.0144 ns** | **0.0127 ns** | **16.41 ns** | **16.39 ns** | **16.43 ns** |      **0.0085** |           **-** |           **-** |                **40 B** |
| **HashedSet** |  **100** | **18.28 ns** | **0.0251 ns** | **0.0209 ns** | **18.28 ns** | **18.23 ns** | **18.30 ns** |      **0.0085** |           **-** |           **-** |                **40 B** |
|     **Array** |  **100** | **13.07 ns** | **0.0213 ns** | **0.0189 ns** | **13.07 ns** | **13.04 ns** | **13.10 ns** |      **0.0068** |           **-** |           **-** |                **32 B** |
|      List | 1000 | 16.44 ns | 0.0310 ns | 0.0290 ns | 16.43 ns | 16.39 ns | 16.50 ns |      0.0085 |           - |           - |                40 B |
| HashedSet | 1000 | 18.16 ns | 0.0349 ns | 0.0310 ns | 18.17 ns | 18.11 ns | 18.23 ns |      0.0085 |           - |           - |                40 B |
|     Array | 1000 | 13.11 ns | 0.0464 ns | 0.0434 ns | 13.13 ns | 13.00 ns | 13.19 ns |      0.0068 |           - |           - |                32 B |

## Core
|    Method |    N |     Mean |     Error |    StdDev |   Median |      Min |      Max |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |---------:|----------:|----------:|---------:|---------:|---------:|-------:|------:|------:|----------:|
|      List |   10 | 16.92 ns | 0.0310 ns | 0.0290 ns | 16.92 ns | 16.85 ns | 16.96 ns | 0.0085 |     - |     - |      40 B |
| HashedSet |   10 | 18.44 ns | 0.0289 ns | 0.0270 ns | 18.44 ns | 18.42 ns | 18.51 ns | 0.0085 |     - |     - |      40 B |
|     Array |   10 | 13.37 ns | 0.0275 ns | 0.0244 ns | 13.36 ns | 13.33 ns | 13.42 ns | 0.0068 |     - |     - |      32 B |
|      **List** |  **100** | **17.02 ns** | **0.0188 ns** | **0.0175 ns** | **17.02 ns** | **16.99 ns** | **17.06 ns** | **0.0085** |     **-** |     **-** |      **40 B** |
| **HashedSet** |  **100** | **18.42 ns** | **0.0279 ns** | **0.0261 ns** | **18.41 ns** | **18.37 ns** | **18.46 ns** | **0.0085** |     **-** |     **-** |      **40 B** |
|     **Array** |  **100** | **13.15 ns** | **0.0391 ns** | **0.0366 ns** | **13.15 ns** | **13.09 ns** | **13.22 ns** | **0.0068** |     **-** |     **-** |      **32 B** |
|      List | 1000 | 16.90 ns | 0.0233 ns | 0.0218 ns | 16.90 ns | 16.85 ns | 16.94 ns | 0.0085 |     - |     - |      40 B |
| HashedSet | 1000 | 18.17 ns | 0.0503 ns | 0.0471 ns | 18.16 ns | 18.11 ns | 18.27 ns | 0.0085 |     - |     - |      40 B |
|     Array | 1000 | 13.23 ns | 0.0205 ns | 0.0192 ns | 13.23 ns | 13.20 ns | 13.27 ns | 0.0068 |     - |     - |      32 B |