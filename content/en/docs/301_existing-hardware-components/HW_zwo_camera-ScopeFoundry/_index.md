
---
title: HW_zwo_camera (ScopeFoundry)
description: ASI ZWO Astronomy Camera ScopeFoundry Hardware Component
weight: 51
---
- [GitHub Repository](https://github.com/ScopeFoundry/HW_zwo_camera)
- Last Updated: 2024-08-12T00:35:51Z


#### To add to your app:

`cd to/your_project_folder/` and use the following cmd (requires [git](/docs/100_development-environment/20_git/))

```bash
git clone https://github.com/ScopeFoundry/HW_zwo_camera ScopeFoundryHW/zwo_camera
```


## Readme


uses the python-zwoasi python library and SDK from ZWO

https://github.com/python-zwoasi/python-zwoasi
zwoasi-0.1.0.1-py2.py3-none-any.whl

	pip install zwoasi

On MacOS, the default security settings prevent the SDK library from being accessed

xattr -d com.apple.quarantine ScopeFoundryHW/zwo_camera/ASI_linux_mac_SDK_V1.22/lib/mac/libASICamera2.dylib.1.22 

You must also have libusb installed (homebrew works):
	brew install libusb 


