# `property Rg` command

## Syntax

`property Rg filename Keyword Args`

- filename = file name

- Keyword = *NC*
     
    - *NC* = Chain length
    - *MaxMP* = Only chains ID ≤ MaxMP are considered
    - *MinMP* = Only chains ID ≥ MinMP are considered
    
- Args = *format*
    - *format*  = data, dump, cfg
    - *RFile*   = Result file name

## Examples
```text
property Rg dump.PPA_0  NC 300  
property Rg dump.cfg_*  NC 500  MaxMP 10 format cfg
```
## Description
The `property Rg` command calculates the mean-square radius of gyration for linear chains. In future versions, this function will be extended to polymer chains with arbitrary topologies.

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
In polydisperse linear-chain systems, `MaxMP` and `MinMP` allow users to select polymer chains within a specified range of molecular IDs. 
Specifically, `MaxMP` selects chains with molecular IDs not exceeding the given maximum value, whereas `MinMP` selects chains with molecular IDs not lower than the given minimum value.

---
`format` specify the format of the input file. 
Supported formats are LAMMPS data files (`data`), LAMMPS dump files (`dump`), and CFG files (`cfg`).
If your CFG file cannot be read correctly, please contact us with the file format details, and we will try to improve the program accordingly.

`RFile` specifies the name of the result file. The calculated results will be written to the file defined by the user.


## Default
format = dump, NC = 0, RFile = RG.DAT




