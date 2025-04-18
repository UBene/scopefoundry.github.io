---
title: Sharing hardware components
description: Publish your shiny new plugin as a ScopeFoundryHW plug-in on GitHub. 
weight: 22
---

The following instructions publish   `company_model`  in your_project_folder's `ScopeFoundryHW` 

```
├── your_project_folder
   ├── ScopeFoundryHW
      ├── company_model
         ├── company_model_hw.py					
         ├── Licence
         ├── README.md
         # optional
         ├── company_model_dev.py			
         ├── company_model_test_app.py
         ├── .gitignore
         ├── docs
            ├── links.json 
         ├── ** more files/directory that make your hw component work
         
    **
```

with a recommended `.gitignore` as we generally do not recommend to track measurement and log data:

```.gitignore
# .gitignore
*.pyc
*.h5
*log*.txt
```

If you like to adhere to this [template use ScopeFoundry.tools](/docs/11_tools-tutorials/2_hardware-1/#the-template) to generate the folder structure.

## Publish your hardware

1. Initialize git repositiory localy (`cd ScopeFoundryHW/{company_model}`)

   ```sh
   git init --initial-branch=main
   ```
   
2. Commit your code. If it is the first commit, assuming you commit all at once:

   ```sh
   git add -A && git commit -m "Initial release"
   ```

3. Create the target repo on GitHub by prepending `HW_` to the package:

   1. sign-up/log-on on GitHub with your `USER_NAME` 
   2. New (repository) to make a public repo named `HW_{company_model}`
      ![create_repo](create_repo.png)
   3. note the repo url for the next step![repo_created](repo_created.png)


4. Push your code to the remote repo

   ```sh
   git remote add origin https://github.com/{USER_NAME}/HW_{company_model}.git
   git branch -M main
   git push -u origin main
   ```

#### Discoverable on this page

This page periodically crawls GitHub for HW_* repos. Thereby, it considers users/organisations that forked the ScopeFoundry Repo. So this page will find your hw repo if 

- you fork [ScopeFoundry/Scopefoundry](https://github.com/ScopeFoundry/ScopeFoundry)
- Indeed label your Hardware repo starting with `HW_`



## Adding published plug-ins to your project

Assuming:

- urls `https://github.com/{THEIR_USER_NAME}/HW_{company_model}.git`
- `cd to/your_project_folder/` and use the following cmd (requires [git](/docs/100_development/20_git/))

```sh
git clone https://github.com/{THEIR_USER_NAME}/HW_{company_model}.git ScopeFoundryHW/{company_model}
```

Note: We removed the prepended `HW_` in the target folder name.

If you are planning to share changes you make to this code then it is wise to first fork the code and clone the fork  (see bellow).


HINT: The entries of [reference/hw-components](/docs/300_reference/hw-components/) contain this line filled out. 



## Updating already published plug-ins

If it is **not** your repo or you do **not** have write access:

- Sign up/log in github with your  `USER_NAME`
- fork the original github repo

Now you should have github repository url of the form: `https://github.com/{USER_NAME}/HW_{company_model}.git`  Here we push to the branch `master`.

1. go the folder you of the hardware
   ```sh
   cd to/your_project_folder/ScopeFoundryHW/{company_model}
   ```

2. Commit your code. To wrap all changes in one commit (not necessarily recommended)
   ```sh
   git add -A && git commit -m "describe your contribution"
   ```

4. Push your code to the remote repo
   ```sh
   git remote add origin https://github.com/{USER_NAME}/HW_{company_model}.git
   git push -u origin
   ```

If you'd like to share your updates with the original owner, then create a Pull Request on GitHub and they can decide to include it.
