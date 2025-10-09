---
title: BaseRaster scan
description: Base classes that facilitated implementing scanning Measurements.
date: 2025-01-01
weight: 100
---

An example can be found by creating a new app using [ScopeFoundry tools](/docs/11_tools-tutorials/1_new-microscope-app/).

## Version 1 vs Version 2

The two versions of these base classes differ in the way movement is defined.

1. The legacy base class is `ScopeFoundry.scanning.BaseRaster2DSlowScan` and requires overriding the following methods:

   - `move_position_slow`
   - `move_position_fast`
   - `move_position_start`


2. The V2 version, `ScopeFoundry.scanning.BaseRaster2DSlowScanV2`, instead requires defining [actuators](/docs/20_built-in-measurements/scanning/sweeping/#actuators) with the settings paths associated with the stage's target position.

   {{% pageinfo color="info" %}}
   BaseRaster2DSlowScan***V2*** released in ScopeFoundry 2.1
   {{% /pageinfo %}}

   
