``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|                        Method |    N |        Mean |      Error |     StdDev |      Median |  Gen 0 |  Gen 1 | Gen 2 | Allocated |
|------------------------------ |----- |------------:|-----------:|-----------:|------------:|-------:|-------:|------:|----------:|
|                        **OfType** |   **10** |    **455.9 ns** |  **0.7345 ns** |  **0.6871 ns** |    **456.0 ns** | **0.0911** |      **-** |     **-** |     **432 B** |
|       &#39;foreach (is and cast)&#39; |   10 |    157.1 ns |  0.3402 ns |  0.3182 ns |    157.2 ns | 0.0710 |      - |     - |     336 B |
| &#39;foreach (as and null check)&#39; |   10 |    149.7 ns |  0.2239 ns |  0.1985 ns |    149.7 ns | 0.0710 |      - |     - |     336 B |
|                        **OfType** |  **100** |  **2,732.7 ns** |  **3.0637 ns** |  **2.7159 ns** |  **2,732.2 ns** | **0.4845** |      **-** |     **-** |    **2296 B** |
|       &#39;foreach (is and cast)&#39; |  100 |  1,006.9 ns |  2.9184 ns |  2.5871 ns |  1,006.3 ns | 0.4654 |      - |     - |    2200 B |
| &#39;foreach (as and null check)&#39; |  100 |    939.0 ns |  1.4949 ns |  1.3252 ns |    938.9 ns | 0.4654 |      - |     - |    2200 B |
|                        **OfType** | **1000** | **23,713.4 ns** | **30.9775 ns** | **27.4607 ns** | **23,702.2 ns** | **3.5095** |      **-** |     **-** |   **16704 B** |
|       &#39;foreach (is and cast)&#39; | 1000 |  8,036.8 ns | 21.1932 ns | 18.7872 ns |  8,036.0 ns | 3.5095 | 0.0153 |     - |   16608 B |
| &#39;foreach (as and null check)&#39; | 1000 |  7,777.5 ns | 16.1499 ns | 15.1067 ns |  7,777.1 ns | 3.5095 | 0.0153 |     - |   16608 B |
