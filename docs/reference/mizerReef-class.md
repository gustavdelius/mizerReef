# S4 marker class for mizerReef extension

A formal S4 class that extends
[MizerParams](https://sizespectrum.org/mizer/reference/MizerParams.html)
but adds no new slots. All reef-specific state (refuge, algae, detritus
parameters) lives in `other_params(params)`. The class label enables S3
dispatch of mizer generics to mizerReef-specific methods.

## See also

[MizerParams](https://sizespectrum.org/mizer/reference/MizerParams.html),
[`newReefParams()`](https://cmbeese.github.io/mizerReef/reference/newReefParams.md)
