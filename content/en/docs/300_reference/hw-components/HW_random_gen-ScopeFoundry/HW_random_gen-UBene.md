
---
title: HW_random_gen (UBene)
description: No description available.
weight: 54
---
- [GitHub Repository](https://github.com/UBene/HW_random_gen)
- Last Updated: 2017-01-23T22:17:34Z
- Forked from [HW_random_gen (ScopeFoundry)](/docs/300_reference/hw-components/hw_random_gen-scopefoundry)

#### To add to your app:

`cd to/your_project_folder/ScopeFoundryHW` and use the following cmd (requires [git](/docs/100_development/20_git/))

```bash
mkdir random_gen && cd random_gen && git init --initial-branch=master && git remote add upstream_UBene https://github.com/UBene/HW_random_gen && git pull upstream_UBene master && cd ..
```

*or* fork on GitHub **and** use your adjusted cmd:

```bash
mkdir random_gen && cd random_gen && git init --initial-branch=master && git remote add origin https://github.com/YOUR_GH_ACC/HW_random_gen && git pull origin master && cd ..
```

## Readme
ScopeFoundryHW.random_gen
===========================

ScopeFoundry hardware plug-in example that presents a random number
generator as a hardware device

ScopeFoundry is a Python platform for controlling custom laboratory 
experiments and visualizing scientific data

<http://www.scopefoundry.org>

This software is not made by or endorsed by the device manufacturer


Author
----------

Edward S. Barnard <esbarnard@lbl.gov> and Alan Buckley


Requirements
------------

	* ScopeFoundry
	* numpy
