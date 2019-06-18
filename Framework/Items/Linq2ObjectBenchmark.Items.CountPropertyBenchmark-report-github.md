``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |      Mean |     Error |    StdDev |    Median |       Min |       Max | Rank | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |----------:|----------:|----------:|----------:|----------:|----------:|-----:|------------:|------------:|------------:|--------------------:|
|      **List** |   **10** | **0.0266 ns** | **0.0016 ns** | **0.0015 ns** | **0.0264 ns** | **0.0244 ns** | **0.0301 ns** |    **2** |           **-** |           **-** |           **-** |                   **-** |
| HashedSet |   10 | 0.4729 ns | 0.0022 ns | 0.0021 ns | 0.4723 ns | 0.4698 ns | 0.4770 ns |    4 |           - |           - |           - |                   - |
|     Array |   10 | 0.0000 ns | 0.0000 ns | 0.0000 ns | 0.0000 ns | 0.0000 ns | 0.0000 ns |    1 |           - |           - |           - |                   - |
|      **List** |  **100** | **0.0265 ns** | **0.0010 ns** | **0.0009 ns** | **0.0264 ns** | **0.0251 ns** | **0.0279 ns** |    **2** |           **-** |           **-** |           **-** |                   **-** |
| HashedSet |  100 | 0.4744 ns | 0.0012 ns | 0.0011 ns | 0.4745 ns | 0.4719 ns | 0.4761 ns |    4 |           - |           - |           - |                   - |
|     Array |  100 | 0.0483 ns | 0.0015 ns | 0.0013 ns | 0.0483 ns | 0.0459 ns | 0.0506 ns |    3 |           - |           - |           - |                   - |
|      **List** | **1000** | **0.0271 ns** | **0.0011 ns** | **0.0010 ns** | **0.0272 ns** | **0.0251 ns** | **0.0285 ns** |    **2** |           **-** |           **-** |           **-** |                   **-** |
| HashedSet | 1000 | 0.4739 ns | 0.0032 ns | 0.0028 ns | 0.4726 ns | 0.4713 ns | 0.4796 ns |    4 |           - |           - |           - |                   - |
|     Array | 1000 | 0.0478 ns | 0.0015 ns | 0.0014 ns | 0.0477 ns | 0.0462 ns | 0.0501 ns |    3 |           - |           - |           - |                   - |
