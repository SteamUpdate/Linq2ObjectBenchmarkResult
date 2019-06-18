``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |       Mean |     Error |    StdDev |     Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |-----------:|----------:|----------:|-----------:|------------:|------------:|------------:|--------------------:|
|    **Common** |   **10** |   **5.141 ns** | **0.1240 ns** | **0.1327 ns** |   **5.070 ns** |           **-** |           **-** |           **-** |                   **-** |
| Optimized |   10 |   2.813 ns | 0.0086 ns | 0.0081 ns |   2.811 ns |           - |           - |           - |                   - |
|    **Common** |  **100** |  **54.903 ns** | **0.2069 ns** | **0.1936 ns** |  **54.841 ns** |           **-** |           **-** |           **-** |                   **-** |
| Optimized |  100 |  43.133 ns | 0.1460 ns | 0.1366 ns |  43.117 ns |           - |           - |           - |                   - |
|    **Common** | **1000** | **510.335 ns** | **0.9485 ns** | **0.8408 ns** | **510.528 ns** |           **-** |           **-** |           **-** |                   **-** |
| Optimized | 1000 | 274.140 ns | 0.7548 ns | 0.6691 ns | 274.064 ns |           - |           - |           - |                   - |
