``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
|    Method |    N |         Mean |      Error |     StdDev |       Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-------------:|-----------:|-----------:|-------------:|-------:|------:|------:|----------:|
|    **Common** |   **10** |    **434.02 ns** |  **0.8373 ns** |  **0.7833 ns** |    **433.95 ns** | **0.0405** |     **-** |     **-** |     **192 B** |
| Optimized |   10 |     50.79 ns |  0.0862 ns |  0.0807 ns |     50.78 ns | 0.0085 |     - |     - |      40 B |
|    **Common** |  **100** |  **2,599.63 ns** |  **4.7691 ns** |  **4.2277 ns** |  **2,598.52 ns** | **0.0381** |     **-** |     **-** |     **192 B** |
| Optimized |  100 |    325.28 ns |  0.2726 ns |  0.2416 ns |    325.24 ns | 0.0081 |     - |     - |      40 B |
|    **Common** | **1000** | **27,277.88 ns** | **81.6082 ns** | **76.3363 ns** | **27,274.63 ns** | **0.0305** |     **-** |     **-** |     **248 B** |
| Optimized | 1000 |  6,544.98 ns | 38.7707 ns | 36.2662 ns |  6,558.83 ns | 0.0153 |     - |     - |      96 B |
