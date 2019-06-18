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
|    **Common** |   **10** |    **96.60 ns** |  **0.0751 ns** |  **0.0702 ns** |    **96.57 ns** |      **0.0067** |           **-** |           **-** |                **32 B** |
| Optimized |   10 |    19.22 ns |  0.1435 ns |  0.1342 ns |    19.14 ns |           - |           - |           - |                   - |
|    **Common** |  **100** |   **705.61 ns** |  **0.8259 ns** |  **0.6897 ns** |   **705.64 ns** |      **0.0067** |           **-** |           **-** |                **32 B** |
| Optimized |  100 |   186.65 ns |  1.1481 ns |  1.0739 ns |   186.32 ns |           - |           - |           - |                   - |
|    **Common** | **1000** | **3,128.96 ns** | **14.2271 ns** | **13.3081 ns** | **3,123.23 ns** |      **0.0038** |           **-** |           **-** |                **32 B** |
| Optimized | 1000 |   820.45 ns |  1.8724 ns |  1.4618 ns |   820.53 ns |           - |           - |           - |                   - |
