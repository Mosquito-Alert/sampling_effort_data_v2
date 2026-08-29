# Mosquito Alert Sampling Effort Data (v2)

Open access data on Mosquito Alert participation and sampling effort, produced
with the **revised (v2) propensity estimator**.

## Description

This dataset contains data on participation and sampling effort in the
[Mosquito Alert](http://www.mosquitoalert.com/) citizen science system. It can
be used for a variety of purposes, including (a) to adjust estimates of
mosquito population densities and human-mosquito encounters based on sampling
effort, and (b) to better understand the dynamics of citizen scientists'
participation. The data is organized spatially by grids of "sampling cells,"
drawn at intervals of 0.05 degree and 0.025 degree latitude and longitude, and
it is based on optional anonymous background tracks from the Mosquito Alert
app. The dataset includes raw track counts aggregated in sampling cells, along
with estimates of sampling effort based on a model of participants' propensity
to send any report as a function of the time elapsed since they first began
participating.

## What is v2? Relationship to the original sampling effort dataset

This is a revised version of the
[Mosquito Alert sampling effort dataset](https://github.com/Mosquito-Alert/sampling_effort_data)
([doi:10.5281/zenodo.5802476](https://doi.org/10.5281/zenodo.5802476)). In
2026 we identified an error in the way the daily reporting-propensity model
was estimated in the original (v1) pipeline: the risk sets used for the
discrete-time hazard estimates counted reporting-day records rather than
participants, which deflated the estimated propensities (and hence the
sampling effort values) by an amount that grows with participation time —
by a factor of roughly 1.4 for new participants up to roughly 5 or more for
long-term participants. Cell-day sampling effort values in v2 are therefore
higher than in v1 (typically by a factor of about 1.4 to 2.5), with the
largest revisions in places and times dominated by long-term participants.
The *ranking* of cell-days is almost unchanged (rank correlation above 0.99).
v2 also makes two smaller corrections to the imputation of participation
spans and adds a fixed per-run-date random seed so that each day's dataset
can be regenerated exactly. A detailed description and comparison is being
prepared as a data descriptor article; until it is published, the revision
is documented in the metadata files here.

**Which version should I use?** New analyses should use v2. The v1 dataset
continues to be produced and published in parallel for users who need
continuity of an existing time series, but it carries a notice pointing here.

**Switching from v1:** the file names and column layout here are identical to
v1, so existing download and processing code only needs to point at this
repository instead.

## Contents

The repository contains the following files:

* `sampling_effort_daily_cellres_025.csv.gz` - Daily participation and sampling effort in 0.025 degree sampling cells (v2 estimator).
* `sampling_effort_daily_cellres_025_metadata.json` - Metadata for the 0.025 degree sampling cell data.
* `CITATION.cff` - Shows how to cite this dataset.
* `LICENSE` - License for this dataset (CC0).
* `.gitignore` - Specifies which files are excluded from the git repository.
* `README.md` - This file.

## Permanent Location

All releases from this repository are also hosted on Zenodo. The latest
version can always be found through the concept DOI:

[![DOI:10.5281/zenodo.22112557](https://zenodo.org/badge/DOI/10.5281/zenodo.22112557.svg)](https://doi.org/10.5281/zenodo.22112557)
