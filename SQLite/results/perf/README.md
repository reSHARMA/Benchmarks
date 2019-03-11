# Performance results

We measured the performance with both -O3 and Os options. We took I refs as the performance measure, less miss implies higher performance.

### I ref results

|  | -O3 | -Os | 
|------|------|-----|
|clang-8 |1,060,020,906|1,097,454,319|
|clang-8 with patch|1,054,717,026|1,096,107,301|
|% decrease in I ref value with gcm|1.06%|1.097%|
