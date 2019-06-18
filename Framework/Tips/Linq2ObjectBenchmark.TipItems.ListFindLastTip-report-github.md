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
|    **Common** |   **10** |   **124.14 ns** |  **0.1219 ns** |  **0.1081 ns** |   **124.11 ns** |      **0.0083** |           **-** |           **-** |                **40 B** |
| Optimized |   10 |    18.94 ns |  0.0160 ns |  0.0150 ns |    18.94 ns |           - |           - |           - |                   - |
|    **Common** |  **100** | **1,008.22 ns** |  **0.5801 ns** |  **0.5143 ns** | **1,008.15 ns** |      **0.0076** |           **-** |           **-** |                **40 B** |
| Optimized |  100 |   181.78 ns |  0.1500 ns |  0.1403 ns |   181.78 ns |           - |           - |           - |                   - |
|    **Common** | **1000** | **9,870.95 ns** | **18.2820 ns** | **17.1010 ns** | **9,865.97 ns** |           **-** |           **-** |           **-** |                **40 B** |
| Optimized | 1000 | 1,774.50 ns |  1.4003 ns |  1.3098 ns | 1,774.31 ns |           - |           - |           - |                   - |
