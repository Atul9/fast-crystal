# 💎 Fast Crystal

It's Crystal version based on [ruby version](https://github.com/JuanitoFatas/fast-ruby).

Each idiom has a corresponding code example that resides in [code](code).


All results listed in README.md are running with Crystal 0.22.0 (2017-04-20) LLVM 4.0.0 on OS X 10.12.4 in release mode.
Machine information: MacBook Pro (Retina, 15-inch, Mid 2015), 2.2 GHz Intel Core i7, 16 GB 1600 MHz DDR3.
Your results may vary, but you get the idea. : )

**Let's write faster code, together! <3**

## Measurement Tool

Use [benchmark](https://crystal-lang.org/api/0.22.0/Benchmark.html).

## Run the Benchmarks

```
$ crystal src/fast-crystal.cr
```

### Template

```crystal
require "benchmark"

def fast
end

def slow
end

Benchmark.ips do |x|
  x.report("fast code description") { fast }
  x.report("slow code description") { slow }
end
```

## Idioms

### Index

- [General](#general)
- [Array](#array)
- [Enumerable](#enumerable)
- [Hash](#hash)
- [Proc & Block](#proc--block)
- [String](#string)
- [Range](#range)

### General

##### Parallel Assignment vs Sequential Assignment [code](code/general/assignment.cr)

```
RUN crystal build --release code/general/assignment.cr -o bin/general/assignment_benchmark
RUN ./bin/general/assignment_benchmark with Crystal 0.22.0 (2017-04-20) LLVM 4.0.0

Sequential Assignment  445.6M (  2.24ns) (±16.59%)       fastest
  Parallel Assignment 412.08M (  2.43ns) (±15.75%)  1.08× slower
```

##### Positional arguments vs Named arguments [code](code/general/positional_argument_vs_named_argument.cr)

```
RUN crystal build --release code/general/positional_argument_vs_named_argument.cr -o bin/general/positional_argument_vs_named_argument_benchmark
RUN ./bin/general/positional_argument_vs_named_argument_benchmark with Crystal 0.22.0 (2017-04-20) LLVM 4.0.0

     Named arguments 472.76M (  2.12ns) (±17.01%)       fastest
Positional arguments 455.11M (   2.2ns) (±17.72%)  1.04× slower
```

### Array

### General

### Enumerable

### Hash

### Proc & Block

### String

#### String Concatenation [code](code/string/concatenation.cr)

```
RUN crystal build --release code/string/concatenation.cr -o bin/string/concatenation_benchmark
RUN ./bin/string/concatenation_benchmark with Crystal 0.22.0 (2017-04-20) LLVM 4.0.0

String#+  23.35M ( 42.82ns) (± 3.19%)       fastest
String#"   5.21M ( 192.0ns) (± 2.57%)  4.48× slower
String#%   3.29M (304.04ns) (± 1.97%)  7.10× slower
```

### Range
