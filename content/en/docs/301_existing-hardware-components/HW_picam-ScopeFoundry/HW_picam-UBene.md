
---
title: HW_picam (UBene)
description: ScopeFoundry hardware plug-in to control PICAM-based Princeton Instruments Cameras
weight: 57
---
- [GitHub Repository](https://github.com/UBene/HW_picam)
- Last Updated: 2025-02-13T11:58:50Z
- Forked from [HW_picam (ScopeFoundry)](/docs/301_existing-hardware-components/hw_picam-scopefoundry)

#### To add to your app:

`cd to/your_project_folder/` and use the following cmd (requires [git](/docs/100_development-environment/20_git/))

```bash
git clone https://github.com/UBene/HW_picam ScopeFoundryHW/picam
```


## Readme
ScopeFoundryHW.picam
===================================

ScopeFoundry hardware plug-in to control PICAM based Princeton Instruments
Cameras. Tested on a PI PIXIS camera.

ScopeFoundry is a Python platform for controlling custom laboratory 
experiments and visualizing scientific data

<http://www.scopefoundry.org>

This software is not made by or endorsed by the device manufacturer


Author
----------

Edward S. Barnard <esbarnard@lbl.gov>


Requirements
------------

	* ScopeFoundry
	* numpy
	* PICAM DLL
	
	
History
--------

### 0.1.0	2020-08-04	Initial public release.

Plug-in has been used internally and has been stable.
Check Git repository for detailed history. Tested on PI PIXIS CCD.

### 0.2.0	2020-08-04	Connect to multiple cameras

Tested with PI EMCCD, PI Pylon

