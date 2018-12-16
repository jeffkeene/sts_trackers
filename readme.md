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
1. Add project Eclipse Oomph setups from git://git.eclipse.org/gitroot/oomph/org.eclipse.oomph.git
1. Open /setups/org.eclipse.setup in Oomph setup editor
1. Navigate to platform:/resource/setups/org.eclipse.setup (usually first entry)
1. Expand child Eclipse
1. Expand child <Self Products>
1. Locate current STS installation as child of <Self Products>
1. Locate specific version of STS installation as child of previous node
1. Create new general project
1. Add an Oomph product setup file to new project.
1. Copy the STS version node, the grand-child of <Self Products>, into to the new product setup, as child of top node
 - This copy can be done from single window mode, but may be easier the first few times as drag and drop in multi-window mode 
1. Remove download locations from P2 Director that reference a specifically numbered nightly build location.  At eclipse.org these age out quickly.
1. Test an installation using the Eclipse Installer, pointing at the new setup 

There is probably an easier way to get the Self Product model than this, seems a bit round Robin Hood's Barn the way I did it.
