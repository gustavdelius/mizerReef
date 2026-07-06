# Set the parameters for external mortality

Set the parameters for external mortality

## Usage

``` r
setExtMortParams(params, ext_mort_params = NULL)
```

## Arguments

- params:

  A `MizerParams` object.

- ext_mort_params:

  Optional. A named list or matrix with columns/names 'nat_mort',
  'sen_prop', and 'sen_curve'. If NULL, defaults are used. All values
  must be numeric and non-negative.

## Value

A `MizerParams` object with updated external mortality parameters
(stored in `other_params$ext_mort_params`).

## External mortality in mizerReef

     External mortality in mizerReef includes residual natural mortality
     and senescence mortality, representing background sources of death
     not explicitly modeled (e.g., predation, disease, aging). This function
     allows you to set or override the default rates and scaling for these
     processes.

     Residual natural mortality is modeled as an allometric function of body
     size, decreasing with increasing size. Senescence mortality is modeled
     as a power function of relative size, allowing flexible control over
     the rate and scaling of age-related death.

     If no parameters are provided, defaults are used: nat_mort = 0.2,
     sen_prop = 0.1, sen_curve = 0.3. All parameters must be numeric
     and non-negative. The function checks for required columns and
     valid values if a custom parameter set is provided.

## Residual natural mortality

     Residual natural mortality accounts for any external predation or
     fishing mortality that is not explicitly included in the model. It is
     assumed to decrease allometrically with body size. Residual natural
     mortality is a rate with units 1/year given by:

     \deqn{\mu_{nat.i}(w) = \mu_{nat}\, w^{1-n}.}
          {\mu_{nat.i}(w) = \mu_{nat}\, w^{1-n}.}

      Here \eqn{\mu_{nat}} is the residual natural mortality rate at size
      1 g and \eqn{n} is the allometric scaling exponent. In mizerReef,
      these default to \eqn{\mu_{nat} = 0.2} and \eqn{n = 0.75}.

## Senescence mortality

     Senescence mortality \eqn{\mu_{sen.i}(w)} is used to represent
     mortality caused by background sources such as illness or age. The
     rate of senescence mortality (in 1/year) is given by:

     \deqn{\mu_{sen.i}(w) = k_{sen}\left(
                                 \frac{\log_{10}(w)}{\log_{10}(w_{max.i})}
                                 \right)^{p_{sen}}}
          {\mu_{sen.i}(w) = k_{sen}
          (\log_{10}(w)/\log_{10}(w_{max.i}))^{p_{sen}}}

     where \eqn{k_{sen}} is the rate of senescence mortality, \eqn{p_{sen}}
     defines the slope of the senescence curve, \eqn{w_{max.i}} maximum body
     size of group \eqn{i} in grams.
