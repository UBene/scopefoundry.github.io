---
title: CHANGELOG
weight: 100_000
---
### ScopeFoundry 2.1.0 2025-05-30

- Features added:
  - [documentation files] Measurement, HardwareComponent, and BaseMicroscopeApp now include links to their respective documentation files placed in designated folders. If the designated folder does not exist, it will be created. Links are shown on right-click in the tree and the "Help" menu in the app.
  - [dataset_metadata] Metadata such as filename and UUID are now separated from h5_io, allowing them to be reused to save data in different file formats.
  - [measurement] Added a convenience method to open a new h5 file and retrieve dataset_metadata.
  - [logged_quantity] Can now disconnect from QDoubleSpinBox.
  - [scanning] Added version 2 of BaseRasterScans, where stages are defined with lq_paths.
  - [publish_hw] A ScopeFoundry.tool to publish HardwareComponents on GitHub.
  - [LoggedQuantity.change_readonly_on] added. Special listener function. When other_lq changes, LQ will changes its readonly status to func(other_lq.val).

- Fixes:
  - pyqtdarktheme when dark_mode = True is specified in initializer of an app.
  - ScopeFoundry.tools.new_app for Linux. Thanks for M. Gamba for reporting this bug.


### ScopeFoundry 2.0.2 2025-02-14

- Features added:
  - right click on hardware now lists documents that are in the HWs /docs folder


- Fixes:
  - icons now packaged
  - qtconsole installed through conda caused problems. Now it is recomended all dependencies installed in one pip command that lets pip find a set of compatible dependencies.
  - ScopeFoundry.tools.new_hw more stable when tools are called from the app


### ScopeFoundry 2.0.1 2025-01-22

- Fixes:
  - Issue #61 xreload stopped working in python version 3.12: For 3.12+ ScopeFoundry now uses its own modified version of xreload.py. Older version still need to install xreload
  - Critical bugfix: .qss file required was not included in packaging
  - ScopeFoundry.tools.new_app now has access to example hardware

### ScopeFoundry 2.0.0 2025-01-16

- Features added:
  - LQCollection supports dynamical addition and removal of LoggedQuantities
  - LQs can now hold 3 previous and 7 proposed values. Values are proposed when ini files are saved and read from .h5 and .ini files specified by the "inspect file" LQ. Right click on associated widgets  display, and allow user to set those values.
  - settings can be set and inspected from .h5 and .ini files with drag and drop.
  - settings: Can now be dynamical added removed.
  - operations: Can now be dynamical added removed.
  - added a function to generate a tree widget of operations and settings from BaseApp, Measurement and HardwareComponent. The tree widget updates when operations/LQ are added removed.
  - darkmode: better support (in darkmode text is white, so one should not actively set any background to a light color)
  - Measruement.new_start_stop_button convenience method added.
  - `python -m ScopeFoundry.tools` to help build a new setup, new hardware components, new measurements, and generate files to analyze h5 files.
- Fixes:
  - Issue #14 ini loading: no longer stops if failures occured, a report is shown if failures occured.
  - Issue #46 Hardware connect() name mangling with PySide.
  - Issue #57: fixed several cases where displayed values and actual values of settings were not consistent. (checked with unittests).
  - INI file loading of bool lq arrays
  - connected the ui's "about" and "doc" action to launching a webbrowser and displaying readme.md
- Architecture change:
  - Split logged_quantity and base_app into packages.
  - lq_path concept and .ini loading functionality moved from base_microscope_app to base_app.
  - Organized icons
  - More typehints while removing `typing_extension` module dependence and keeping compatibility with python 3.8.
  - `tools` module supersedes `plugin_manager`
  - unittests: various tests added that can be run from a single file
  - Some style is controlled through .qss file.
- Measurement bugfixes:
  - PID controller: plant input can be limited by a min, max values.
  - Sequencer: iterations, wait_until fixed. Better support for dark mode.
- Thanks to Benedikt Ursprung leading this new version!
- Thanks to Mark Hager for a brand new website!


### ScopeFoundry 1.5.0 2024-10-21

- Measurement bugfixes:
  - ranged_optimization: bugfix in "fine" optimization
  - scanning: testing added, start button replacement, test for BaseRaster3DSlowScan added
- INI file handling refactored:
  - MicroscopeBaseApp: Loading .ini file follows now follows logic similar to loading .h5
  - DataBrowser: added support for saving and loading .ini files.
- Improved consistencies:
  - removed unused/duplicate imports
  - replaced os.path dependence with pathlib.Path
- LoggedQuantity dynamic change of choices:
  - unit test added
  - improved consistency of set and displayed value.

### ScopeFoundry 1.4.2 2024-07-03

- Add CI/CD for GitHub to auto-build releases and publish to PyPI

### ScopeFoundry 1.4.1 2024-07-01

- Fixes bug with Data Browser and other sub-package imports (#47)

### ScopeFoundry 1.4.0 2024-03-14

- Thanks to Benedikt Ursprung for lots of useful changes in this version!
- Type Hinting. Note: this means Python < 3.7 no longer is compatible
- Sequencer for building custom measurement flows
- Settings can be protected during INI load with protected flag
- Settings can be loaded from H5 files
- QT6 compatibility
- Dark Mode Option

### ScopeFoundry 1.3.0 2023-09-26

- Updated HDF5 data file format to include a unqiue identifier
- cb32_uuid: a compact time-sortable globally unique identifier


### ScopeFoundry 1.2.3 2023-09-13

- Bug fix for importing of Data Browser


### ScopeFoundry 1.2.2 2023-08-29

- Refactoring of Data Browser, including faster startup


### ScopeFoundry 1.2.1 2023-03-29

- Initial version of Plug-in Manager
- Bug fix: for new QT version, display_update_timer, progressBars in Measurement


### ScopeFoundry 1.2.0 2023-01-03

- Hardware components now have a background thread for updating state
- Reload Code buttons for Hardware and Measurements (uses xreload)
- Data Browser updates
- Add colors to UI elements connected to LoggedQuantities
- Base Raster 3D Scan Measurement
- Raster Scan GUI updates
- Logo and Icon
- Save and Load Window Positions
- Graphics: Zoomable Map
- h5_io: create_extendable_h5_dataset
- Helper Functions: load_qt_ui_from_pkg, auto_connect_widget_in_ui
- Bug Fix: Jupyter qtconsole works with python 3.8
- Bug Fix: Measurement threading issues


### ScopeFoundry 1.1.1 2018-08-14

- Bug Fix: QtConsole creates alerts instead of writing to console on Windows

### ScopeFoundry 1.1.0 2018-07-24

- App level logging enabled by default
- Hardware:
- Thread locking at HardwareComponent level
- Connection LQ handles failed attempts at connecting
to hardware
- LoggedQuantity:
- LQ Math and LQ follower functions
- new_default_widget method
- Measurements:
- Nested Measurements: start_nested_measure_and_wait
- activation setting starts and stops measurement
- Scanning:
- Bug fixes to raster scan and UI updates
- Allows ScopeFoundry App operation in Jupyter / IPython notebooks


### ScopeFoundry 1.0.0 2017-09-12

- Initial PyPI release


