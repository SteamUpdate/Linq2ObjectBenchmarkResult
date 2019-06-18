``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|    Method |    N |     Mean |     Error |    StdDev |   Median |      Min |      Max | Rank | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|---------- |----- |---------:|----------:|----------:|---------:|---------:|---------:|-----:|------------:|------------:|------------:|--------------------:|
|      **List** |   **10** | **13.70 ns** | **0.0249 ns** | **0.0221 ns** | **13.71 ns** | **13.67 ns** | **13.74 ns** |    **1** |           **-** |           **-** |           **-** |                   **-** |
| HashedSet |   10 | 28.91 ns | 0.2336 ns | 0.2185 ns | 28.79 ns | 28.74 ns | 29.35 ns |    3 |      0.0085 |           - |           - |                40 B |
|     Array |   10 | 34.35 ns | 0.0847 ns | 0.0793 ns | 34.36 ns | 34.26 ns | 34.49 ns |    4 |           - |           - |           - |                   - |
|      **List** |  **100** | **13.71 ns** | **0.0169 ns** | **0.0158 ns** | **13.70 ns** | **13.67 ns** | **13.73 ns** |    **1** |           **-** |           **-** |           **-** |                   **-** |
| HashedSet |  100 | 28.65 ns | 0.0393 ns | 0.0367 ns | 28.66 ns | 28.56 ns | 28.71 ns |    3 |      0.0085 |           - |           - |                40 B |
|     Array |  100 | 34.39 ns | 0.0635 ns | 0.0594 ns | 34.38 ns | 34.30 ns | 34.48 ns |    4 |           - |           - |           - |                   - |
|      **List** | **1000** | **14.40 ns** | **0.0140 ns** | **0.0131 ns** | **14.40 ns** | **14.38 ns** | **14.43 ns** |    **2** |           **-** |           **-** |           **-** |                   **-** |
| HashedSet | 1000 | 28.72 ns | 0.0273 ns | 0.0255 ns | 28.71 ns | 28.69 ns | 28.78 ns |    3 |      0.0085 |           - |           - |                40 B |
|     Array | 1000 | 34.44 ns | 0.0810 ns | 0.0758 ns | 34.44 ns | 34.33 ns | 34.57 ns |    4 |           - |           - |           - |                   - |
