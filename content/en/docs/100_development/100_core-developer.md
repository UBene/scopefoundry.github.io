---
title: core developer
description: Become a ScopeFoundry core developer
weight: 100
---

If you would like to have a local copy of ScopeFoundry to modify within your microscope repository, we recommend to make a local copy. (`cd to/your_project_folder`)

```sh
git clone https://github.com/ScopeFoundry/ScopeFoundry.git
```

Then your tree should look like:

```
├── your_project_folder
	├── ScopeFoundry/			# Local Sub-tree of ScopeFoundry (overrides pip installed scopefoundry)
	    └── ...
	├── ScopeFoundryHW/ 			# Local copies of ScopeFoundry hardware plugins
	    ├── virtual_function_gen/		# Local sub-tree of specific hardware plugin
	    └── ...
	├── fancy_app.py
	# optional
	├── .git/				# Stores Git repository information of your project (not ScopeFoundry)
	    └── ...
```

If you want to make contributions to the ScopeFoundry project:

1. fork on GitHub

2. `cd to/your_project_folder/ScopeFoundry`

   ``` bash
   git remote add https://github.com/{YOUR_USER_NAME}/ScopeFoundry.git
   ```

3. create a pull request on GitHub.



