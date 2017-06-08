# nustar_axions
Test repo for nustar axion analysis

---
# Contents:

This has some python scripts that show the data formats of the source, background, and response files that we can expect from our NuSTAR solar axion work.

For this test, I've done the following:

- Filter on GTIs for the following time range:
2017-03-21T15:22:50 2017-03-21T15:34:22

- Use `nuproducts` to produce a source spectrum and associated response files using this GTI file an input (keyword usrgtifile in the `nuproducts` call).

- Use [nuskybgd](https://github.com/NuSTAR/nuskybgd) to produce a simulated background spectrum. I've followed the ABC guide, with the exception that instead of fitting the background I've taken the normalization parameters from a different observation for the internal continuum / lines / aperture CXB components and zereo'd out the contribution from the "solar" parts of the background and the focused CXB component.

- I produced the background using the /perfect keyword (no Poisson fluctuations on the background count rate) and by increasing the background exposure by a factor of 1e6 to ensure that the background is properly sampled. This should give a "smooth" background curve that can be used for simulations and maximum likelihood analysis methods.

- Check out [Juypyter Notebook](SolarDataExamples.ipynb) that shows how to handle the various data formats.

