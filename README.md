# DFT

The main objective of this repository is to study the adsorption of carbon monoxide (CO) on the metal surface Au (111). To carry out this study it is required that you have the ```quantum-espresso``` and ```xcrysden``` packages installed. In addition, basic knowledge about ```ab-initio``` calculations is necessary.

## Convergence parameters
in the ```./FCC``` folder we can find different metals with a structure face-centered cubic (fcc). The following figure shows the convergence of energy as a function of paramater ```ecutwfc```. The calculation made is of type ```scf``` and the ```k-points``` are ```8, 8, 8```

![ecut_e](https://user-images.githubusercontent.com/37848611/41562372-bccedfec-7322-11e8-8679-c27af20f0aab.jpeg)



Then we analyzed the convergence of the energy with regard to the points k, we show below a table with the results obtained in the convergence:

element | ecutwfc [eV] |k-points| lattice const [a.u] | lattice const (exp)[a.u] | energy [eV]
--------|--------------|--------|---------------------|--------------------------|------------
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Au}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Au}" title="\mathrm{Au}" /></a> |545|6-8|1|7.706|1
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Ag}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Ag}" title="\mathrm{Ag}" /></a> |545|6-8|1|7.720|1
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Pt}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Pt}" title="\mathrm{Pt}" /></a> |272|4-6|1|7.415|1
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Pd}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Pd}" title="\mathrm{Pd}" /></a> |408|4-6|1|7.352|1
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Ir}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Ir}" title="\mathrm{Ir}" /></a> |408|8-10|1|7.255|1
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Rh}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Rh}" title="\mathrm{Rh}" /></a> |272|> 10|1|7.187|1

## Adsorption of CO on Au (111)
Using the experimental lattice parameter of the Au, we built the cell with the ```slab``` representing the surface (111) of the Au. The following figure shows the surface with the CO molecule arranged in a ```top``` place.

![pwi2xsf](https://user-images.githubusercontent.com/37848611/41565852-e2dc7850-732e-11e8-9d90-ea3cc75533eb.jpg)

The energy of adsorption on the surface is given by:

<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;E_{abs}&space;=&space;-&space;\left&space;(&space;E_{\mathrm{CO}/Sup}&space;-&space;E_{Sup}&space;-&space;E_{\mathrm{CO}}\right&space;)" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;E_{abs}&space;=&space;-&space;\left&space;(&space;E_{\mathrm{CO}/Sup}&space;-&space;E_{Sup}&space;-&space;E_{\mathrm{CO}}\right&space;)" title="E_{abs} = - \left ( E_{\mathrm{CO}/Sup} - E_{Sup} - E_{\mathrm{CO}}\right )" /></a>

Without relaxing this structure we calculate how is the convergence of the adsorption energy in function of the ecutwfc parameter.the input files are in ```./ADSORPTION_ECUTWFC```. 
