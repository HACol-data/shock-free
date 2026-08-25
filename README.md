```markdown
# SUBSO3_Nx4

Data and configuration for the `SUBSO3_Nx4` shock-free accretion-column simulation.

The corresponding post-processing and plotting code is available in:

<https://github.com/gvlipunova/plotHacol>

This repository contains model data only. It is intended to be placed as a nested data repository inside the code directory, for example:

```text
plotHacol/
├── plotmodel.py
├── tire_MPI.py
├── g_postpro.py
├── ...
└── SUBSO3_Nx4/
    ├── globals.conf
    ├── geo.dat
    ├── flux.dat
    ├── tireout.hdf5
    └── ...
```

## Model

This model corresponds to a shock-free solution used in the paper.

Main parameters:

```ini
[SUBSO3_Nx4]
outdir = SUBSO3_Nx4
mdot = 300.
mu30 = 0.1
afac = 0.25
ifdisc = False
nx = 4800
parallelfactor = 8
omegafactor = 0.0
voutfactor = -0.1
pressfactor = 0.99999999999999
raddiff = False
venttest = False
squeezemode = True
tmax = 100.
```

Parameter meanings include:

| Parameter | Meaning |
|---|---|
| `mdot` | Dimensionless mass-accretion rate used by the simulation |
| `mu30` | Magnetic dipole moment in units of \(10^{30}\ {\rm G\,cm^3}\) |
| `afac` | Azimuthal filling factor of the accretion column |
| `nx` | Number of radial grid points |
| `parallelfactor` | Parallelization factor |
| `omegafactor` | Stellar rotation-related parameter |
| `voutfactor` | Outer-boundary velocity factor |
| `pressfactor` | Outer-boundary pressure factor |
| `raddiff` | Enables/disables radiative diffusion |
| `venttest` | Enables/disables vent test mode |
| `squeezemode` | Enables squeezed-column geometry mode |
| `tmax` | Maximum simulated time in code units |

## Typical outputs

The repository may contain model inputs and selected output files such as:

```text
globals.conf
geo.dat
flux.dat
tireout.hdf5
```

Some large or automatically generated files are intentionally ignored by Git, including:

```text
HDF5 output files
tireout*.dat
ftable.dat
sfront.dat
summary.txt
log
post-processing figures
early/ and late/ plot directories
```

See `.gitignore` for the complete list.

## Running and plotting

The model is normally run using the simulation code from the `plotHacol` repository. For example, from the parent code directory:

```bash
python tire_MPI.py SUBSO3_Nx4
```

Post-processing may be performed with:

```bash
python plotmodel.py SUBSO3_Nx4
```

The exact commands and available plotting options are described in the main code repository:

<https://github.com/gvlipunova/plotHacol>
```

Then add it to the data repository:

```bash
git add README.md
git commit -m "Add README for SUBSO3_Nx4 model data"
git push origin main
```

OpenAI GPT-5.6 Terra (External...  •  175039 + 793 tokens
