# NWT_potentialFreeSurfaceFoam

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)
[![OpenFOAM](https://img.shields.io/badge/OpenFOAM-v2406-green.svg)](https://www.openfoam.com/)

## Overview

Validated OpenFOAM-based numerical wave tank implementation using the `potentialFreeSurfaceFoam` solver with complete case setups demonstrating wave generation, propagation, and validation against experimental data.

## Associated Publication

This repository directly supports published research on numerical wave tank validation. Please cite the relevant publication if you use this code.

## Quick Start

```bash
# Clone and extract
git clone https://github.com/SeaFD/NWT_potentialFreeSurfaceFoam.git
cd NWT_potentialFreeSurfaceFoam
unzip S03.zip && cd S03

# Source OpenFOAM (adjust path)
source /path/to/OpenFOAM/etc/bashrc

# Run simulation
./Allrun

# Visualize
paraFoam
```

## Requirements

- OpenFOAM v2312 or later
- ParaView for visualization
- Python 3.x for post-processing

## Case Description

The S03 case provides a validated regular wave test condition with experimental comparison data.

## License

GNU GPL v3.0 - required for OpenFOAM compatibility. See [LICENSE](LICENSE).

## Author

**Josh Davidson**  
ORCID: [0000-0001-5966-4272](https://orcid.org/0000-0001-5966-4272)

## Related

- [potentialFreeSurfaceFoam solver](https://github.com/SeaFD/potentialFreeSurfaceFoam)
- [A-NWT](https://github.com/SeaFD/A-NWT)
