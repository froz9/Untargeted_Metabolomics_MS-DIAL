# Untargeted Metabolomics Processing using MS-DIAL

MS-DIAL provides a easy pipeline to perform untargeted metabolomics.
Here you will learn the process to analyze your raw LC-MS/MS data,
and subsequent export for downstream analysis and annotation methods.

## Requirements

Linux or Windows based computer.
As MS-DIAL version 5.5, it is no longer a requirement to convert your vendor (.RAW) LC-MS/MS files into open source format (.MZML, .ABF), you don't need the use of other programs to perform file conversion as Proteowizard.


1. [MS-DIAL](https://github.com/systemsomicslab/MsdialWorkbench/releases) software for Windows needs to be downloaded from the official repository, try to download to most recent version.
- [MassBank MS/MS positive and negative database files](http://prime.psc.riken.jp/compms/msdial/main.html#MSP).
- The LC-MS files all present in a single folder.
- The LC-MS standards file generated during data collection (should contain columns for: metabolite name, m/z, and retention time).
