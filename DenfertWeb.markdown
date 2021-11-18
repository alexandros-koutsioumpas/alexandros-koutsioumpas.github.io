---
layout: page
title: Denfert WebServer
permalink: /Denfert/
exclude: true
---

The site provides a simplified and convenient way for performing ab-initio low-resolution shape reconstructions of monodisperse non-interacting biological molecules (proteins, nucleic acids) in dilute solutions from SAXS or SANS data, where the hydration layer contribution to the scattering is taken into account. All you need to provide is the ASCII data of your solution scattering experiment, the parameters related to the contrast of the biomolecules, and the instrumental resolution (for SANS). Optionally you may provide an estimation of the maximum diameter of the particle (_Dmax_) and you may also limit the momentum transfer range (_Qmax_) that will be fitted. Scroll at the end of the page for details and hints related to data input.

<img src="{{site.baseurl}}/assets/img-denfert.jpg" alt="avatar" width="100"/>

The initial Indirect Fourier Transform (IFT) of the data is performed using the method of Bayesian estimation of hyperparameters, see:

[Hansen J.Appl. Cryst (2000) 33, 1415](https://doi.org/10.1107/S0021889800012930)

Shape reconstruction is performed with the program DENFERT v 2.3 described in the following two publications:

[Koutsioubas & Perez J. Appl. Cryst. (2013) 46, 1884](https://onlinelibrary.wiley.com/doi/10.1107/S0021889813025387) and [Koutsioubas et al. J. Appl. Cryst. (2016) 49, 690](https://onlinelibrary.wiley.com/doi/10.1107/S1600576716003393)

If you need to control more parameters of the reconstruction procedure, please use the [binary version]({{site.baseurl}}/assets/denfert_v2p3.zip) of the program on your local machine. A complete manual with examples for the use of the program can be found [here]({{site.baseurl}}/assets/denfert_manual.pdf).

___

**Note that you need to register as a user of the webserver by sending an email to [denfertweb@gmail.com](mailto:denfertweb@gmail.com?subject=denfert%20registration) with the subject "denfert registration" and optionally including your name and affiliation in the message body. You will receive a verification message after a while.**

___
### Parameter Input (X-rays)
<script type="text/javascript">
	function shrinktext() {
	var size = document.getElementById("sdata").value.length;
	var s=Math.ceil(size/32000);
	var string=document.getElementById("sdata").value;
	var lines = string.split('\n');
	var out="";
	//debugger;
	for(var i = 0;i < lines.length;i=i+s){
		out=out+lines[i]+'\n';
}
	document.getElementById("sdata").value=out;
	return True;
}
</script>

<script type="text/javascript">var submitted=false;</script>
<iframe name="hidden_iframe" id="hidden_iframe" style="display:none;" onload="if(submitted)  {window.location='{{site.baseurl}}/assets/webdenfert_submit_message.html';}"></iframe>

<form class="form" action="https://docs.google.com/forms/u/0/d/e/1FAIpQLSczpgW4aGnE2KZiQXMzhmyOHA0ixjF_xZ3B0qTXlUlFh8pqVw/formResponse" method="POST" target="hidden_iframe"
    onsubmit="submitted=true;">


<p> <label>Email</label>
<input name="entry.2107985966" required size="40" type="email" /> <small> Important! your address shoud be registered (see above) </small> </p>

<p> <label>Project name</label>
<input name="entry.896354957" required size="30" type="text" maxlength="30" /> <small> only alphanumeric characters (keep it simple) </small> </p>

<p> paste ASCII scattering data (exclude any negative intensity values!)</p>
<p> <textarea name="entry.2117040675" id="sdata" required type="text" rows = "5" cols = "80"></textarea> </p>

<p> momentum transfer (Q) in <input type="radio" name="entry.493766941" required value="angstrom" checked="checked"> (1/Angstrom) <input type="radio" name="entry.493766941" value="nm"> (1/nm) units <br> </p> 

(optional) maximum momentum transfer Qmax <input type="text" name="entry.1483736366" value="" size="5"> <small>(in the same units (1/Angstrom or 1/nm) as for Q)</small><br>
  
(optional) maximum diameter Dmax <input type="text" name="entry.184211383" value="" size="5"> <small>(in the same inverse units (Angstrom or nm) as for Q)</small><br>
  
particle electron density (e/Angstrom^3):  <input type="text" name="entry.405121486" required value="0.44" size="5"> <small>(default value for proteins)</small><br>

solvent electron density (e/Angstrom^3):  <input type="text" name="entry.474174320" required value="0.334" size="5"><small>(default value for H2O)</small><br>

<p> <input type="radio" name="entry.1033017014" required value="large" checked="checked"> large beads <small> (faster reconstruction)</small>  <input type="radio" name="entry.1033017014" value="small"> small beads <small>(slower reconstruction)</small> <br> </p> 

<input type="submit" value="start reconstruction from SAXS data" onclick="shrinktext();" />

</form>
___
---
---

### Parameter Input (neutrons)
<script type="text/javascript">
	function shrinktextB() {
	var size = document.getElementById("sdataB").value.length;
	var s=Math.ceil(size/32000);
	var string=document.getElementById("sdataB").value;
	var lines = string.split('\n');
	var out="";
	//debugger;
	for(var i = 0;i < lines.length;i=i+s){
		out=out+lines[i]+'\n';
}
	document.getElementById("sdataB").value=out;
	return True;
}
</script>

<script type="text/javascript">var submitted=false;</script>
<iframe name="hidden_iframe" id="hidden_iframe" style="display:none;" onload="if(submitted)  {window.location='{{site.baseurl}}/assets/webdenfert_submit_message.html';}"></iframe>

<form class="form" action="https://docs.google.com/forms/u/0/d/e/1FAIpQLSczpgW4aGnE2KZiQXMzhmyOHA0ixjF_xZ3B0qTXlUlFh8pqVw/formResponse" method="POST" target="hidden_iframe"
    onsubmit="submitted=true;">


<p> <label>Email</label>
<input name="entry.2107985966" required size="40" type="email" /> <small> Important! your address shoud be registered (see above) </small> </p>

<p> <label>Project name</label>
<input name="entry.896354957" required size="30" type="text" maxlength="30" /> <small> only alphanumeric characters (keep it simple) </small> </p>

<p> paste ASCII scattering data (exclude any negative intensity values!) </p>
<p> <textarea name="entry.2117040675" id="sdataB" required type="text" rows = "5" cols = "80"></textarea> </p>

<p> momentum transfer (Q) in <input type="radio" name="entry.493766941" required value="angstrom" checked="checked"> (1/Angstrom) <input type="radio" name="entry.493766941" value="nm"> (1/nm) units <br> </p> 

<p> beam wavelength (Angstrom):  <input type="text" name="entry.2112607829" required id="num1" value="6" size="2"><br>
wavelength spread (%):  <input type="text" name="entry.210238414" required id="num1" value="10" size="3"><br>
divergence (radians):  <input type="text" name="entry.2072205536" required id="num1" value="0.002" size="8"><br>
<small>(Default values represent typical collimation settings at a neutron diffractometer)</small><br> </p>

(optional) maximum momentum transfer Qmax <input type="text" name="entry.1483736366" value="" size="5"> <small>(in the same units (1/Angstrom or 1/nm) as for Q)</small><br>
  
(optional) maximum diameter Dmax <input type="text" name="entry.184211383" value="" size="5"> <small>(in the same inverse units (Angstrom or nm) as for Q)</small><br>
  
particle scattering length density (10^-6/Angstrom^2):  <input type="text" name="entry.405121486" required value="3.11" size="5"> <small>(default value for proteins)</small><br>

solvent scattering length density (10^-6/Angstrom^2):  <input type="text" name="entry.474174320" required value="6.35" size="5"><small>(default value for H2O)</small><br>

<p> <input type="radio" name="entry.1033017014" required value="large" checked="checked"> large beads <small> (faster reconstruction)</small>  <input type="radio" name="entry.1033017014" value="small"> small beads <small>(slower reconstruction)</small> <br> </p> 

<input type="submit" value="start reconstruction from SANS data" onclick="shrinktextB();" />

</form>
___



### Hints about data input and the shape reconstruction procedure

- The main body of the pasted ASCII data should be in a three column format (_Q, intensity, intensity error bar_) like in the following example:

```
    4.138455E-02          5.904029      1.555333E-01  
    4.371607E-02          5.652469      1.527037E-01  
    4.604759E-02          5.533381      1.521723E-01  
    4.837912E-02          5.547052      1.474577E-01 
    5.071064E-02          5.296281      1.436712E-01 
```

- Avoid any zero or negative values for _Q_, _intensity_ and _intensity error bar_ in the input file. Also exclude any high-Q flat plateaus that are obviously background dominated. 

- Any existing comment lines in the ASCII data file will be ignored.

- Consider to remove from the ASCII data file any early experimental points that might not follow the Guinier law.

- Units can be either in Angstrom or nm and this info needs to be specified in the radio buttons. If input experimental data are in Angstrom then the optional _Dmax,Qmax_ values should be given in _Angstrom_ and _1/Ansgtrom_ units respectively. If input experimental data are in nm then the optional _Dmax,Qmax_ values should be given in nm and _1/nm_ units respectively.

- Default _sld_ and _electron densities_ are those of proteins. In the case of nucleic acids, these values need to be adjusted by the user.

- Default _sld_ (neutron case) is that of deuterated water. If you work with a mixed H2O/D2O solvent you need to adjust this value.

- Instrument resolution info has to be provided only for SANS reconstructions. Default values represent usual settings at a SANS diffractometer.

- In most cases, the automatic IFT will be able to provide a reliable estimation of _Dmax_. If that is not the case, then the user should give an estimation of Dmax, and perform the calculations again.

- Shape reconstruction may take from a few minutes up to several hours. A report of the results will be emailed to the specified address.

- It is advised to run multiple reconstructions for the same dataset, in order to estimate solution stability. Please do not submit more than 4 shape reconstructions, simultaneously. In case of high server load, your reconstructions will be placed in a waiting list.

