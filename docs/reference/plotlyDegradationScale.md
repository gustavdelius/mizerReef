# Interactive Plotly version of plotDegradationScale

Returns an interactive heatmap for degradation scaling parameters.

## Usage

``` r
plotlyDegradationScale(
  object = NULL,
  trajectory = NULL,
  return_data = FALSE,
  ...
)
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

A plotly object
