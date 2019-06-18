``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |        Mean |       Error |      StdDev |      Median |         Min |         Max | Rank |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|------------:|------------:|------------:|------------:|------------:|-----:|-------:|------:|------:|----------:|
|      **List** |   **10** |    **607.8 ns** |   **0.8212 ns** |   **0.7280 ns** |    **607.7 ns** |    **606.8 ns** |    **609.4 ns** |    **2** |      **-** |     **-** |     **-** |         **-** |
| HashedSet |   10 |    651.6 ns |   1.3409 ns |   1.2543 ns |    651.4 ns |    649.5 ns |    653.7 ns |    3 | 0.0076 |     - |     - |      40 B |
|     Array |   10 |    570.7 ns |   0.5120 ns |   0.4539 ns |    570.7 ns |    570.0 ns |    571.4 ns |    1 |      - |     - |     - |         - |
|      **List** |  **100** |  **5,905.0 ns** |   **4.9314 ns** |   **4.6129 ns** |  **5,905.7 ns** |  **5,896.0 ns** |  **5,913.1 ns** |    **5** |      **-** |     **-** |     **-** |         **-** |
| HashedSet |  100 |  6,329.5 ns |   4.3334 ns |   4.0535 ns |  6,330.1 ns |  6,321.6 ns |  6,334.9 ns |    6 | 0.0076 |     - |     - |      40 B |
|     Array |  100 |  5,521.0 ns |   2.7814 ns |   2.1715 ns |  5,521.2 ns |  5,517.3 ns |  5,525.5 ns |    4 |      - |     - |     - |         - |
|      **List** | **1000** | **60,108.8 ns** | **126.2675 ns** | **118.1107 ns** | **60,083.0 ns** | **59,962.4 ns** | **60,361.0 ns** |    **8** |      **-** |     **-** |     **-** |         **-** |
| HashedSet | 1000 | 62,985.6 ns |  84.8215 ns |  79.3421 ns | 62,988.5 ns | 62,854.5 ns | 63,102.8 ns |    9 |      - |     - |     - |      40 B |
|     Array | 1000 | 55,436.5 ns |  46.7693 ns |  41.4598 ns | 55,434.4 ns | 55,368.6 ns | 55,499.7 ns |    7 |      - |     - |     - |         - |
