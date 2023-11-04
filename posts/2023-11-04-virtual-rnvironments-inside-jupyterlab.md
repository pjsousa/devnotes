---
title: Virtual Rnvironments Inside JupyterLab
description: How to spin a local jupyter lab server and have it use a virtual environment
date: 2023-11-04T05:55:50.695Z
preview: ""
draft: false
tags:
    - jupyter
    - venv
categories: []
slug: virtual-rnvironments-jupyterlab
keywords:
    - jupyter
    - venv# 
---


## Hey jupyter, where's my venv?

If you want to use a venv inside jupyter lab and are just `source venv/bin/activate`ing it before launching jupyter, you'll notice that your console tabs will see the venv, but the notebooks themselves will not.

## Kernels to the rescue!

You'll just need to create a kernel to use the venv, or any set of venv's you want.

1) After creating the virtual environment

``` bash
python3 -m venv venv
```

2) Activate it
``` bash
source venv/bin/activate
```

3) Install ipykernel
``` bash
pip install ipykernel
```

4) Add the venv to Jupyter Kernels

``` bash
python -m ipykernel install --user --name=<venv name>
```

5) Restart Jupyter Lab


6) Use it. Open a notebook, go to "Kernel" tab and select the kernel you just created. You can set a kernel as default for all notebooks or create a new kernel for as many use cases as you'd like

