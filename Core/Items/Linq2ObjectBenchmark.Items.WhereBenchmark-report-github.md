``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |        Mean |      Error |     StdDev |      Median |         Min |         Max | Rank |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |------------:|-----------:|-----------:|------------:|------------:|------------:|-----:|-------:|------:|------:|----------:|
|      **List** |   **10** |    **193.9 ns** |  **0.3226 ns** |  **0.3017 ns** |    **193.9 ns** |    **193.5 ns** |    **194.6 ns** |    **2** | **0.0236** |     **-** |     **-** |     **112 B** |
| HashedSet |   10 |    270.6 ns |  0.1879 ns |  0.1569 ns |    270.7 ns |    270.3 ns |    270.8 ns |    3 | 0.0286 |     - |     - |     136 B |
|     Array |   10 |    110.3 ns |  0.1589 ns |  0.1486 ns |    110.3 ns |    110.1 ns |    110.6 ns |    1 | 0.0186 |     - |     - |      88 B |
|      **List** |  **100** |  **1,036.8 ns** |  **3.4223 ns** |  **3.2013 ns** |  **1,035.1 ns** |  **1,032.3 ns** |  **1,042.5 ns** |    **5** | **0.0229** |     **-** |     **-** |     **112 B** |
| HashedSet |  100 |  1,375.6 ns |  2.1880 ns |  1.9396 ns |  1,375.3 ns |  1,373.2 ns |  1,380.1 ns |    6 | 0.0286 |     - |     - |     136 B |
|     Array |  100 |    434.4 ns |  0.2781 ns |  0.2601 ns |    434.3 ns |    433.9 ns |    434.8 ns |    4 | 0.0186 |     - |     - |      88 B |
|      **List** | **1000** | **12,025.9 ns** |  **9.1742 ns** |  **8.1327 ns** | **12,027.0 ns** | **12,008.3 ns** | **12,037.7 ns** |    **8** | **0.0305** |     **-** |     **-** |     **168 B** |
| HashedSet | 1000 | 15,509.0 ns | 25.0634 ns | 23.4443 ns | 15,505.3 ns | 15,475.3 ns | 15,558.6 ns |    9 | 0.0305 |     - |     - |     192 B |
|     Array | 1000 |  6,489.4 ns | 25.8974 ns | 24.2245 ns |  6,489.6 ns |  6,445.5 ns |  6,542.3 ns |    7 | 0.0229 |     - |     - |     144 B |