``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |        Mean |      Error |     StdDev |      Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |------------:|-----------:|-----------:|------------:|------------:|------------:|------------:|--------------------:|
|    **Common** |   **10** |    **90.48 ns** |  **0.2345 ns** |  **0.1958 ns** |    **90.37 ns** |      **0.0067** |           **-** |           **-** |                **32 B** |
| Optimized |   10 |    21.17 ns |  0.0789 ns |  0.0738 ns |    21.14 ns |           - |           - |           - |                   - |
|    **Common** |  **100** |   **681.79 ns** |  **0.7081 ns** |  **0.6623 ns** |   **681.77 ns** |      **0.0067** |           **-** |           **-** |                **32 B** |
| Optimized |  100 |   208.51 ns |  0.1750 ns |  0.1637 ns |   208.56 ns |           - |           - |           - |                   - |
|    **Common** | **1000** | **6,639.71 ns** | **24.2154 ns** | **22.6511 ns** | **6,639.44 ns** |           **-** |           **-** |           **-** |                **32 B** |
| Optimized | 1000 | 1,112.27 ns |  0.9197 ns |  0.8603 ns | 1,112.32 ns |           - |           - |           - |                   - |
