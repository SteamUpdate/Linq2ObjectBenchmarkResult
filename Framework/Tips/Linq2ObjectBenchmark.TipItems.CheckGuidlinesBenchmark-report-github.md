``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2906 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929688 Hz, Resolution=341.3333 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3394.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3394.0

Job=Clr  Runtime=Clr  

```
|                   Method |    N |        Mean |      Error |    StdDev |      Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|------------------------- |----- |------------:|-----------:|----------:|------------:|------------:|------------:|------------:|--------------------:|
| **&#39;Array.Find with lambda&#39;** |   **10** |    **26.76 ns** |  **0.1322 ns** | **0.1237 ns** |    **26.71 ns** |           **-** |           **-** |           **-** |                   **-** |
|               Array.Find |   10 |    27.27 ns |  0.5079 ns | 0.4751 ns |    27.07 ns |           - |           - |           - |                   - |
|           FirstOrDefault |   10 |   105.04 ns |  0.2300 ns | 0.1920 ns |   105.02 ns |      0.0067 |           - |           - |                32 B |
| **&#39;Array.Find with lambda&#39;** |  **100** |   **258.45 ns** |  **0.5590 ns** | **0.4956 ns** |   **258.34 ns** |           **-** |           **-** |           **-** |                   **-** |
|               Array.Find |  100 |   258.62 ns |  0.2642 ns | 0.2342 ns |   258.62 ns |           - |           - |           - |                   - |
|           FirstOrDefault |  100 |   816.68 ns |  1.1391 ns | 1.0098 ns |   816.47 ns |      0.0067 |           - |           - |                32 B |
| **&#39;Array.Find with lambda&#39;** | **1000** | **1,643.16 ns** |  **2.5265 ns** | **2.3633 ns** | **1,642.38 ns** |           **-** |           **-** |           **-** |                   **-** |
|               Array.Find | 1000 | 1,638.21 ns |  3.2262 ns | 3.0178 ns | 1,637.80 ns |           - |           - |           - |                   - |
|           FirstOrDefault | 1000 | 4,292.98 ns | 10.3782 ns | 8.6663 ns | 4,289.06 ns |           - |           - |           - |                32 B |
