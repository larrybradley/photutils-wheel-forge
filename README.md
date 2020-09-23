## A pipeline for building wheels for Photutils

[![Build Status](https://dev.azure.com/larrybradley/photutils-wheel-forge/_apis/build/status/larrybradley.photutils-wheel-forge?branchName=master)](https://dev.azure.com/larrybradley/photutils-wheel-forge/_build?definitionId=4)

After releasing a new Photutils version, update
[autowheel.yml](https://github.com/larrybradley/photutils-wheel-forge/blob/master/autowheel.yml)
with the package version, python versions, and
minimum numpy version. After pushing the changes, Azure Pipelines will
automatically start to build the wheels.

To manually build the wheels, go to the
[Azure build](https://dev.azure.com/larrybradley/photutils-wheel-forge/_build/)
, click on ``larrybradley.photutils-wheel-forge``, then click "Run
pipeline", and then click "Run".

Once the builds are complete, download the wheels by running:

    python get_wheels.py

Then upload the wheels to PyPI with `twine`:

    twine upload wheelhouse/*.whl
