# SQLite amalgam

We closely followed the instructions to build sqlite-amalgam enabling the flags described [here](https://www.sqlite.org/footprint.html).

## Measuring size

We manually measure size of the binary formed.

## Performance benchmarking

We used [speedtest1.c](https://sqlite.org/src/file/test/speedtest1.c) provided by sqlite for benchmarking speed with options --shrink-memory --reprepare --stats --heap 10000000 64 --size 5 as described [here](https://www.sqlite.org/footprint.html).

The performance was measured by observing the "I refs" .
