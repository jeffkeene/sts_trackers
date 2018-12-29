# Summary

A tracker for Spring Tool Suite configurations as Oomph models.  Can be used as a starting point for local customizations.

# Details

Human tracked, there will be some lag in this project after an update of STS.

## Reading materials
- http://thecodingflow.com/?p=50
- https://projects.eclipse.org/projects/tools.oomph
- https://git.eclipse.org/c/oomph/org.eclipse.oomph.git/tree/setups
- https://github.com/ftl/ft.oomph.mysetup
- https://stackoverflow.com/questions/40179789/how-do-i-add-a-plugin-to-an-oomph-product-setup?rq=1

## How it was done.

1. Manually install latest STS
1. Add Oomph feature using Install New Software feature
1. In Window->Preferences, Oomph->Setup Tasks->Preference Recorder, check "Record into:" for value User, then use icon to "open recorder target file" (provides an editor on user.setup)
1. Navigate to index:/org.eclipse.setup (usually second entry, after user:/user.setup)
1. Expand child Eclipse
1. Expand child <Self Products>
1. Locate current STS installation as child of \<Self Products\>
1. Locate specific version of STS installation as child of previous node
1. Create new general project
1. Add an Oomph product setup file to new project.
1. Copy the STS version node, the grand-child of \<Self Products\>, into to the new product setup, as child of top node.  This copy can be done from single window mode, but may be easier the first few times as drag and drop in multi-window mode 
1. Remove download locations from P2 Director that reference a specifically numbered nightly build location.  At eclipse.org these age out quickly.
1. Test an installation using the Eclipse Installer, pointing at the new setup 

# How to use this model

## Summary

Install one copy of the STS you want, copy part of the installation out to a common fileshare, then give that location out as the location for the repo variable during other installations

## Details

1. Install a full STS kit once.
1. Locate the Default.profile inside that installation, looks something like
 - file:/G:/Programs/sts-4.1.0.RELEASE/configuration/../p2/org.eclipse.equinox.p2.engine/profileRegistry/DefaultProfile.profile
1. Copy the full contents from back at the /p2/ node to a common location your team can reach from a 'file:/' qualifier
1. Use the Eclipse Installer, in Advanced Mode, giving this STS.setup as a user product
1. On the prompt for variables, in for sts-repo-?, give the common path to the p2 Default.profile you created above