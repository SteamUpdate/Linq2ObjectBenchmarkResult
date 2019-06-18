``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |        Mean |       Error |      StdDev |      Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |------------:|------------:|------------:|------------:|------------:|------------:|------------:|--------------------:|
|    **Common** |   **10** |    **654.5 ns** |   **0.5284 ns** |   **0.4684 ns** |    **654.5 ns** |           **-** |           **-** |           **-** |                   **-** |
| Optimized |   10 |    424.1 ns |   2.7589 ns |   2.5807 ns |    423.5 ns |           - |           - |           - |                   - |
|    **Common** |  **100** |  **6,296.3 ns** |   **7.6044 ns** |   **7.1132 ns** |  **6,296.2 ns** |           **-** |           **-** |           **-** |                   **-** |
| Optimized |  100 |  3,874.0 ns |   6.6446 ns |   6.2154 ns |  3,872.9 ns |           - |           - |           - |                   - |
|    **Common** | **1000** | **65,999.4 ns** | **358.5663 ns** | **335.4031 ns** | **65,956.8 ns** |           **-** |           **-** |           **-** |                   **-** |
| Optimized | 1000 | 36,748.7 ns |  58.3813 ns |  54.6099 ns | 36,749.5 ns |           - |           - |           - |                   - |
