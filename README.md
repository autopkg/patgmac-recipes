## patgmac-recipes

```
ALERT: AbsoluteManageExporter has become LANrevImporter. As part of this move, recipes have been duplicated with the LANrev name/identifier. 
Going forward, please use the LANrev recipes, not Absolute. 
The Absolute recipes will be removed at some point!!

See https://github.com/jbaker10/LANrevImporter/wiki/Switching-from-AbsoluteManageExport-to-LANrevImporter
```

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
autopkg repo-add grahamgilbert-recipes
```

For instructions on getting AutoPkg setup with LANrev, see:
```
https://github.com/jbaker10/LANrevImporter  
 
```

## VMware Fusion Deploy:  

This recipe creates a mass deployment package of VMware Fusion. Idea for this was borrowed from Nick McSpadden at Facebook. https://github.com/facebook/Recipes-for-AutoPkg.  

You will need to create an override that specifies your volume license serial number and optionally a unique name (such as Company-VMwareFusionDeploy). 
If needed, you could create a separate override if you have more than one VL.  

I will make a LANrev recipe for this soon as well. 