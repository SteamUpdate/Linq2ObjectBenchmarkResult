``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |        Mean |      Error |     StdDev |      Median |         Min |         Max | Rank |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|-----------:|------------:|------------:|------------:|-----:|-------:|------:|------:|----------:|
|      **List** |   **10** |    **383.1 ns** |  **0.2643 ns** |  **0.2472 ns** |    **383.1 ns** |    **382.8 ns** |    **383.7 ns** |    **2** |      **-** |     **-** |     **-** |         **-** |
| HashedSet |   10 |    428.9 ns |  0.3743 ns |  0.3501 ns |    428.9 ns |    428.4 ns |    429.6 ns |    3 | 0.0081 |     - |     - |      40 B |
|     Array |   10 |    312.0 ns |  0.3301 ns |  0.3088 ns |    311.9 ns |    311.4 ns |    312.6 ns |    1 |      - |     - |     - |         - |
|      **List** |  **100** |  **3,414.8 ns** |  **2.9616 ns** |  **2.6254 ns** |  **3,415.5 ns** |  **3,409.7 ns** |  **3,418.6 ns** |    **5** |      **-** |     **-** |     **-** |         **-** |
| HashedSet |  100 |  3,783.4 ns |  6.2697 ns |  5.5579 ns |  3,784.2 ns |  3,774.6 ns |  3,791.5 ns |    6 | 0.0076 |     - |     - |      40 B |
|     Array |  100 |  2,800.5 ns |  3.6069 ns |  3.1974 ns |  2,799.9 ns |  2,794.8 ns |  2,806.0 ns |    4 |      - |     - |     - |         - |
|      **List** | **1000** | **34,008.2 ns** | **41.1450 ns** | **38.4870 ns** | **34,009.0 ns** | **33,925.1 ns** | **34,072.2 ns** |    **8** |      **-** |     **-** |     **-** |         **-** |
| HashedSet | 1000 | 37,373.1 ns | 84.9419 ns | 79.4547 ns | 37,345.6 ns | 37,273.6 ns | 37,539.2 ns |    9 |      - |     - |     - |      40 B |
|     Array | 1000 | 28,634.7 ns | 20.0475 ns | 18.7525 ns | 28,633.2 ns | 28,603.6 ns | 28,664.2 ns |    7 |      - |     - |     - |         - |