# SECprofiler

**Prototype of [CCprofiler](https://github.com/CCprofiler/CCprofiler)**, initially developed by
R. Hafen and M. Heusel (with contributions by I. Bludau and others).

SECprofiler is an R package for detecting protein complex features in size-exclusion
chromatography (SEC) co-fractionation data, in particular SEC-SWATH-MS. It established the
core concepts later matured in CCprofiler:

- import of peptide/protein elution traces from OpenSWATH, MaxQuant and OpenMS
- sibling peptide correlation filtering and protein quantification from peptide traces
- complex-centric feature detection: querying complex hypotheses (e.g. CORUM) in the
  co-elution data via sliding-window and peak-picking approaches
- SEC molecular-weight calibration, stoichiometry estimation, benchmarking
- the interactive SECexplorer viewer

> This repository is kept for provenance. For analysis, use
> **[CCprofiler](https://github.com/CCprofiler/CCprofiler)**.

## Installation (development)

```r
# install.packages("devtools")
devtools::install_github("heuselm/SECprofiler")
# or, from a local clone:
devtools::load_all()
```

Package dependencies can be installed globally with `sudo ./install_r_packages`.
Branches: `master` (default), `peakpicker`, `secexplorer`, `newstuff_mhe`,
`refactor/new-sw-output`.

## Data structure: elution profiling (`traces`) container
```
Trace container: List with:
    Class: "Traces"
    $traces (data.table Column1: id Column 2:end numeric quant matrix)
    $annotation (data.table, contains id column as key for merging and associated annotations in separate columns)
    $trace_type (character, "peptide" or "protein")
```


## Reference

Heusel, M., Bludau, I., Rosenberger, G., Hafen, R., Frank, M., Banaei-Esfahani, A.,
van Drogen, A., Collins, B.C., Gstaiger, M., Aebersold, R. (2019). Complex-centric proteome
profiling by SEC-SWATH-MS. *Molecular Systems Biology* 15, e8438.
https://doi.org/10.15252/msb.20188438

## License

MIT (see `DESCRIPTION`).

---
<sub>README optimized with Claude Opus 5.5.</sub>
