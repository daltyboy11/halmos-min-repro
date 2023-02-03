# Steps to reproduce
Run `forge test` in the root dir. This should succeed with output
```
Running 2 tests for test/Counter.t.sol:CounterTest
[PASS] testIncrement() (gas: 28356)
[PASS] testSetNumber(uint256) (runs: 256, μ: 27098, ~: 28342)
Test result: ok. 2 passed; 0 failed; finished in 8.03ms

Running 2 tests for test/Counter0-6-12.sol:CounterTest
[PASS] testIncrement() (gas: 28470)
[PASS] testSetNumber(uint256) (runs: 256, μ: 27782, ~: 28560)
Test result: ok. 2 passed; 0 failed; finished in 8.27ms
```

Next run `halmos` in the root dir. This will fail with output similar to:
```
Traceback (most recent call last):
  File "/Users/goldfinch/Library/Python/3.10/bin/halmos", line 8, in <module>
    sys.exit(main())
  File "/Users/goldfinch/Library/Python/3.10/lib/python/site-packages/halmos/__main__.py", line 356, in main
    if len(cryticCompile.compilation_units) > 1: raise ValueError('Multiple compilation units', cryticCompile.compilation_units)
ValueError: ('Multiple compilation units', {'2ac028068425fe641bd47dd95ace52a4': <crytic_compile.compilation_unit.CompilationUnit object at 0x105cbfa30>, '03d8f3133f7ef1aa74f7c6937c4c8d49': <crytic_compile.compilation_unit.CompilationUnit object at 0x105cbdea0>})
```

# Halmos Issue
https://github.com/a16z/halmos/issues/16