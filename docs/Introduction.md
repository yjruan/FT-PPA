# Introduction
## 1. Overview
Developed based on my learning and research experience, the program uses modern Fortran standards (2003 or later), and provides tools for problems in polymer simulation and theory, including entanglement analysis ([**FT-PPA** algorithm](https://pubs.acs.org/doi/10.1021/acs.macromol.3c02054)), structural analysis (radius of gyration, chain orientation etc.), tube theory calculations, as well as several additional utilities for post-processing simulation data.

The entanglement analysis is an important module of this program.
FT-PPA is an analysis of primitive paths for entangled polymers based on combining energy minimization with the Frenet trihedron geometric analysis. See the work [Macromolecules 2024, 57, 2792](https://pubs.acs.org/doi/10.1021/acs.macromol.3c02054).

I have no time to add all **Error** or **WARNING** message in program.
Users are welcome to try this program and provide feedback. 
Any comments or suggestions will be greatly appreciated, and the program will be continuously improved in future updates.

Although the project is called **FT-PPA**, the program was developed earlier and retains its original name, **Nexus**, in memory of the time my son and I spent watching Ultraman together.

## 2. Features
- [1. FT-PPA: Entanglement Analysis](FT-PPA.md)
  - [1.1 Statistics](FT-PPA_Stat.md)
  - [1.2 Visualization](FT-PPA_Dump.md)

- [2. Property: Chain Analysis](property.md)
  - [2.1 Radius of Gyration](property_Rg.md)
  - [2.2 End-to-End Distance](property_Re.md)
  - [2.3 Contour Length of Primitive Path](property_Conlen.md)
  - [2.4 Mean Square Internal Distance](property_MSID.md)

## 3. Install
Users can directly use the precompiled executable files provided for Linux and Windows.

<!-- either compile the program from source code or 
 [Compile from Source on Linux] --(docs/QS_Complie.md)-->

- [Use Precompiled Executable Files](docs/QS_Executable.md)

Users can find test configurations and their corresponding analysis results in the `example` directory, which can be used to check the input format and verify the program output.


## 4. Additional Website Links
[1. LAMMMPS](https://docs.lammps.org/)

LAMMPS is a classical molecular dynamics (MD) code that models ensembles of particles in a liquid, solid, or gaseous state. Therefore, the coordinate file format mainly follows the LAMMPS input and output format.

[2. Z1 code](https://github.com/mkmat/Z1plus-code)

Z1+ code is a widely used primitive path analysis for entangled polymers. Interested users can refer for this method.


