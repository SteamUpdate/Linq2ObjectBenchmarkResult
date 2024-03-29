# `Count(q => q...)` [Optimized]

## Code
```csharp
public int TestSet()
{
    var count = 0;
    foreach (var item in set)
    {
        if (item.GetType() == typeof(Entity))
        {
            count++;
        }
    }
    return count;
}
```

## Framework
|    Method |    N |         Mean |      Error |     StdDev |       Median |          Min |          Max |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-------------:|-----------:|-----------:|-------------:|-------------:|-------------:|-------:|------:|------:|----------:|
|      List |   10 |    41.872 ns |  0.3322 ns |  0.3108 ns |    41.981 ns |    41.350 ns |    42.305 ns |      - |     - |     - |         - |
| HashedSet |   10 |   112.260 ns |  0.8197 ns |  0.7668 ns |   112.273 ns |   111.121 ns |   113.539 ns | 0.0085 |     - |     - |      40 B |
|     Array |   10 |     5.520 ns |  0.0353 ns |  0.0330 ns |     5.518 ns |     5.458 ns |     5.576 ns |      - |     - |     - |         - |
|      **List** |  **100** |   **334.502 ns** |  **0.8194 ns** |  **0.7264 ns** |   **334.285 ns** |   **333.747 ns** |   **336.530 ns** |      **-** |     **-** |     **-** |         **-** |
| **HashedSet** |  **100** |   **860.062 ns** |  **4.5695 ns** |  **4.2743 ns** |   **859.873 ns** |   **850.223 ns** |   **868.802 ns** | **0.0076** |     **-** |     **-** |      **40 B** |
|     **Array** |  **100** |    **56.530 ns** |  **0.3747 ns** |  **0.3505 ns** |    **56.490 ns** |    **56.144 ns** |    **57.371 ns** |      **-** |     **-** |     **-** |         **-** |
|      List | 1000 | 3,254.345 ns | 31.0505 ns | 27.5255 ns | 3,257.503 ns | 3,218.693 ns | 3,302.966 ns |      - |     - |     - |         - |
| HashedSet | 1000 | 8,328.915 ns | 78.2937 ns | 73.2360 ns | 8,360.223 ns | 8,198.441 ns | 8,431.608 ns |      - |     - |     - |      40 B |
|     Array | 1000 |   634.370 ns | 13.9041 ns | 19.4916 ns |   630.798 ns |   595.003 ns |   669.881 ns |      - |     - |     - |         - |


## Core
|    Method |    N |         Mean |      Error |     StdDev |       Median |          Min |          Max |  Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |-------------:|-----------:|-----------:|-------------:|-------------:|-------------:|-------:|------:|------:|----------:|
|      List |   10 |    41.543 ns |  0.0657 ns |  0.0615 ns |    41.544 ns |    41.442 ns |    41.667 ns |      - |     - |     - |         - |
| HashedSet |   10 |    97.032 ns |  0.1038 ns |  0.0971 ns |    97.031 ns |    96.832 ns |    97.191 ns | 0.0085 |     - |     - |      40 B |
|     Array |   10 |     5.640 ns |  0.0076 ns |  0.0071 ns |     5.639 ns |     5.626 ns |     5.653 ns |      - |     - |     - |         - |
|      **List** |  **100** |   **333.834 ns** |  **0.3357 ns** |  **0.2976 ns** |   **333.832 ns** |   **333.312 ns** |   **334.234 ns** |      **-** |     **-** |     **-** |         **-** |
| **HashedSet** |  **100** |   **778.215 ns** |  **0.6847 ns** |  **0.6404 ns** |   **778.139 ns** |   **777.314 ns** |   **779.151 ns** | **0.0076** |     **-** |     **-** |      **40 B** |
|     **Array** |  **100** |    **56.075 ns** |  **0.0684 ns** |  **0.0640 ns** |    **56.086 ns** |    **55.997 ns** |    **56.240 ns** |      **-** |     **-** |     **-** |         **-** |
|      List | 1000 | 3,211.679 ns |  1.9797 ns |  1.7550 ns | 3,211.679 ns | 3,208.768 ns | 3,214.904 ns |      - |     - |     - |         - |
| HashedSet | 1000 | 7,610.392 ns |  5.9234 ns |  5.2510 ns | 7,610.405 ns | 7,603.322 ns | 7,617.772 ns | 0.0076 |     - |     - |      40 B |
|     Array | 1000 |   615.456 ns | 12.0895 ns | 16.9478 ns |   622.544 ns |   583.950 ns |   636.772 ns |      - |     - |     - |         - |
