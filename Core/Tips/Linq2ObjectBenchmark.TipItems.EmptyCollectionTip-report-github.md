``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT
  Core   : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Core  Runtime=Core  

```
| Method |     Mean |     Error |    StdDev |   Median |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|------- |---------:|----------:|----------:|---------:|-------:|------:|------:|----------:|
|   List | 6.508 ns | 0.0245 ns | 0.0229 ns | 6.508 ns | 0.0085 |     - |     - |      40 B |
|  Array | 2.230 ns | 0.0063 ns | 0.0055 ns | 2.229 ns | 0.0051 |     - |     - |      24 B |
|   Linq | 2.053 ns | 0.0034 ns | 0.0031 ns | 2.053 ns |      - |     - |     - |         - |
