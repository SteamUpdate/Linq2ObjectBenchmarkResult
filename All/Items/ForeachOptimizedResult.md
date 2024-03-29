# `foreach` [Optimized]

## Code
```csharp
var typeName = typeof(Entity).FullName;
foreach (var item in set)
{
    if (item.GetType().FullName == typeName)
    {

    }
}
```

## Framework
|    Method |    N |        Mean |      Error |     StdDev |      Median |         Min |         Max |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|-----------:|------------:|------------:|------------:|-------:|------:|------:|----------:|
|      List |   10 |    425.7 ns |   3.193 ns |   2.986 ns |    425.3 ns |    420.8 ns |    431.0 ns |      - |     - |     - |         - |
| HashedSet |   10 |    463.2 ns |   2.193 ns |   2.051 ns |    463.5 ns |    459.0 ns |    465.9 ns | 0.0081 |     - |     - |      40 B |
|     Array |   10 |    366.0 ns |   1.891 ns |   1.769 ns |    365.7 ns |    362.7 ns |    369.5 ns |      - |     - |     - |         - |
|      **List** |  **100** |  **3,825.7 ns** |  **17.721 ns** |  **16.576 ns** |  **3,830.3 ns** |  **3,783.1 ns** |  **3,848.6 ns** |      **-** |     **-** |     **-** |         **-** |
| **HashedSet** |  **100** |  **4,080.9 ns** |  **33.379 ns** |  **31.223 ns** |  **4,069.1 ns** |  **4,038.5 ns** |  **4,136.8 ns** | **0.0076** |     **-** |     **-** |      **40 B** |
|     **Array** |  **100** |  **3,337.4 ns** |  **24.577 ns** |  **22.989 ns** |  **3,340.0 ns** |  **3,298.7 ns** |  **3,376.8 ns** |      **-** |     **-** |     **-** |         **-** |
|      List | 1000 | 37,031.0 ns | 364.194 ns | 340.668 ns | 36,941.7 ns | 36,665.9 ns | 37,690.8 ns |      - |     - |     - |         - |
| HashedSet | 1000 | 40,600.9 ns | 424.890 ns | 397.443 ns | 40,634.7 ns | 40,052.9 ns | 41,199.9 ns |      - |     - |     - |      40 B |
|     Array | 1000 | 32,738.3 ns | 346.679 ns | 324.284 ns | 32,590.1 ns | 32,403.8 ns | 33,265.3 ns |      - |     - |     - |         - |

## Core

|    Method |    N |        Mean |      Error |     StdDev |      Median |         Min |         Max |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|-----------:|------------:|------------:|------------:|-------:|------:|------:|----------:|
|      List |   10 |    383.1 ns |  0.2643 ns |  0.2472 ns |    383.1 ns |    382.8 ns |    383.7 ns |      - |     - |     - |         - |
| HashedSet |   10 |    428.9 ns |  0.3743 ns |  0.3501 ns |    428.9 ns |    428.4 ns |    429.6 ns | 0.0081 |     - |     - |      40 B |
|     Array |   10 |    312.0 ns |  0.3301 ns |  0.3088 ns |    311.9 ns |    311.4 ns |    312.6 ns |      - |     - |     - |         - |
|      **List** |  **100** |  **3,414.8 ns** |  **2.9616 ns** |  **2.6254 ns** |  **3,415.5 ns** |  **3,409.7 ns** |  **3,418.6 ns** |      **-** |     **-** |     **-** |         **-** |
| **HashedSet** |  **100** |  **3,783.4 ns** |  **6.2697 ns** |  **5.5579 ns** |  **3,784.2 ns** |  **3,774.6 ns** |  **3,791.5 ns** | **0.0076** |     **-** |     **-** |      **40 B** |
|     **Array** |  **100** |  **2,800.5 ns** |  **3.6069 ns** |  **3.1974 ns** |  **2,799.9 ns** |  **2,794.8 ns** |  **2,806.0 ns** |      **-** |     **-** |     **-** |         **-** |
|      List | 1000 | 34,008.2 ns | 41.1450 ns | 38.4870 ns | 34,009.0 ns | 33,925.1 ns | 34,072.2 ns |      - |     - |     - |         - |
| HashedSet | 1000 | 37,373.1 ns | 84.9419 ns | 79.4547 ns | 37,345.6 ns | 37,273.6 ns | 37,539.2 ns |      - |     - |     - |      40 B |
|     Array | 1000 | 28,634.7 ns | 20.0475 ns | 18.7525 ns | 28,633.2 ns | 28,603.6 ns | 28,664.2 ns |      - |     - |     - |         - |
