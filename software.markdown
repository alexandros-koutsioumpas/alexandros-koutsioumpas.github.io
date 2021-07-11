---
layout: page
title: Software
permalink: /Software/
---

Here is information about Scientific Software Packages I have developed over the years..

**ANAKLASIS**

[_anaklasis_](https://github.com/alexandros-koutsioumpas/anaklasis) is a set of open-source _Python3_ scripts (with _fortran90_ extensions) that facilitate a range of specular neutron and x-ray reflectivity calculations, involving the generation of theoretical curves and the comparison/fit of interfacial model reflectivity against experimental datasets. 

In the [project repository page](https://github.com/alexandros-koutsioumpas/anaklasis) you may find instructions for installing the package on all major platforms (_Linux_, _macOS_, _Windows_) and also documentation and examples in the form of scripts and _Jupyter_ notebooks.

**MEMPROT**

A program for the data fitting of SEC-SAXS experimental curves of detegent solubilized membrane proteins.

If you use MEMPROT, please cite :
[Pérez, J. and Koutsioubas, A., Acta Cryst. (2015) D71, 86-93](http://dx.doi.org/10.1107/S1399004714016678)

The program can be downloaded from the [Synchrotron SOLEIL website](https://www.synchrotron-soleil.fr/en/beamlines/swing)

**DENFERT**

... a program for the ab initio “dummy-atom” structural modeling of Biological Macromolecules including the contribution of their inherent hydration layer.

version 2.3 (July 2019)
Developed by Alexandros Koutsioumpas and Javier Pérez

If you use DENFERT, please cite :

[A. Koutsioubas & J. Pérez, **Journal of Applied Crystallography** (2013) 46, 1884](http://scripts.iucr.org/cgi-bin/paper?kk5146) and

[A. Koutsioubas, S. Jaksch & J.Pérez, J. (2016). **J. Appl. Cryst.** 49, 690](http://dx.doi.org/10.1107/S1600576716003393)

The version 2.3 of the program can be downloaded from this [link]({{site.baseurl}}/assets/denfert_v2p3.zip).

[User manual download]({{site.baseurl}}/assets/denfert_manual.pdf)

Brief description


DENFERT is implementing a simulated annealing algorithm similar to DAMMIN program by D. Svergun (Biophys. J. 76, 2879-2886) for the restoration of low-resolution structural info of bio-molecules from SAXS and SANS data. The major advantage of DENFERT is that the hydration layer around bio-molecules is taken into account by introducing a second type of beads (hydration beads) in the model.

<img src="{{site.baseurl}}/assets/img-denfert.jpg" alt="avatar" width="100"/>

In the figure above, you may see an example of the shape restoration of Lysozyme from SAXS data using DENFERT. A cartoon representation of the crystallographic structure is also presented for comparison. The bottom figure depicts additionally the hydration layer around the reconstructed protein shape.


**DIONYSIA**

The program can be used for model-free fitting of multiple solvent contrast neutron reflectivity data from experiments performed at the solid/liquid or air/liquid interface. Data input includes, the actual normalised and background subtracted reflectivity curves, and also the scattering length densities (sld) of the substrate and the solvent. No assumptions concerning the form of the interfacial scattering length density profile or its maximum extension (_D_) need to be made. An Indirect Fourier Transform (IFT) method is used for the estimation of _D_, that is later used for bounding the search that is performed by a simulated annealing algorithm for finding an sld and hydration (solvent volume fraction) profile that agrees with the experimental data. For a complete description of the used methodology please refer to the article [Koutsioubas A. Journal of Applied Crystallography (2019) 52, 538](https://doi.org/10.1107/S1600576719003534).

The executables for _macOS_ and _Linux_ together with examples and user manual can be downloaded from this [link](https://doi.org//10.1107/S1600576719003534/kc5089sup1.zip).