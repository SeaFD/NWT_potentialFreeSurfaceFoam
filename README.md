# NWT_potentialFreeSurfaceFoam

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![OpenFOAM](https://img.shields.io/badge/OpenFOAM-v2406-green.svg)](https://www.openfoam.com/)

---

## Overview

This repository provides a validated implementation of a **Numerical Wave Tank (NWT)** in OpenFOAM using the `potentialFreeSurfaceFoam` solver. The cases replicate physical wave tank experiments with a moving wall wavemaker and include systematic studies of:

* Wave generation and propagation
* Spatial and temporal convergence
* Solver parameter sensitivity
* Validation against experimental measurements
* Comparison with a Volume of Fluid (VoF) model using `interFoam`

The repository is intended to support reproducibility of the results presented in the associated publication and to serve as a reference implementation for NWT simulations in OpenFOAM.

---

## Associated Publication

This repository accompanies the following manuscript:

**"Numerical wave tank implementation and validation using potentialFreeSurfaceFoam"**

If you use this repository, please cite the publication.

---

## Repository Structure

```text
NWT_potentialFreeSurfaceFoam/
│
├── cases/
│   ├── potentialFreeSurfaceFoam/
│   └── interFoam/
│
├── README.md
└── LICENSE
```

### Description

* **potentialFreeSurfaceFoam/**
  Main study cases used for validation and convergence analysis.

* **interFoam/**
  VoF-based comparison case used to benchmark performance against a multiphase solver.

All cases share:

* identical geometry
* consistent wavemaker input (piston motion)

---

## Quick Start

```bash
# Clone repository
git clone https://github.com/SeaFD/NWT_potentialFreeSurfaceFoam.git
cd NWT_potentialFreeSurfaceFoam

# Navigate to a case 
cd cases/potentialFreeSurfaceFoam

# Source OpenFOAM (adjust path)
source /path/to/OpenFOAM/etc/bashrc

# Run simulation
./Allrun

# Visualise
paraFoam
```

---

## Running the interFoam Case

```bash
cd cases/interFoam
./Allrun
```

### Notes

* This case includes additional fields required for VoF simulations (e.g. `alpha.water`)
* Solver-specific numerical settings are included within the case directories
* Wavemaker input is aligned with the corresponding potentialFreeSurfaceFoam case

---

## Case Description

The cases are based on experimental wave tank data from the OES Task 10 benchmark.

### Key Features

* Moving wall wavemaker (prescribed piston motion)
* Free surface tracking via:

  * `zeta` (potentialFreeSurfaceFoam)
  * `alpha.water` (interFoam)
* Wave probe sampling at multiple locations
* Validation against experimental time series

---

## Requirements

* OpenFOAM v2406 (or compatible version ≥ v2312)
* ParaView (for visualisation)
* Bash environment (Linux/macOS or WSL)

Optional:

* Python 3.x (post-processing)

---

## Reproducibility Notes

* All simulation inputs (geometry, mesh, boundary conditions) are included
* Wavemaker motion is prescribed directly from experimental measurements
* No calibration or tuning of input signals is required
* Solver settings follow those described in the associated publication

---

## License

GNU GPL v3.0 – required for OpenFOAM compatibility.
See [LICENSE](LICENSE) for details.


## Author

**Josh Davidson**  
ORCID: [0000-0001-5966-4272](https://orcid.org/0000-0001-5966-4272)

## Related

- [potentialFreeSurfaceFoam solver](https://github.com/SeaFD/potentialFreeSurfaceFoam)
