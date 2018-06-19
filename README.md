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

Without relaxing this structure we calculate how is the convergence of the adsorption energy in function of the ```ecutwfc``` parameter, the input files are in ```./ADSORPTION_ECUTWFC```. The value in convergence is ```ecutwfc = 408 eV```, see the output files and the following figure:

## Surface Au(111)
We carry out a relaxation of the surface Au (111) to obtain the distance between relaxed layers. And later calculate the work function of the surface. the work function turned out to be ```5.2709 eV``` and the relaxed structure turned out to be:

```text
...
ATOMIC_POSITIONS (alat)
Au       0.000000000  -0.000000000  -0.071640824
Au       0.500000000   0.288675000   0.797508797
Au       0.000000000   0.577350000   1.652174586
Au       0.000000000  -0.000000000   2.520937441
...
```
the results and some graphs can be observed in the output files in ```./RELAX```.
### work function
The work function can be calculated by the expression:

<a href="https://www.codecogs.com/eqnedit.php?latex=\dpi{120}&space;\phi_{Au(111)}&space;=&space;v(\infty)&space;-&space;\epsilon_{fermi}" target="_blank"><img src="https://latex.codecogs.com/gif.latex?\dpi{120}&space;\phi_{Au(111)}&space;=&space;v(\infty)&space;-&space;\epsilon_{fermi}" title="\phi_{Au(111)} = v(\infty) - \epsilon_{fermi}" /></a>

The fermi energy can be easily obtained from the output. On the other hand, the potential function at infinity requires a post-processing of the output files. One must follow the following steps:

1- Calculation of potential by ```pp.x```

```bash
pp.x < Au_SURFACE_PP.in > Au_SURFACE_PP.out
```

where the structure ```pp.x``` can be seen in [Quantum Espresso](https://www.quantum-espresso.org/). Then we must use ```average.x```:

```bash
average.x < Au_SURFACE.average.in > Au_SURFACE.average.out
```
## Chemisorption of CO on Au(111)
Firstly, we locate the CO molecule almost vertically, allowing it to lean. Then we relax the structure, keeping the two lower layers of the surface fixed. To leave a fixed atom during relaxation we have to proceed as shown below in the input file:

```text
...
ATOMIC_POSITIONS alat
Au      0.000000        0.000000        0.000000    0   0   0
Au      0.500000        0.288675        0.816497    0   0   0
Au      0.000000        0.577350        1.632993 
Au      0.000000        0.000000        2.449490
 
C       0.500000        0.288675        3.073734
O       0.500001        0.289675        3.464843
...
```
then we perform this procedure again for different high symmetry sites ```top```, ```bridge``` and ```hollow```.

configuration	|	Energy of CO/Au(111) [Ry]	| Energy of Au(111)	[Ry]|	Energy of CO	[Ry] |	Energy of adsoption [Ry]|
--------------|---------------------------|-----------------------|-------------------|-------------------------
top		|	-1158.8585489846	|	-1098.8639312247   |	-59.9853925693 	|0.009225190599941868 
bridge	|		-1158.8315677922|		-1098.8639312247|		-59.9853925694    |   -0.017756001900004037
hollow		|	-1158.8218290875|	-1098.8639312247 |	-59.9853837055  |     -0.027485842700116336 	
