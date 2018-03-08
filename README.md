Turbo Boost
===============

This is one of @brendangregg's Model Specific Register (MSR) tools ported to FreeBSD.
To see the original tools, check out [here](https://github.com/brendangregg/msr-cloud-tools).

## Prereqs

This tool depends on [x86info](https://www.freshports.org/sysutils/x86info/) package to get the `CPU family`, and `Set CPU MHZ`(Estimated current CPU frequency).

It also uses [cpucontrol(8)](https://www.freebsd.org/cgi/man.cgi?query=cpucontrol&sektion=8&manpath=FreeBSD+8.0-RELEASE) to read the msr values.

Tested on FreeBSD 12.0-CURRENT.
```
# sudo pkg install x86info
# kldload cpuctl
```

## Contents

- [showboost](showboost): show the real CPU clock rate to understand the current level of turbo boost.

## Screenshots

Measure the actual clock rate for CPU 0:

<pre>
# <b>./showboost</b>
Base CPU MHz : 3000
Set CPU MHz  : 3000
Turbo MHz(s) : 3400 3500
Turbo Ratios : 113% 116%
CPU 0 summary every 1 seconds...

TIME       C0_MCYC      C0_ACYC        UTIL  RATIO    MHz
21:41:43   3021819807   3521745975     100%   116%   3496
21:41:44   3021682653   3521564103     100%   116%   3496
21:41:45   3021389796   3521576679     100%   116%   3496
21:41:46   3021685725   3521635645     100%   116%   3496
21:41:47   3021297135   3521362183     100%   116%   3496
[...]
</pre>

