## Example property

This directory contains a molecular dynamics configuration (`dump.RE-POSITION_0`) and a reference input script (`input.dat`). 
The system is an equilibrium configuration of the Kremer–Grest model with a chain length of (N = 300) and a bending potential parameter of 2.0. 
Further details of the simulated system can be found in Ref [1](https://doi.org/10.1021/acs.macromol.3c02054).

To run the example, place the `Nexus` executable in the directory and execute the program.
`Nexus` will read the settings specified in `input.dat`. 
The **Command** used in `input.dat` are described in [here](../../docs/property.md).

The following results will then be generated sequentially:

1. **`RG.DAT`**
   This file contains the components of the mean-square radius of gyration.



## References

[1] Ruan, Y.; Lu, Y.; An, L.; Wang, Z.-G. *Macromolecules* **2024**, *57(6)*, 2792–2800. https://doi.org/10.1021/acs.macromol.3c02054