# Plot heatmap of degradation scaling parameters

Creates a heatmap showing the scaling of refuge density across bleaching
years and refuge size bins for a given degradation trajectory. The input
data should have the first column as bleaching year, and the remaining
columns as refuge size bins.

## Usage

``` r
plotDegradationScale(object = NULL, trajectory = NULL, return_data = FALSE)
```

## Arguments

- object:

  An optional object of class MizerParams or MizerSim. If provided, the
  function will attempt to extract the degradation scaling or trajectory
  from its `@other_params$refuge_params` slot.

- trajectory:

  Optional. Either a character string (`"rubble"`, `"algae"`,
  `"recovery"`) to use built-in data, or a user-provided numeric
  matrix/data.frame with the correct format (bleaching year in first
  column, remaining columns as refuge size bins).

- return_data:

  Logical. If TRUE, returns the formatted data frame instead of the
  plot. Default FALSE.

## Value

A ggplot2 object (heatmap), or a data frame if `return_data = TRUE`.

## Details

This function is flexible in its input:

- If `trajectory` is provided, it takes precedence. It can be:

  - A character string (`"rubble"`, `"algae"`, `"recovery"`) to use
    built-in data.

  - A user-provided numeric matrix or data.frame (bleaching year in
    first column, remaining columns as refuge size bins).

- If `trajectory` is not provided, `object` must be supplied and can be
  a MizerParams or MizerSim object. The function will extract the
  degradation scaling or trajectory from
  `object@other_params$refuge_params$trajectory` or
  `object@other_params$refuge_params$deg_scale`.

## See also

[plotting_functions](https://sizespectrum.org/mizer/reference/plotting_functions.html),
[`setDegradation()`](https://cmbeese.github.io/mizerReef/reference/setDegradation.md),
[`reefDegrade()`](https://cmbeese.github.io/mizerReef/reference/reefDegrade.md)

Other plotting functions:
[`plot2Productivity()`](https://cmbeese.github.io/mizerReef/reference/plot2Productivity.md),
[`plot2TotalBiomass()`](https://cmbeese.github.io/mizerReef/reference/plot2TotalBiomass.md),
[`plotProductivity()`](https://cmbeese.github.io/mizerReef/reference/plotProductivity.md),
[`plotProductivityRelative()`](https://cmbeese.github.io/mizerReef/reference/plotProductivityRelative.md),
[`plotRefugeDensity()`](https://cmbeese.github.io/mizerReef/reference/plotRefugeDensity.md),
[`plotRefugeProfile()`](https://cmbeese.github.io/mizerReef/reference/plotRefugeProfile.md),
[`plotRelativeContribution()`](https://cmbeese.github.io/mizerReef/reference/plotRelativeContribution.md),
[`plotSpectraPercentChange()`](https://cmbeese.github.io/mizerReef/reference/plotSpectraPercentChange.md),
[`plotTotalAbundance()`](https://cmbeese.github.io/mizerReef/reference/plotTotalAbundance.md),
[`plotTotalBiomass()`](https://cmbeese.github.io/mizerReef/reference/plotTotalBiomass.md),
[`plotTotalBiomassRelative()`](https://cmbeese.github.io/mizerReef/reference/plotTotalBiomassRelative.md),
[`plotVulnerable()`](https://cmbeese.github.io/mizerReef/reference/plotVulnerable.md)
