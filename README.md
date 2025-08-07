# TiltNTorsion
This repository calculates tilt and torsional angles of protein domains from an MD trajectory using VMD and TCL, and analyzes their energy profiles using Python. Useful to study conformational changes in proteins to check for which motions are energetically favourable.

```markdown
# MD Angle Analysis

This repository calculates tilt and torsional angles of protein domains from an MD trajectory using VMD and TCL, and analyzes their energy profiles using Python.

## Features
- Computes tilt and torsion angles from MD trajectories
- Accepts user-defined residues and segments
- Visualizes 2D energy landscapes

## Requirements
- VMD
- Python 3.8+
- Python packages: numpy, pandas, matplotlib

## Installation

    pip install -r requirements.txt



## Usage

1. **Edit config file**: `utils/config.json`
```
json
{
  "structure_file": "../input_example/structure.pdb",
  "trajectory_file": "../input_example/trajectory.xtc",
  "skip": 10,
  "segid1": "CHA1",
  "resid1": 434,
  "resid2": 398,
  "segid2": "CHA2",
  "resid3": 770,
  "resid4": 1010,
  "output_tilt": "../output/tilt_angles.dat",
  "output_torsion": "../output/torsion_angles.dat"
}
```

2. **Run VMD Tcl script**:
```
vmd -dispdev text -args utils/config.json -e scripts/angle_analysis.tcl
```

3. **Run Python script**:
```
python scripts/analyze_energy.py
```

## Outputs
- `tilt_angles.dat`: Frame-wise tilt angles
- `torsion_angles.dat`: Frame-wise torsion angles
- `energy_map.png`: Free energy map of tilt vs torsion
```

