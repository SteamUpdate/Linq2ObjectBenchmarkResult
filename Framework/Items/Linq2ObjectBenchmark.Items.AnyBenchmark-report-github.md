``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |     Mean |     Error |    StdDev |   Median |      Min |      Max | Rank | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |---------:|----------:|----------:|---------:|---------:|---------:|-----:|------------:|------------:|------------:|--------------------:|
|      **List** |   **10** | **16.47 ns** | **0.0193 ns** | **0.0180 ns** | **16.47 ns** | **16.44 ns** | **16.51 ns** |    **2** |      **0.0085** |           **-** |           **-** |                **40 B** |
| HashedSet |   10 | 18.36 ns | 0.0485 ns | 0.0454 ns | 18.36 ns | 18.30 ns | 18.45 ns |    3 |      0.0085 |           - |           - |                40 B |
|     Array |   10 | 13.08 ns | 0.0241 ns | 0.0226 ns | 13.08 ns | 13.04 ns | 13.12 ns |    1 |      0.0068 |           - |           - |                32 B |
|      **List** |  **100** | **16.41 ns** | **0.0144 ns** | **0.0127 ns** | **16.41 ns** | **16.39 ns** | **16.43 ns** |    **2** |      **0.0085** |           **-** |           **-** |                **40 B** |
| HashedSet |  100 | 18.28 ns | 0.0251 ns | 0.0209 ns | 18.28 ns | 18.23 ns | 18.30 ns |    3 |      0.0085 |           - |           - |                40 B |
|     Array |  100 | 13.07 ns | 0.0213 ns | 0.0189 ns | 13.07 ns | 13.04 ns | 13.10 ns |    1 |      0.0068 |           - |           - |                32 B |
|      **List** | **1000** | **16.44 ns** | **0.0310 ns** | **0.0290 ns** | **16.43 ns** | **16.39 ns** | **16.50 ns** |    **2** |      **0.0085** |           **-** |           **-** |                **40 B** |
| HashedSet | 1000 | 18.16 ns | 0.0349 ns | 0.0310 ns | 18.17 ns | 18.11 ns | 18.23 ns |    3 |      0.0085 |           - |           - |                40 B |
|     Array | 1000 | 13.11 ns | 0.0464 ns | 0.0434 ns | 13.13 ns | 13.00 ns | 13.19 ns |    1 |      0.0068 |           - |           - |                32 B |
