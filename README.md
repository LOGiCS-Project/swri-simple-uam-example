# SimpleUAM Example Client

This is a basic example client for [SimpleUAM](https://github.com/LOGiCS-Project/swri-simple-uam-pipeline).

This repo is meant as an example to be read and copied into a new project,
rather than as an application to be used directly.

Specifically, your app should batch analysis requests and handle them
asynchronously.

**Do not poll for whether a request is complete outside of testing.**
Blocking and polling for requests is not how SimpleUAM is meant to be used.
Those features are only implemented here to serve as an example for how to
check request status and access zip files in python.
*The result handling code is deliberately bad in order to underscore that
it should not be used in real-world cases.*

## Setup

- Check this repo out *along with its submodules*.
- Follow the instructions [here](https://logics-project.github.io/swri-simple-uam-pipeline/setup/client/)
  to configure your client box so this can run.
- Run `pdm install` in this dir.

## Usage

Basic use is `pdm run example <design-file> <results-dir>`.
This generates info files for the provided design and returns the generated zip
when it appears in the results directory.

Use `pdm run example --help` to see additional arguments and details, including
how to fully process a design with CAD and FDM output.

## Troubleshooting

- This repo is not kept updated with the base SimpleUAM repo.
  If there are errors try checking out the latest version of SimpleUAM with:

  ```bash
  cd simple_uam
  git checkout main
  git pull
  ```

- Sometimes there are issues with `virtualenv` and `pdm` that cause issues with
  packages being detected. Errors like:

  ```bash
  Traceback (most recent call last):
  File "~/suam-example/.venv/bin/example", line 5, in <module>
    from suam_example.cli import main
  File "~/suam-example/suam_example/cli.py", line 10, in <module>
    from simple_uam import direct2cad
  ImportError: cannot import name 'direct2cad' from 'simple_uam' (unknown location)
  ```

  You can fix this by disabling `pdm`'s use of venv with the following:

  ```bash
  pdm config python.use_venv
  pdm install
  ```

  Note that disabling venv like this is *global* and affects all `pdm` projects.
