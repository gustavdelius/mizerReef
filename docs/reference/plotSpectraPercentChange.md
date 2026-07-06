# Plot the percent change between two spectra

This plots the percent change between the steady state spectra of two
mizer objects. Let the spectra of the two objects be represented as
\\N_1(w)\\ and \\N_2(w)\\. This function plots the percent change, given
by \$\$ 100\*(N_2(w) - N_1(w)) / (N_1(w)).\$\$

## Usage

``` r
plotSpectraPercentChange(object1, object2, species = NULL, power, ...)

plotlySpectraPercentChange(object1, object2, ...)
```

## Arguments

- object1:

  An object of class MizerSim or MizerParams

- object2:

  An object of class MizerSim or MizerParams

- species:

  The species to be selected. Optional. By default all species are
  selected. A vector of species names, or a numeric vector with the
  species indices, or a logical vector indicating for each species
  whether it is to be selected (TRUE) or not.

- power:

  The abundance is plotted as the number density times the weight raised
  to this power. The default power = 1 gives the biomass density,
  whereas power = 2 gives the biomass density with respect to
  logarithmic size bins.

- ...:

  Parameters passed to `plotSpectra()`

## Value

A ggplot2 object

## Details

For the difference calculated relative to the average of the two
spectra, \\2 (N_2(w) - N_1(w)) / (N_2(w) + N_1(w))\\, use mizer's own
[`mizer::plotSpectraRelative()`](https://sizespectrum.org/mizer/reference/plotSpectraRelative.html),
which already dispatches correctly for `mizerReef` objects.

The individual spectra are calculated by the
[`mizer::plotSpectra()`](https://sizespectrum.org/mizer/reference/plotSpectra.html)
function which is passed all additional arguments you supply. So you can
for example determine a size range over which to average the simulation
results via the `time_range` argument. See
[`mizer::plotSpectra()`](https://sizespectrum.org/mizer/reference/plotSpectra.html)
for more options.

## See also

Other plotting functions:
[`plot2Productivity()`](https://cmbeese.github.io/mizerReef/reference/plot2Productivity.md),
[`plot2TotalBiomass()`](https://cmbeese.github.io/mizerReef/reference/plot2TotalBiomass.md),
[`plotDegradationScale()`](https://cmbeese.github.io/mizerReef/reference/plotDegradationScale.md),
[`plotProductivity()`](https://cmbeese.github.io/mizerReef/reference/plotProductivity.md),
[`plotProductivityRelative()`](https://cmbeese.github.io/mizerReef/reference/plotProductivityRelative.md),
[`plotRefugeDensity()`](https://cmbeese.github.io/mizerReef/reference/plotRefugeDensity.md),
[`plotRefugeProfile()`](https://cmbeese.github.io/mizerReef/reference/plotRefugeProfile.md),
[`plotRelativeContribution()`](https://cmbeese.github.io/mizerReef/reference/plotRelativeContribution.md),
[`plotTotalAbundance()`](https://cmbeese.github.io/mizerReef/reference/plotTotalAbundance.md),
[`plotTotalBiomass()`](https://cmbeese.github.io/mizerReef/reference/plotTotalBiomass.md),
[`plotTotalBiomassRelative()`](https://cmbeese.github.io/mizerReef/reference/plotTotalBiomassRelative.md),
[`plotVulnerable()`](https://cmbeese.github.io/mizerReef/reference/plotVulnerable.md)
