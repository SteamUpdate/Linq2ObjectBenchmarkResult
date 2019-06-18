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
|      **List** |   **10** | **23.63 ns** | **0.0175 ns** | **0.0155 ns** | **23.63 ns** | **23.60 ns** | **23.66 ns** |    **2** |      **0.0085** |           **-** |           **-** |                **40 B** |
| HashedSet |   10 | 26.02 ns | 0.0230 ns | 0.0215 ns | 26.02 ns | 25.98 ns | 26.05 ns |    3 |      0.0085 |           - |           - |                40 B |
|     Array |   10 | 20.82 ns | 0.3563 ns | 0.3333 ns | 20.63 ns | 20.60 ns | 21.53 ns |    1 |      0.0068 |           - |           - |                32 B |
|      **List** |  **100** | **23.63 ns** | **0.0194 ns** | **0.0172 ns** | **23.62 ns** | **23.61 ns** | **23.67 ns** |    **2** |      **0.0085** |           **-** |           **-** |                **40 B** |
| HashedSet |  100 | 25.93 ns | 0.0247 ns | 0.0219 ns | 25.93 ns | 25.90 ns | 25.97 ns |    3 |      0.0085 |           - |           - |                40 B |
|     Array |  100 | 20.70 ns | 0.0309 ns | 0.0289 ns | 20.70 ns | 20.65 ns | 20.75 ns |    1 |      0.0068 |           - |           - |                32 B |
|      **List** | **1000** | **23.68 ns** | **0.0432 ns** | **0.0383 ns** | **23.67 ns** | **23.64 ns** | **23.79 ns** |    **2** |      **0.0085** |           **-** |           **-** |                **40 B** |
| HashedSet | 1000 | 25.92 ns | 0.0288 ns | 0.0255 ns | 25.91 ns | 25.89 ns | 25.96 ns |    3 |      0.0085 |           - |           - |                40 B |
|     Array | 1000 | 20.70 ns | 0.0257 ns | 0.0228 ns | 20.69 ns | 20.67 ns | 20.75 ns |    1 |      0.0068 |           - |           - |                32 B |
