# SimpleUAM Example Client

This is a basic example client for [SimpleUAM](https://github.com/LOGiCS-Project/swri-simple-uam-pipeline).

This repo is meant to be read more than used directly.

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

# Troubleshooting

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
