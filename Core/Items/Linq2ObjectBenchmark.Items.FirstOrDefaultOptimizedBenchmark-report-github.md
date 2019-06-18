``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |       Mean |     Error |    StdDev |     Median |        Min |        Max | Rank |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-----------:|----------:|----------:|-----------:|-----------:|-----------:|-----:|-------:|------:|------:|----------:|
|      **List** |   **10** | **10.6033 ns** | **0.0091 ns** | **0.0085 ns** | **10.6055 ns** | **10.5873 ns** | **10.6131 ns** |    **3** |      **-** |     **-** |     **-** |         **-** |
| HashedSet |   10 | 17.4554 ns | 0.0291 ns | 0.0258 ns | 17.4647 ns | 17.4050 ns | 17.4839 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array |   10 |  0.2024 ns | 0.0020 ns | 0.0018 ns |  0.2030 ns |  0.1997 ns |  0.2054 ns |    2 |      - |     - |     - |         - |
|      **List** |  **100** | **10.6039 ns** | **0.0089 ns** | **0.0079 ns** | **10.6024 ns** | **10.5918 ns** | **10.6213 ns** |    **3** |      **-** |     **-** |     **-** |         **-** |
| HashedSet |  100 | 17.4471 ns | 0.0274 ns | 0.0256 ns | 17.4489 ns | 17.4014 ns | 17.4802 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array |  100 |  0.1870 ns | 0.0008 ns | 0.0007 ns |  0.1871 ns |  0.1859 ns |  0.1885 ns |    1 |      - |     - |     - |         - |
|      **List** | **1000** | **10.6140 ns** | **0.0118 ns** | **0.0111 ns** | **10.6140 ns** | **10.5976 ns** | **10.6376 ns** |    **3** |      **-** |     **-** |     **-** |         **-** |
| HashedSet | 1000 | 17.3667 ns | 0.0306 ns | 0.0286 ns | 17.3641 ns | 17.3071 ns | 17.4144 ns |    4 | 0.0085 |     - |     - |      40 B |
|     Array | 1000 |  0.2001 ns | 0.0017 ns | 0.0015 ns |  0.1997 ns |  0.1983 ns |  0.2039 ns |    2 |      - |     - |     - |         - |
