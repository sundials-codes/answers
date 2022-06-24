# sundials-codes/answers

This repo holds answer files for the SUNDIALS tests and examples suites.
We create directories for different os+microarchitectures and/or hosts since
the generated answers are generally sensitive to the machine on which they were
created. 

The naming convention for the directories is either ``<os>-<microarch>/<compiler>`` or 
``<hostname>/<compiler>``.
Note that the first format can easily be generated using [Spack](https://github.com/spack/spack):

```
mkdir $(spack arch)/<compiler>
```

Within these directories, we create directories for different precisions, e.g. ``single`` or ``double``.


## Procedure for adding new answers

To add new answers, start by copying the relevant answers in https://github.com/sundials-codes/answers/tree/main/linux-ubuntu20.04-skylake_avx512/ to your new directory (following the naming scheme outlined above). 

Next Commit these files and open a PR to the "staging" branch.

Once the PR is merged, you can generate your new answer files and overwrite the ones you copied from https://github.com/sundials-codes/answers/tree/main/linux-ubuntu20.04-skylake_avx512/. 

Compare the diff and make sure it is reasonable, then commit.

Finally, open a new PR targeting the "staging" branch.

Eventually, "staging" will be merged into main.


## Procedure for updating existing answers

Open a PR against main directly.


## Useful tools

[Archspec](https://archspec.readthedocs.io/en/latest/index.html) is a useful Python library
for detecting the CPU microarchitecture of the system you are on. It can be installed
via pip:

```
$ pip install archspec
$ archspec cpu
skylake_avx512
```

