# ahocorasick

A Golang implementation of the Aho-Corasick string matching algorithm

[![Go Report Card](https://goreportcard.com/badge/github.com/alessiosavi/ahocorasick)](https://goreportcard.com/report/github.com/alessiosavi/ahocorasick) [![GoDoc](https://godoc.org/github.com/alessiosavi/ahocorasick?status.svg)](https://godoc.org/github.com/alessiosavi/ahocorasick) [![License](https://img.shields.io/github/license/alessiosavi/ahocorasick)](https://img.shields.io/github/license/alessiosavi/ahocorasick) [![Version](https://img.shields.io/github/v/tag/alessiosavi/ahocorasick)](https://img.shields.io/github/v/tag/alessiosavi/ahocorasick) [![Code size](https://img.shields.io/github/languages/code-size/alessiosavi/ahocorasick)](https://img.shields.io/github/languages/code-size/alessiosavi/ahocorasick) [![Repo size](https://img.shields.io/github/repo-size/alessiosavi/ahocorasick)](https://img.shields.io/github/repo-size/alessiosavi/ahocorasick) [![Issue open](https://img.shields.io/github/issues/alessiosavi/ahocorasick)](https://img.shields.io/github/issues/alessiosavi/ahocorasick)
[![Issue closed](https://img.shields.io/github/issues-closed/alessiosavi/ahocorasick)](https://img.shields.io/github/issues-closed/alessiosavi/ahocorasick)

## Benchmark

```text
$ go test -bench=. -benchmem -benchtime=10s ./...
goos: linux
goarch: amd64
pkg: github.com/alessiosavi/ahocorasick
BenchmarkMatchWorks-8           42344499               275 ns/op              56 B/op          3 allocs/op
BenchmarkContainsWorks-8        62986035               187 ns/op              56 B/op          3 allocs/op
BenchmarkRegexpWorks-8           2241834              5372 ns/op             368 B/op          5 allocs/op
BenchmarkMatchFails-8           62069413               174 ns/op               0 B/op          0 allocs/op
BenchmarkContainsFails-8        160888270               74.2 ns/op             0 B/op          0 allocs/op
BenchmarkRegexpFails-8           1000000             10282 ns/op               0 B/op          0 allocs/op
BenchmarkLongMatchWorks-8        8081287              1462 ns/op              24 B/op          2 allocs/op
BenchmarkLongContainsWorks-8    39643099               292 ns/op              24 B/op          2 allocs/op
BenchmarkLongRegexpWorks-8        199957             57369 ns/op             464 B/op          8 allocs/op
BenchmarkLongMatchFails-8        9623530              1220 ns/op               0 B/op          0 allocs/op
BenchmarkLongContainsFails-8    51155499               223 ns/op               0 B/op          0 allocs/op
BenchmarkLongRegexpFails-8        163587             71553 ns/op               0 B/op          0 allocs/op
BenchmarkMatchMany-8            35751466               322 ns/op              56 B/op          3 allocs/op
BenchmarkContainsMany-8         68172225               161 ns/op               0 B/op          0 allocs/op
BenchmarkRegexpMany-8             219913             53873 ns/op             336 B/op          4 allocs/op
BenchmarkLongMatchMany-8         3854133              3099 ns/op             504 B/op          6 allocs/op
BenchmarkLongContainsMany-8     51949821               218 ns/op               0 B/op          0 allocs/op
BenchmarkLongRegexpMany-8          24644            480811 ns/op            5464 B/op         56 allocs/op
PASS
ok      github.com/alessiosavi/ahocorasick      235.560s
```

Cpu info

```text
Architecture:          x86_64
CPU op-mode(s):        32-bit, 64-bit
Byte Order:            Little Endian
CPU(s):                8
On-line CPU(s) list:   0-7
Thread(s) per core:    2
Core(s) per socket:    4
Socket(s):             1
NUMA node(s):          1
Vendor ID:             GenuineIntel
CPU family:            6
Model:                 158
Model name:            Intel(R) Core(TM) i7-7820HQ CPU @ 2.90GHz
Stepping:              9
CPU MHz:               1799.932
CPU max MHz:           3900.0000
CPU min MHz:           800.0000
BogoMIPS:              5808.00
Virtualization:        VT-x
L1d cache:             32K
L1i cache:             32K
L2 cache:              256K
L3 cache:              8192K
NUMA node0 CPU(s):     0-7
Flags:                 fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe syscall nx pdpe1gb rdtscp lm constant_tsc art arch_perfmon pebs bts rep_good nopl xtopology nonstop_tsc aperfmperf eagerfpu pni pclmulqdq dtes64 monitor ds_cpl vmx smx est tm2 ssse3 sdbg fma cx16 xtpr pdcm pcid sse4_1 sse4_2 x2apic movbe popcnt tsc_deadline_timer aes xsave avx f16c rdrand lahf_lm abm 3dnowprefetch epb invpcid_single intel_pt ssbd ibrs ibpb stibp tpr_shadow vnmi flexpriority ept vpid fsgsbase tsc_adjust bmi1 hle avx2 smep bmi2 erms invpcid rtm mpx rdseed adx smap clflushopt xsaveopt xsavec xgetbv1 dtherm ida arat pln pts hwp hwp_notify hwp_act_window hwp_epp md_clear spec_ctrl intel_stibp flush_l1d
```
