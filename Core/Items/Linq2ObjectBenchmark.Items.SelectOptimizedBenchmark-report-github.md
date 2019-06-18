``` ini

BenchmarkDotNet=v0.11.5, OS=Windows 10.0.14393.2999 (1607/AnniversaryUpdate/Redstone1)
Intel Core i5-8500 CPU 3.00GHz (Coffee Lake), 1 CPU, 6 logical and 6 physical cores
Frequency=2929684 Hz, Resolution=341.3337 ns, Timer=TSC
.NET Core SDK=2.2.105
  [Host] : .NET Core 2.2.3 (CoreCLR 4.6.27414.05, CoreFX 4.6.27414.05), 64bit RyuJIT

Job=Clr  Runtime=Clr  

```
|    Method |    N | Mean | Error | Median | Min | Max | Rank |
|---------- |----- |-----:|------:|-------:|----:|----:|-----:|
|      **List** |   **10** |   **NA** |    **NA** |     **NA** |  **NA** |  **NA** |    **?** |
| HashedSet |   10 |   NA |    NA |     NA |  NA |  NA |    ? |
|     Array |   10 |   NA |    NA |     NA |  NA |  NA |    ? |
|      **List** |  **100** |   **NA** |    **NA** |     **NA** |  **NA** |  **NA** |    **?** |
| HashedSet |  100 |   NA |    NA |     NA |  NA |  NA |    ? |
|     Array |  100 |   NA |    NA |     NA |  NA |  NA |    ? |
|      **List** | **1000** |   **NA** |    **NA** |     **NA** |  **NA** |  **NA** |    **?** |
| HashedSet | 1000 |   NA |    NA |     NA |  NA |  NA |    ? |
|     Array | 1000 |   NA |    NA |     NA |  NA |  NA |    ? |

Benchmarks with issues:
  SelectOptimizedBenchmark.List: Clr(Runtime=Clr) [N=10]
  SelectOptimizedBenchmark.HashedSet: Clr(Runtime=Clr) [N=10]
  SelectOptimizedBenchmark.Array: Clr(Runtime=Clr) [N=10]
  SelectOptimizedBenchmark.List: Clr(Runtime=Clr) [N=100]
  SelectOptimizedBenchmark.HashedSet: Clr(Runtime=Clr) [N=100]
  SelectOptimizedBenchmark.Array: Clr(Runtime=Clr) [N=100]
  SelectOptimizedBenchmark.List: Clr(Runtime=Clr) [N=1000]
  SelectOptimizedBenchmark.HashedSet: Clr(Runtime=Clr) [N=1000]
  SelectOptimizedBenchmark.Array: Clr(Runtime=Clr) [N=1000]
