# `property ConLen` command

## Syntax

`property ConLen filename Keyword Args`

- filename = file name

- Keyword = *NC* or *Ne*
     
    - *NC* = Chain length

    - *Ne* = monomer number in blob
    
- Args = *format*
    - *format*  = data, dump, cfg

## Examples
```text
property ConLen dump.PPA_0  NC 300  Ne 20
property ConLen dump.cfg_*  NC 500  Ne 20 format cfg
```
## Description
The `property ConLen` command calculate contour length of primitive path following the physical picture of tube model. 
Specially, each linear chain is divided into several blob (tube segments). 
The line that sequentially connects the center of mass of these blobs can be regarded as a proxy for the contour length of the primitive path.<sup>1</sup>

---

`filename` is name of the input coordinate file to be processed. 
If the `filename` does not end with the wildcard character, the command processes only this file. 
If the filename ends with `*`, the command processes all matching files. 
For wildcard processing, the matched filenames must end with non-zero-padded numerical indices, such as `0`, `1`, `2`, ..., instead of `01`, `02`, ...
For example, `dump.PPA_*` can match files such as:
`dump.PPA_0`, `dump.PPA_1`, `dump.PPA_2`, but not filenames with zero-padded indices such as: `dump.PPA_01`, `dump.PPA_02`.

---
`NC` specify the polymer chain length. 
If the input `dump` or `cfg` file does not contain `mol_ID` information, the system is assumed to be monodisperse, and chain identities are assigned based on `NC`.

---
`Ne` specify the monomer number in each blob. 
If `NC` cannot be evenly divided by `Ne`, the program will discard the particles at both ends.
When `Ne` = 1, the contour length of the primitive path is simply the total length obtained by connecting all monomers sequentially along the chain.
This length corresponds to the contour length after energy minimization, as defined by Sukumaran et al.<sup>2</sup>


---
`format` specify the format of the input file. 
Supported formats are LAMMPS data files (`data`), LAMMPS dump files (`dump`), and CFG files (`cfg`).
If your CFG file cannot be read correctly, please contact us with the file format details, and we will try to improve the program accordingly.

## Default
format = dump, NC = 0, Ne = 20


## References

[1] Ruan, Y.; Lu, Y.; An, L.; Wang, Z.-G. *Macromolecules* **2019**, *52(11)*, 4103-4110. https://10.1021/acs.macromol.9b00392

[2] Sukumaran, S. K.; Grest, G. S.; Kremer, K.; Everaers, R. *J. Polym. Sci. B: Polym. Phys.* **2005**, *43(8)*, 917–933. https://doi.org/10.1002/polb.20384

