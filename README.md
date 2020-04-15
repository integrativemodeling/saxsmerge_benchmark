[![DOI](https://zenodo.org/badge/doi/10.5281/zenodo.46479.svg)](http://dx.doi.org/10.5281/zenodo.46479)

This is a benchmark for IMP's SAXS Merge method and webserver.

## Running the benchmark:

Just run `test/test_benchmark.py`. You need gnuplot if you want to make plots.
The benchmark will run saxs
merge on all test systems in the `input/` folder.  All inputs contain an
experimental SAXS profile. Some of them contain a PDB structure, whose SAXS
profile is computed using FoXS and crysol. Comparisons are then also made using
these profiles.


The benchmark takes about 1h to run. Check `example_output` for an example of
the output of the benchmark. It will produce two types of folders per
run:
 - a `runapp_*` folder, in which the merging of the inputs took place
 - a `compapp_*` folder, in which manual and automatic merges are compared

In addition, a file `bench_*.dat` is produced, which contains statistics on the
merge. Its columns are
 1. Run number (an index to the inputs in `input/`)
 1. An index to a set of parameters that was used, currently this is always zero
 1. The name of the input folder
 1. The chi2 between manual and automatic merges
 1. The chi2 between Gaussian Process manual vs automatic mean functions
 1. The radius of gyration in the automatic merge, as guessed with the Guinier fit.
 1. Same as previously
 1. The radius of gyration in the manual merge, as guessed with the Guinier fit.
 1. Same as previously
 1. If a PDB is available, the radius of gyration based on the Guinier fit on
    the FoXS profile
 1. If a PDB is available, the chi2 between automatic merge and FoXS
 1. If a PDB is available, the chi2 between manual merge and FoXS
 1. If a PDB is available, the chi2 between automatic merge and crysol
 1. If a PDB is available, the radius of gyration based on the Guinier fit on
    the crysol profile
 1. The sigma of the Gaussian Process Interpolation on the automatic merge
 1. The sigma of the Gaussian Process Interpolation on the manual merge

Finally, a large number of png files describe visually the inputs and the
outputs. Their name is self-explanatory.

Notice that this benchmark was originally part of an article, which we decided
not to publish. See the warning notice on the [SAXS Merge
website](http://modbase.compbio.ucsf.edu/saxsmerge/)

## Information

_Author(s)_: Yannick G. Spill

_License_: [LGPL](http://www.gnu.org/licenses/old-licenses/lgpl-2.1.html).
This library is free software; you can redistribute it and/or
modify it under the terms of the GNU Lesser General Public
License as published by the Free Software Foundation; either
version 2 of the License, or (at your option) any later version.

_Last known good IMP version_: [![build info](https://integrativemodeling.org/systems/15/badge.svg?branch=master)](https://integrativemodeling.org/systems/) [![build info](https://integrativemodeling.org/systems/15/badge.svg?branch=develop)](https://integrativemodeling.org/systems/)

_Testable_: Yes.

_Parallelizeable_: Yes

_Publications_:
 - [Spill YG, Kim SJ, Schneidman-Duhovny D, Russel D, Webb B, Sali A, Nilges M, J Synchrotron Radiat, (2014) 21, 203-8](http://www.ncbi.nlm.nih.gov/pubmed/24365937)
 - [Pieper U, Webb BM, Dong GQ, Schneidman-Duhovny D, Fan H, Kim SJ, Khuri N, Spill YG, Weinkam P, Hammel M, Tainer JA, Nilges M, Sali A, Nucleic Acids Res, (2014) 42, D336-46](http://www.ncbi.nlm.nih.gov/pubmed/24271400)
 - see also warning notice on the [SAXS Merge website](http://modbase.compbio.ucsf.edu/saxsmerge/)

