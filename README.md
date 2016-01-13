## patgmac-recipes

Recipes for [AutoPkg](http://autopkg.github.io/autopkg/). If you find these useful, please star this repo so I know others are using them.

## Dependencies

Many of my recipes have parents that live in other repos. If you're using Autopkgr, you'll be notified if you're missing a parent. Otherwise, add these repos:

```
autopkg repo-add recipes
autopkg repo-add golbiga-recipes
autopkg repo-add hansen-m-recipes
autopkg repo-add jleggat-recipes
autopkg repo-add scriptingosx-recipes
autopkg repo-add sheagcraig-recipes
autopkg repo-add rtrouton-recipes
autopkg repo-add justinrummel-recipes
autopkg repo-add novaksam-recipes
```

For instructions on getting AutoPkg setup with Absolute Manage, see:
```
https://github.com/tburgin/AbsoluteManageExport  
http://forums.absolute.com/kb.php?a=1062  
```

## VMware Fusion Deploy:  

This recipe creates a mass deployment package of VMware Fusion. Idea for this was borrowed from Nick McSpadden at Facebook. https://github.com/facebook/Recipes-for-AutoPkg.  

You will need to create an override that specifies your volume license serial number and optionally a unique name (such as Company-VMwareFusionDeploy). 
If needed, you could create a separate override if you have more than one VL.  

I will make an Absolute recipe for this soon as well. 