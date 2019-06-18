``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |        Mean |     Error |    StdDev |      Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |------------:|----------:|----------:|------------:|------------:|------------:|------------:|--------------------:|
|    **Common** |   **10** |    **41.90 ns** | **0.0308 ns** | **0.0273 ns** |    **41.90 ns** |           **-** |           **-** |           **-** |                   **-** |
| Optimized |   10 |    11.18 ns | 0.0088 ns | 0.0083 ns |    11.18 ns |           - |           - |           - |                   - |
|    **Common** |  **100** |   **345.08 ns** | **0.2251 ns** | **0.2105 ns** |   **345.08 ns** |           **-** |           **-** |           **-** |                   **-** |
| Optimized |  100 |    84.49 ns | 0.1014 ns | 0.0949 ns |    84.48 ns |           - |           - |           - |                   - |
|    **Common** | **1000** | **3,300.97 ns** | **3.7544 ns** | **3.5119 ns** | **3,300.45 ns** |           **-** |           **-** |           **-** |                   **-** |
| Optimized | 1000 |   766.16 ns | 0.9988 ns | 0.9343 ns |   766.38 ns |           - |           - |           - |                   - |
