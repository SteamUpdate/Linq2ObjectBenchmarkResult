``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|                   Method |    N |        Mean |      Error |     StdDev |      Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|------------------------- |----- |------------:|-----------:|-----------:|------------:|------------:|------------:|------------:|--------------------:|
| **&#39;Array.Find with lambda&#39;** |   **10** |    **26.63 ns** |  **0.0188 ns** |  **0.0176 ns** |    **26.63 ns** |           **-** |           **-** |           **-** |                   **-** |
|               Array.Find |   10 |    28.19 ns |  0.0337 ns |  0.0315 ns |    28.18 ns |           - |           - |           - |                   - |
|           FirstOrDefault |   10 |   103.90 ns |  0.1067 ns |  0.0946 ns |   103.87 ns |      0.0067 |           - |           - |                32 B |
| **&#39;Array.Find with lambda&#39;** |  **100** |   **257.21 ns** |  **0.1873 ns** |  **0.1752 ns** |   **257.17 ns** |           **-** |           **-** |           **-** |                   **-** |
|               Array.Find |  100 |   258.12 ns |  0.1804 ns |  0.1688 ns |   258.11 ns |           - |           - |           - |                   - |
|           FirstOrDefault |  100 |   839.64 ns |  0.3723 ns |  0.3301 ns |   839.59 ns |      0.0067 |           - |           - |                32 B |
| **&#39;Array.Find with lambda&#39;** | **1000** | **1,633.12 ns** |  **2.5875 ns** |  **2.4203 ns** | **1,632.50 ns** |           **-** |           **-** |           **-** |                   **-** |
|               Array.Find | 1000 | 1,636.54 ns |  1.4094 ns |  1.1769 ns | 1,636.44 ns |           - |           - |           - |                   - |
|           FirstOrDefault | 1000 | 4,265.24 ns | 11.9633 ns | 10.6051 ns | 4,267.67 ns |           - |           - |           - |                32 B |
