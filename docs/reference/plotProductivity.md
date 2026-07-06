# Plot the total productivity for each species Group

When called with a MizerParams object the total steady state
productivity is plotted for each group. When called with a MizerSim
object the productivity of each species through time is plotted.

## Usage

``` r
plotProductivity(
  object,
  start_time = NULL,
  end_time = NULL,
  facet = TRUE,
  species = NULL,
  total = TRUE,
  min_fishing_l = NULL,
  max_fishing_l = NULL,
  include_repro = FALSE,
  return_data = FALSE,
  ...
)

plotlyProductivity(object, species = NULL, ...)
```

## Arguments

- object:

  An object of class MizerParams or MizerSim

- start_time:

  The first time to be plotted. Default is the beginning of the time
  series.

- end_time:

  The last time to be plotted. Default is the end of the time series.

- facet:

  A boolean value indicating whether to facet the result plot by species
  group. Defaults to TRUE.

- total:

  A boolean value that determines whether the total productivity from
  all species is plotted as well. Default is TRUE.

- min_fishing_l:

  The minimum length (cm) of fished individuals for productivity
  estimates. Defaults to 7 cm.

- max_fishing_l:

  The maximum length (cm) of fished individuals for productivity
  estimates. Defaults to max length.

- include_repro:

  A boolean value that indicates whether to include energy for
  reproduction in productivity estimates. Defaults to using
  [`getEGrowthTime()`](https://cmbeese.github.io/mizerReef/reference/getEGrowthTime.md)
  if FALSE or mizer's
  [`mizer::getEReproAndGrowth()`](https://sizespectrum.org/mizer/reference/getEReproAndGrowth.html)
  if TRUE.

- return_data:

  A boolean value that determines whether the formatted data used for
  the plot is returned instead of the plot itself. Default value is
  FALSE.

- ...:

  unused

## Value

A ggplot2 object, unless `return_data = TRUE`, in which case a data
frame with the the productivity for each Species Group is returned.

## Potential fisheries productivity

Productivity refers to the rate at which fish biomass is produced and
available for harvest in a given area over a given period of time.
Productivity cannot be measured in situ.

The productivity \\P_i(w)\\ of species group \\i\\ is given by

\$\$P_i(w) = \int_w^{w+dw} \left( N_i(w) + g_i(w) \right) w \\ dw.\$\$

\\N_i(w)\\ is the abundance density \\(no./m^{2})\\ and \\g_i(w)\\ is
the energy rate available for growth after metabolism and movement have
been accounted for \\(grams/year)\\. The productivity is calculated for
all fish in the size range between `min_fishing_length` and
`max_fishing_length`. These lengths can be the same for all groups or
can be specified as a vector with one value for each species in the
model. The minimum length defaults to \\7 cm\\ regardless of species
group and maximum length defaults to the maximum weight in the model.

## See also

[`getEGrowthTime()`](https://cmbeese.github.io/mizerReef/reference/getEGrowthTime.md),[`getProductivity()`](https://cmbeese.github.io/mizerReef/reference/getProductivity.md),
[`plotBiomass()`](https://sizespectrum.org/mizer/reference/plotBiomass.html),
[`plot2TotalBiomass()`](https://cmbeese.github.io/mizerReef/reference/plot2TotalBiomass.md),
[`plotTotalBiomassRelative()`](https://cmbeese.github.io/mizerReef/reference/plotTotalBiomassRelative.md),
`plotProductivity()`,
[`plot2Productivity()`](https://cmbeese.github.io/mizerReef/reference/plot2Productivity.md),
[`plotProductivityRelative()`](https://cmbeese.github.io/mizerReef/reference/plotProductivityRelative.md)

Other plotting functions:
[`plot2Productivity()`](https://cmbeese.github.io/mizerReef/reference/plot2Productivity.md),
[`plot2TotalBiomass()`](https://cmbeese.github.io/mizerReef/reference/plot2TotalBiomass.md),
[`plotDegradationScale()`](https://cmbeese.github.io/mizerReef/reference/plotDegradationScale.md),
[`plotProductivityRelative()`](https://cmbeese.github.io/mizerReef/reference/plotProductivityRelative.md),
[`plotRefugeDensity()`](https://cmbeese.github.io/mizerReef/reference/plotRefugeDensity.md),
[`plotRefugeProfile()`](https://cmbeese.github.io/mizerReef/reference/plotRefugeProfile.md),
[`plotRelativeContribution()`](https://cmbeese.github.io/mizerReef/reference/plotRelativeContribution.md),
[`plotSpectraPercentChange()`](https://cmbeese.github.io/mizerReef/reference/plotSpectraPercentChange.md),
[`plotTotalAbundance()`](https://cmbeese.github.io/mizerReef/reference/plotTotalAbundance.md),
[`plotTotalBiomass()`](https://cmbeese.github.io/mizerReef/reference/plotTotalBiomass.md),
[`plotTotalBiomassRelative()`](https://cmbeese.github.io/mizerReef/reference/plotTotalBiomassRelative.md),
[`plotVulnerable()`](https://cmbeese.github.io/mizerReef/reference/plotVulnerable.md)
