``` ini

BenchmarkDotNet=v0.11.4, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
  [Host] : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0
  Clr    : .NET Framework 4.7.2 (CLR 4.0.30319.42000), 64bit RyuJIT-v4.7.3416.0

Job=Clr  Runtime=Clr  

```
|                        Method |    N |        Mean |      Error |     StdDev |      Median | Gen 0/1k Op | Gen 1/1k Op | Gen 2/1k Op | Allocated Memory/Op |
|------------------------------ |----- |------------:|-----------:|-----------:|------------:|------------:|------------:|------------:|--------------------:|
|                        **OfType** |   **10** |    **428.0 ns** |  **0.8030 ns** |  **0.7118 ns** |    **427.9 ns** |      **0.0911** |           **-** |           **-** |               **432 B** |
|       &#39;foreach (is and cast)&#39; |   10 |    173.8 ns |  0.3058 ns |  0.2861 ns |    173.9 ns |      0.0710 |           - |           - |               336 B |
| &#39;foreach (as and null check)&#39; |   10 |    178.4 ns |  0.5192 ns |  0.4857 ns |    178.3 ns |      0.0710 |           - |           - |               336 B |
|                        **OfType** |  **100** |  **2,936.7 ns** |  **4.3845 ns** |  **4.1013 ns** |  **2,937.1 ns** |      **0.4845** |           **-** |           **-** |              **2296 B** |
|       &#39;foreach (is and cast)&#39; |  100 |  1,097.2 ns |  1.1048 ns |  0.9794 ns |  1,097.2 ns |      0.4654 |           - |           - |              2200 B |
| &#39;foreach (as and null check)&#39; |  100 |  1,081.0 ns |  1.2673 ns |  1.1854 ns |  1,081.4 ns |      0.4654 |           - |           - |              2200 B |
|                        **OfType** | **1000** | **26,629.9 ns** | **45.0987 ns** | **42.1854 ns** | **26,621.4 ns** |      **3.5095** |           **-** |           **-** |             **16707 B** |
|       &#39;foreach (is and cast)&#39; | 1000 |  9,029.9 ns | 13.1356 ns | 12.2870 ns |  9,026.9 ns |      3.5095 |      0.0153 |           - |             16619 B |
| &#39;foreach (as and null check)&#39; | 1000 |  9,106.7 ns | 14.5211 ns | 13.5830 ns |  9,105.8 ns |      3.5095 |      0.0153 |           - |             16619 B |
