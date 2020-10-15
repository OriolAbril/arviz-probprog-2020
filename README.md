# Backend agnostic exploratory analysis of Bayesian models
Poster about ArviZ to presented at PROBPROG 2020. The poster highlights and summarized the content of this repository.

## Presentation outline
The presentation starts enumerating some of the steps of the Bayesian modeling
workflow. ArviZ aims to help make all these tasks accessible by focusing on
the steps of the workflow that tend to lie outside the scope of probabilistic
programming languages (PPLs).

![workflow](https://raw.githubusercontent.com/arviz-devs/arviz_misc/master/stancon_2020/img/Bayesian_workflow_Updated.png)

To do so, it proposes a common data structure: `InferenceData`. By converting
the data from virtually any PPL to `InferenceData`, ArviZ aims to facilitate
the sharing and reproducing of results while allowing all its visualization
and statistical codebase to be completely backend agnostic.

### `InferenceData` creation
We will first create and run 3 implementations of the same model using different PPLs
(click or scan the QR to see the model implementation):

| PyMC3 | PyStan | Soss |
|---|---|---|
| [![qr][pymc qr]][pymc example] | [![qr][pystan qr]][pystan example] | [![qr][soss qr]][soss example] |
| [PyMC3 docs](https://docs.pymc.io/) | [PyStan docs](https://pystan.readthedocs.io/en/latest/) | [Soss docs](https://cscherrer.github.io/Soss.jl/stable/) |

Each example reads the data from a JSON file and implements the same model,
using the same naming convention. After forwards and backwards sampling, the
results are stored as `InferenceData`.

All 3 resulting `InferenceData` objects have then been published on [figshare](https://figshare.com/authors/Oriol_Abril_Pla/8786540)

### Exploratory analysis of the model
Once we have generated our data, we will demonstrate ArviZ statistical and
visualization capabilities while showing it is indeed backend agnostic. The
data used will be any of the generated `InferenceData`, chosen at random.
Independently of the file loaded, all the plots and stats functions will work
correctly.

All this is done in a [single notebook](https://nbviewer.jupyter.org/github/OriolAbril/arviz-probprog-2020/blob/master/eabm.ipynb), from which some plots have been
used in the poster.





[pymc qr]: https://raw.githubusercontent.com/OriolAbril/arviz-probprog-2020/master/img/pymc3_qr.png
[pymc example]: https://nbviewer.jupyter.org/github/OriolAbril/arviz-probprog-2020/blob/master/models/pymc3.ipynb
[pystan qr]: https://raw.githubusercontent.com/OriolAbril/arviz-probprog-2020/master/img/pystan_qr.png
[pystan example]: https://nbviewer.jupyter.org/github/OriolAbril/arviz-probprog-2020/blob/master/models/pystan.ipynb
[soss qr]: https://raw.githubusercontent.com/OriolAbril/arviz-probprog-2020/master/img/soss_qr.png
[soss example]: https://nbviewer.jupyter.org/github/OriolAbril/arviz-probprog-2020/blob/master/models/soss.ipynb
