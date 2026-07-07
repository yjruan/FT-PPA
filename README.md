# Nexus
## Preface
A program for analyzing properties of polymer systems.
The program uses modern Fortran standards (2003 or later) with modules, and is designed to analyze instantaneous configurations generated from LAMMPS simulations.

The current version can process orthogonal, monoclinic, and triclinic simulation boxes. 
These box types correspond to equilibrium simulations, shear simulations using the `fix deform` command, and uniaxial extensional simulations using the `fix nvt/uef` command in LAMMPS, respectively.
It provides tools for characterizing polymer systems, including entanglement analysis (FT-PPA), structural analysis (radius of gyration, chain orientation etc.), tube theory calculation, as well as several additional utilities for post-processing simulation data.


**FT-PPA** is an important module of this program.
FT-PPA is an analysis of primitive paths for entangled polymers based on combining energy minimization with the Frenet trihedron
geometric analysis. 
More details about this method can be found in [Macromolecules 2024, 57, 2792](https://pubs.acs.org/doi/10.1021/acs.macromol.3c02054).

However, I have no time to add all **Error** or **WARNING** message in program.
Users are welcome to try this program and provide feedback. 
Any comments or suggestions will be greatly appreciated, and the program will be continuously improved in future updates.

Z1+ code is another widely used primitive path analysis for entangled polymers. Interested users can refer to [this webpage](https://github.com/mkmat/Z1plus-code) for more information


## Quick Start

`Nexus` is written in Fortran.
Users can either compile the program from source code or directly use the precompiled executable files provided for Linux and Windows.
- [Compile from Source on Linux](docs/QS_Complie.md)
- [Use Precompiled Executable Files](docs/QS_Executable.md)

By default, `Nexus` searches for an input file named `input.dat` in the current directory. The analysis task, input configuration file, output file name, and other parameters should be specified in `input.dat`.
After reading `input.dat`, Nexus will perform the selected analysis task from the modules listed in the [Features Overview](#features-overview) section.

Users can find test configurations and their corresponding analysis results in the `example` directory, which can be used to check the input format and verify the program output.

## Features Overview
- [1. FT-PPA: Entanglement Analysis](docs/FT-PPA.md)
  - [1.1 Statistics](docs/FT-PPA_Stat.md)
  - [1.2 Visualization](docs/FT-PPA_Dump.md)

- [2. Property: Chain Analysis](docs/property.md)
  - [2.1 Radius of Gyration](docs/property_Rg.md)
  - [2.2 End-to-End Distance]
  - [2.3 Contour Length of Primitive Path](docs/property_Conlen.md)
  <!--- [2.4 Contour Length of Primitive Path](docs/property_Conlen.md)>

## License

Nexus is distributed under the [GNU General Public License v3.0](LICENSE).

Nexus incorporates source code from [FLAP](https://github.com/szaghi/FLAP), developed by Stefano Zaghi and used under the GNU General Public License v3.0. Additional third-party copyright and license information is provided in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).


