# Castoro sources

The glyph design sources are in FontLab 7 .vfj format. These sources also contain the classes and kerning data used in the OpenType Layout GPOS table, and the GSUB code in .fea format.

The OpenType Layout for the Castoro fonts was initially developed in Microsoft‘s Visual OpenType Layout Tool .vtp format, then converted to .fea syntax using our [Volto](https://github.com/TiroTypeworks/Volto) conversion tool, and integrated into the FontLab 7 .vfj sources. As of version 1.10 (build 002), the .vfj files should be considered the source for OTL, and the previously available .vtp files have been removed from the repo.

The build process described below uses UFO input sources, which can be exported from FontLab 7. So the overall toolchain for editing and generating new fonts is:

* FontLab
* UFO
* build script

Note that the .designspace files in the UFO folder are not as exported from FontLab, and should not be overwritten.


## Building the Fonts

The fonts are built using fontmake and post-processed with gftools scripts. The tools are all Python based. 

First, install the tools into a python3 virtual environment in the Castoro folder:


```
# Create a new virtualenv
python3 -m venv venv
# Activate env
source venv/bin/activate
# Install dependencies
pip install -r requirements.txt
```

Then from the src folder run the build script in the terminal:

```
cd src
sh build.sh
```
