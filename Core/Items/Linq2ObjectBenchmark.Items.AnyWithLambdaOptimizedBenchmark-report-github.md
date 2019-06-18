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
|      **List** |   **10** | **10.4945 ns** | **0.0247 ns** | **0.0231 ns** | **10.4960 ns** | **10.4417 ns** | **10.5300 ns** |    **4** |      **-** |     **-** |     **-** |         **-** |
| HashedSet |   10 | 18.5730 ns | 0.0931 ns | 0.0825 ns | 18.5794 ns | 18.3038 ns | 18.6469 ns |    6 | 0.0085 |     - |     - |      40 B |
|     Array |   10 |  0.3730 ns | 0.0022 ns | 0.0021 ns |  0.3725 ns |  0.3703 ns |  0.3767 ns |    1 |      - |     - |     - |         - |
|      **List** |  **100** | **10.2683 ns** | **0.0201 ns** | **0.0188 ns** | **10.2736 ns** | **10.2413 ns** | **10.3063 ns** |    **3** |      **-** |     **-** |     **-** |         **-** |
| HashedSet |  100 | 18.2827 ns | 0.0403 ns | 0.0377 ns | 18.2814 ns | 18.2225 ns | 18.3479 ns |    5 | 0.0085 |     - |     - |      40 B |
|     Array |  100 |  0.3959 ns | 0.0022 ns | 0.0021 ns |  0.3956 ns |  0.3928 ns |  0.4005 ns |    2 |      - |     - |     - |         - |
|      **List** | **1000** | **10.4583 ns** | **0.0088 ns** | **0.0078 ns** | **10.4598 ns** | **10.4454 ns** | **10.4707 ns** |    **4** |      **-** |     **-** |     **-** |         **-** |
| HashedSet | 1000 | 18.7201 ns | 0.0300 ns | 0.0266 ns | 18.7210 ns | 18.6736 ns | 18.7702 ns |    6 | 0.0085 |     - |     - |      40 B |
|     Array | 1000 |  0.3945 ns | 0.0024 ns | 0.0022 ns |  0.3943 ns |  0.3909 ns |  0.3993 ns |    2 |      - |     - |     - |         - |
