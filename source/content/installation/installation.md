# Installation

Brightway is a Python software package. A user interface [is available](./ui.md), but not necessary for use. Brightway can be installed using the [Python package installer `pip`](https://pypi.org/project/pip/) or the [multi-language package management system `conda`](https://docs.conda.io/en/latest/). This guide uses `conda`.

```{note}
Brightway supports Python 2 and 3 (>3.4). However, we recommend you use Python 3. 
```

## Installing Brightway Locally

```{admonition} Prerequisites
:class: important
1. A working installation of [Conda](https://docs.conda.io/en/latest/)
2. Basic knowledge of [Conda environments](https://docs.conda.io/projects/conda/en/latest/user-guide/tasks/manage-environments.html)
3. Basic knowledge of [the difference between `brightway2` and `brightway 25`](../faq/brightway.md)
```

::::{tab-set}

:::{tab-item} Linux or macOS (x64)

```{note}
Brightway runs natively on Unix (x64) systems, including Linux distributions and macOS.
```

1. Create a new Conda environment (in this example named `bw`):

```
conda create -n bw -c cmutel brightway25 jupyterlab
```

2. Activate the environment:

```
conda activate bw
```

:::

:::{tab-item} Windows (x64)

```{note}
Brightway runs natively on Windows (x64) systems, including Windows 7-11.
```

1. Create a new Conda environment (in this example named `bw`):

```
conda create -n bw -c cmutel brightway25 jupyterlab
```

2. Activate the environment:

```
conda activate bw
```

3. Install `pywin32`:

```
conda install pywin32
```

:::

:::{tab-item} macOS (Apple Silicon/ARM)

```{note}
Brightway runs on the new Apple Silicon ARM architecture. However, the super-fast linear algebra software library `pypardiso` is not compatible with the ARM processor architecture. To avoid critical errors during instruction that would break core functionality, a different version of Brightway (`brightway_nosolver`) must be installed, which includes a different linear algebra software library (`scikit-umfpack`).
```

1. Create a new Conda environment (in this example named `bw`):

```
conda create -n bw -c cmutel -c conda-forge brightway25_nosolver jupyterlab scikit-umfpack
```

2. Activate the environment:

```
conda activate bw
```

::::

## Updating Brightway

Brightway is being actively developed, with frequent new releases. To update Brightway:

``` bash
conda update conda
conda update -c cmutel brightway25
```

```{warning}
Newer versions of Brightway can introduce breaking changes. We recommend you create a new Conda environment for each project, and only update Brightway when you are ready to update your project.
```

```{toctree}
---
hidden:
maxdepth: 2
---
self
upgrading
ui
cloud
docker
```
