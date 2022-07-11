# SEGY2NUMPY
# How to convert segy file to numpy format.

This readme is provided for helping computer sciense or geo-science researchers quickly convert segy seismic dataset to python friendly numpy format. By converting segy to numpy, many machine learning/deep learning assited seismic interpretation code can use directly on them.
Hope this can save you the months I spend on this issue. 

A actual usecase can be found in paper "A Gigabyte Interpreted Seismic Dataset for Automatic Fault Recognition"
The code and the dataset generated can be found in dataset repo: https://dataverse.harvard.edu/dataset.xhtml?persistentId=doi:10.7910/DVN/YBYGBK
Thanks in advance if you cite this paper.

## Package required:
python,
numpy,
obspy.

When I try to read segy file, I found that many segy file store their inline number, crossline number in random place. You need first check the file header to carefully read the position where it is stored. For instance, some store the inline number at the 4-8 bytes of the trace header, while the opunake3d dataset store it in the 196-200 bytes.
Once you identified the byte location of the inline number and crossline number. You can retrive these using the folloing obspy offical header convertion file. In this package, they provide name for the bytes in the trace header. You can check the obspy's byte name using this file.
https://github.com/obspy/obspy/blob/master/obspy/io/segy/header.py

Hope this helps. 
You can also check my example code. 

Good luck with the convertion.
