# RStudio JupyterHub Integration in Euler Setup

This repository contains scripts and configurations designed to customize RStudio within a JupyterHub environment hosted on the Euler computing infrastructure at ETH Zürich. The primary goal is to equip users with CLI tools that enable them to modify the default configuration of RStudio to better suit their project needs.

For instance, users can select a specific RStudio container and the R version that aligns with their project requirements.

To facilitate these customizations, I have developed two main scripts: `rstudio_config` and `rstudio_log_level`.

### rstudio_config

The `rstudio_config` script allows users to set environment variables required by JupyterHub in the Euler cluster:

```bash
RSTUDIO_IMAGE
RSTUDIO_TAG
R_LIBS_USER
RSTUDIO_EXTRA_PARAMS
RSTUDIO_SINGULARITY_EXTRA_PARAMS
```

Executing this script creates or modifies the `$HOME/.config_r_studio` file, which is then sourced by the JupyterHub Spawner to apply the specified configurations.

### rstudio_log_level

The `rstudio_log_level` script enables users to adjust the log level within `$HOME/.rstudio/logging.conf`. By default, RStudio logs at the `debug` level, which can generate an excessive number of warnings. This script allows for the log level to be customized, potentially reducing the verbosity of log output.

## Acknowledgments

- Thanks to the Euler cluster team at ETH Zürich for their support and for providing the necessary infrastructure.
- Special thanks to Loic Hausammann for his role in integrating JupyterHub with the Euler cluster.
