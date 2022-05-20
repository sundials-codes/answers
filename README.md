# sundials-codes/answers

This repo holds answer files for the SUNDIALS tests and examples suites.
We create directories for different os+microarchitectures and/or hosts since
the generated answers are generally sensitive to the machine on which they were
created. 

The naming convention for the directories is either ``<os>-<microarch>`` or 
``<hostname>``. Note that the first format can easily be generated using [Spack](https://github.com/spack/spack):

```
mkdir $(spack arch)
```

Within these directories, we create directories for different precisions, e.g. ``single`` or ``double``.

## Useful tools

[Archspec](https://archspec.readthedocs.io/en/latest/index.html) is a useful Python library
for detecting the CPU microarchitecture of the system you are on. It can be installed
via pip:

```
$ pip install archspec
$ archspec cpu
skylake_avx512
```

