# DFT

The main objective of this repository is to study the adsorption of carbon monoxide (CO) on the metal surface Au (111). To carry out this study it is required that you have the ```quantum-espresso``` and ```xcrysden``` packages installed. In addition, basic knowledge about ```ab-initio``` calculations is necessary.

## Convergence parameters
in the CC folder we can find different metals with a structure face-centered cubic (fcc). We analyze here how is the convergence with the cutting potential ```ecutwfc``` and the numbert of k-point. The following figure shows the convergence of energy as a function of paramater ```ecutwfc```. The calculation made is of type ```scf``` and the k-points are ```8 8 8```

![ecut_e](https://user-images.githubusercontent.com/37848611/41562372-bccedfec-7322-11e8-8679-c27af20f0aab.jpeg)



Then we analyzed the convergence of the energy with regard to the points k, we show below a table with the results obtained in the convergence:

element | ecutwfc [eV] | k-points | energy [eV]
--------|--------------|----------|------------
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Au}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Au}" title="\mathrm{Au}" /></a> |7.706|2|1
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Ag}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Ag}" title="\mathrm{Ag}" /></a> |7.720|2|1
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Pt}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Pt}" title="\mathrm{Pt}" /></a> |7.415|2|1
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Pd}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Pd}" title="\mathrm{Pd}" /></a> |7.352|1|1
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Ir}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Ir}" title="\mathrm{Ir}" /></a> |7.255|1|1
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Rh}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Rh}" title="\mathrm{Rh}" /></a> |7.187|1|1


element | constan exp [a.u] | constan sim [a.u]
--------|-------------------|------------------
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Au}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Au}" title="\mathrm{Au}" /></a> |7.706|2
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Ag}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Ag}" title="\mathrm{Ag}" /></a> |7.720|2
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Pt}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Pt}" title="\mathrm{Pt}" /></a> |7.415|2
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Pd}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Pd}" title="\mathrm{Pd}" /></a> |7.352|1
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Ir}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Ir}" title="\mathrm{Ir}" /></a> |7.255|1
<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\mathrm{Rh}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\mathrm{Rh}" title="\mathrm{Rh}" /></a> |7.187|1
