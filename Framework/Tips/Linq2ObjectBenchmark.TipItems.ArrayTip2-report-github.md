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
|    **Common** |   **10** |   **5.152 ns** | **0.1406 ns** | **0.1315 ns** |   **5.086 ns** |           **-** |           **-** |           **-** |                   **-** |
| Optimized |   10 |   2.827 ns | 0.0046 ns | 0.0041 ns |   2.828 ns |           - |           - |           - |                   - |
|    **Common** |  **100** |  **54.809 ns** | **0.0772 ns** | **0.0723 ns** |  **54.787 ns** |           **-** |           **-** |           **-** |                   **-** |
| Optimized |  100 |  43.082 ns | 0.0442 ns | 0.0391 ns |  43.088 ns |           - |           - |           - |                   - |
|    **Common** | **1000** | **509.873 ns** | **0.8112 ns** | **0.7191 ns** | **509.857 ns** |           **-** |           **-** |           **-** |                   **-** |
| Optimized | 1000 | 273.982 ns | 0.4473 ns | 0.4184 ns | 274.138 ns |           - |           - |           - |                   - |
