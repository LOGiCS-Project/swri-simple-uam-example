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
