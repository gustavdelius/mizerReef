# Set algae parameters for mizerReef

Set algae parameters for mizerReef

## Usage

``` r
setAlgaeParams(
  params,
  algae_growth_initial = NULL,
  algae_capacity = NULL,
  UR_interaction = NULL,
  use_UR_cc = FALSE,
  algae_colour = "darkseagreen3"
)
```

## Arguments

- params:

  A `MizerParams` object.

- algae_growth_initial:

  Numeric. The initial growth rate of algae in grams/m^2/year. Default
  is 2e3.

- algae_capacity:

  Numeric. Carrying capacity for algae biomass in grams per year.
  Default is 1e4.

- UR_interaction:

  Optional. A named list or array with one or more resource interaction
  vectors (e.g. interaction_algae, interaction_detritus,
  interaction_sponge), each of length equal to the number of species. If
  NULL, will use columns in species_params or set to zero. All values
  must be numeric and between 0 and 1.

- use_UR_cc:

  Logical. Whether to implement a carrying capacity for all unstructured
  resources. Default is FALSE. This flag is stored in the other_params
  slot.

- algae_colour:

  Character. Colour to use for algae in plots. Default is
  "darkseagreen3".

## Value

A `MizerParams` object with updated algae parameters (in `algae_params`
slot).

## Details

All algae-related parameters (growth rate, capacity) are stored in the
`algae_params` slot of the params object. Resource interaction strengths
are set in the species_params data frame. This function supports
flexible multi-resource interaction via the UR_interaction argument.

## Algae as an unstructured resource

     mizerReef supports algae as a non-size-structured resource,
     consumed primarily by herbivorous fish. This function sets
     the initial growth rate, system carrying capacity, and
     interaction strengths for algae, allowing for flexible
     diet preferences.

     The interaction strength (\eqn{\theta_{i,algae}}) for each
     species \eqn{i} determines how strongly that group feeds on
     algae. This can be set via the `interaction_algae` column in
     the species parameter data frame, or directly via the
     `UR_interaction` argument. If neither is provided, all
     interaction strengths are set to zero and a warning is issued.

     The initial growth rate (`algae_growth_initial`) and carrying
     capacity (`algae_capacity`) control the baseline production
     and maximum standing stock of algae, respectively. These values
     may be reset by [reefSteady()] to ensure steady state abundances
     match observed or target values.

     Carrying capacity can be toggled with `use_UR_cc`. When enabled,
     algae biomass will be limited by the specified capacity.

     Note: Interaction with size-structured resources, such as plankton,
     is set with the resource_interaction column of the species parameters
     dataframe.

## Algae consumption

The rate at which herbivorous consumer groups encounter algae biomass
\\E\_{i.A}(w)\\ is controlled by the parameter \\\rho\_{A.i}\\. It
scales with the size of the consumer raised to an allometric exponent
\\m\_{alg}\\ which is taken from empirical data.

\$\$E\_{i.A}(w)=\rho\_{i.A}\\ w^{m\_{alg}}\\B_A\$\$

The mass specific consumption rate then accounts for the preference of
functional group \$i\$ for algae, \\\theta\_{i.A}\\. This gives the
mass-specific algae consumption rate:

\$\$c_A = \sum_i\int\rho\_{i.A}\\ w^{m\_{alg}}
N_i(w)\theta\_{i.A}\\dw\$\$
