# `Count` (Property)

## Code
```csharp
public int TestSet()
{
    return set.Count;
    // return array.Length;
}
```

## Framework
|    Method |    N |      Mean |     Error |    StdDev |    Median |       Min |       Max | Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |----------:|----------:|----------:|----------:|----------:|----------:|------------:|------------:|------------:|--------------------:|
|      List |   10 | 0.0266 ns | 0.0016 ns | 0.0015 ns | 0.0264 ns | 0.0244 ns | 0.0301 ns |           - |           - |           - |                   - |
| HashedSet |   10 | 0.4729 ns | 0.0022 ns | 0.0021 ns | 0.4723 ns | 0.4698 ns | 0.4770 ns |           - |           - |           - |                   - |
|     Array |   10 | 0.0000 ns | 0.0000 ns | 0.0000 ns | 0.0000 ns | 0.0000 ns | 0.0000 ns |           - |           - |           - |                   - |
|      **List** |  **100** | **0.0265 ns** | **0.0010 ns** | **0.0009 ns** | **0.0264 ns** | **0.0251 ns** | **0.0279 ns** |           **-** |           **-** |           **-** |                   **-** |
| **HashedSet** |  **100** | **0.4744 ns** | **0.0012 ns** | **0.0011 ns** | **0.4745 ns** | **0.4719 ns** | **0.4761 ns** |           **-** |           **-** |           **-** |                   **-** |
|     **Array** |  **100** | **0.0483 ns** | **0.0015 ns** | **0.0013 ns** | **0.0483 ns** | **0.0459 ns** | **0.0506 ns** |           **-** |           **-** |           **-** |                   **-** |
|      List | 1000 | 0.0271 ns | 0.0011 ns | 0.0010 ns | 0.0272 ns | 0.0251 ns | 0.0285 ns |           - |           - |           - |                   - |
| HashedSet | 1000 | 0.4739 ns | 0.0032 ns | 0.0028 ns | 0.4726 ns | 0.4713 ns | 0.4796 ns |           - |           - |           - |                   - |
|     Array | 1000 | 0.0478 ns | 0.0015 ns | 0.0014 ns | 0.0477 ns | 0.0462 ns | 0.0501 ns |           - |           - |           - |                   - |


## Core
|    Method |    N |      Mean |     Error |    StdDev |    Median |       Min |       Max | Gen 0 | Gen 1 | Gen 2 | Allocated |
|---------- |----- |----------:|----------:|----------:|----------:|----------:|----------:|------:|------:|------:|----------:|
|      List |   10 | 0.0118 ns | 0.0013 ns | 0.0011 ns | 0.0116 ns | 0.0105 ns | 0.0143 ns |     - |     - |     - |         - |
| HashedSet |   10 | 0.4978 ns | 0.0020 ns | 0.0018 ns | 0.4976 ns | 0.4949 ns | 0.5010 ns |     - |     - |     - |         - |
|     Array |   10 | 0.0174 ns | 0.0018 ns | 0.0016 ns | 0.0171 ns | 0.0156 ns | 0.0210 ns |     - |     - |     - |         - |
|      **List** |  **100** | **0.0201 ns** | **0.0022 ns** | **0.0019 ns** | **0.0200 ns** | **0.0167 ns** | **0.0236 ns** |     **-** |     **-** |     **-** |         **-** |
| **HashedSet** |  **100** | **0.4988 ns** | **0.0041 ns** | **0.0038 ns** | **0.4991 ns** | **0.4936 ns** | **0.5064 ns** |     **-** |     **-** |     **-** |         **-** |
|     **Array** |  **100** | **0.0183 ns** | **0.0013 ns** | **0.0011 ns** | **0.0183 ns** | **0.0169 ns** | **0.0206 ns** |     **-** |     **-** |     **-** |         **-** |
|      List | 1000 | 0.0175 ns | 0.0016 ns | 0.0015 ns | 0.0179 ns | 0.0143 ns | 0.0192 ns |     - |     - |     - |         - |
| HashedSet | 1000 | 0.5008 ns | 0.0031 ns | 0.0029 ns | 0.5002 ns | 0.4972 ns | 0.5071 ns |     - |     - |     - |         - |
|     Array | 1000 | 0.0156 ns | 0.0015 ns | 0.0014 ns | 0.0156 ns | 0.0133 ns | 0.0177 ns |     - |     - |     - |         - |