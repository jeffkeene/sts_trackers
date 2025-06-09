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
- https://github.com/nittka/oomph-playground

## How it was done

1. Manually install latest STS
1. Add Oomph feature using Install New Software feature
1. In Navigate->Open Setup, select <Self Products>... node, which should be current version of STS
1. Locate current STS installation as child of \<Self Products\>
1. Locate specific version of STS installation as child of previous node
1. Create new general project
1. Add an Oomph product setup file to new project
1. Copy the STS version node, the grand-child of \<Self Products\>, into to the new product setup, as child of top node.  This copy can be done from single window mode, but may be easier the first few times as drag and drop in multi-window mode
1. Edit the properties of the copied node, to have a name of 'x.y.z-RELEASE', instead of 'version' 
1. Add an attribute for `requiredJavaVersion="21"` to the `<version>` element of the copied node
1. Remove download locations from P2 Director that reference a specifically numbered nightly build location.  At eclipse.org these age out quickly.
1. Test an installation using the Eclipse Installer, pointing at the new setup 

# How to use this model

## Summary

Copy the STS.setup file locally, install the Eclipse Installer, point it at the setup file and run.

## Details

1. Install the Eclipse Installer
1. Set it to Advanced Mode, where you can specify custom catalogs (plus sign on upper right, near filter box)
1. Add this STS.setup file
1. Select the Eclipse product version you want to install
1. Run, accepting all certificate signers and licenses
