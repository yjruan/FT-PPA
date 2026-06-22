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
The `property ConLen` command calculate contour length of primitive path following the physical picture of tube model. Specially, each linear chain is divided into several blob (tube segments). The line that  sequentially connects the center of mass of these blobs can be regarded as a proxy for the contour length of the primitive path.

---

`filename` is name of the input coordinate file to be processed. 
If the `filename` does not end with the wildcard character, the command processes only this file. 
If the filename ends with `*`, the command processes all matching files. 
For wildcard processing, the matched filenames must end with non-zero-padded numerical indices, such as `0`, `1`, `2`, ..., instead of `01`, `02`, ...
For example, `dump.PPA_*` can match files such as:
`dump.PPA_0`, `dump.PPA_1`, `dump.PPA_2`, but not filenames with zero-padded indices such as: `dump.PPA_01`, `dump.PPA_02`.

---

`EnNum` will output the kink number per chain and entanglement number per chain to a file named `EnNum.DAT`.
The columns in the output file are `Num`, `Kink`, and `EnP`.
An entanglement is associated with a pair of kinks, 
Note that an entanglement is generally defined by a pair of kinks. However,
due to the multiple chain entanglements, one kink may be paired with two different kinks, and thus contribute to two entanglements. 
As a result, the kink number per chain and the entanglement number per chain are not identical.
| Column | Description |
|---|---|
| `Num` | File index |
| `Kink` | Kink number per chain |
| `EnP` | Entanglement number per chain |

---
`format` specify the format of the input file. Supported formats are LAMMPS data files (`data`), LAMMPS dump files (`dump`), and CFG files (`cfg`).
If your CFG file cannot be read correctly, please contact us with the file format details, and we will try to improve the program accordingly.

`NC` specify the polymer chain length. 
If the input `dump` or `cfg` file does not contain `mol_ID` information, the system is assumed to be monodisperse, and chain identities are assigned based on `NC`.