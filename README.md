# Introduction
The program uses the [**FT-PPA** algorithm](https://pubs.acs.org/doi/10.1021/acs.macromol.3c02054) to analyze entanglements in polymers and also calculate other properties. 
- [1. Overview](docs/Introduction.md#1-overview)
- [2. Features](docs/Introduction.md#2-features)
- [3. Install](docs/Introduction.md#3-install)
- [4. Additional website links](docs/Introduction.md#4-additional-website-link)

# Quick Start

1) Download the executable from the [Releases](https://github.com/yjruan/Nexus/releases) page.

2) Place the executable, a file named `input.dat`, and particle coordinate files in the same directory.

3) Specify the properties you want in the `input.dat`, such as entanglement number, the radius of gyration, etc. See the [Features](docs/Introduction.md#2-features) for details. For example:
```text
   FTPPA Stat dump.PPA_0 EnNum NC 300
```
This command counts (Stat) the entanglement number (EnNum) from dump.PPA_0, assuming a chain length (NC) of 300.

4) Run the program: on Windows, double-click the executable; on Linux, grant execute permission using `chmod`, and run it.

5) The program will output the properties as specified in `input.dat`. 

6) Example input files and their corresponding outputs are available in the [`example`](example) directory.

# Key Features
The program provides entanglement information for equilibrium, shear, and uniaxial extensional simulations using orthogonal, monoclinic, and triclinic simulation boxes, respectively. 
These simulations are performed in LAMMPS using equilibrium conditions, `fix deform`, and `fix nvt/uef` commands, respectively.



# License

Nexus is distributed under the [GNU General Public License v3.0](LICENSE).

Nexus incorporates source code from [FLAP](https://github.com/szaghi/FLAP), developed by Stefano Zaghi and used under the GNU General Public License v3.0. 
Additional third-party copyright and license information is provided in [THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).


