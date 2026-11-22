# Data

## Overview

This project uses synthetic data and assumed parameters to simulate pedestrian dispersal after the Kandy Esala Perahera. No real spectator attendance records, pedestrian tracking data or personally identifiable information are used.

The simulation generates pedestrian positions and desired walking speeds programmatically. These values are used to represent hypothetical crowd conditions within a simplified rectangular environment measuring 40 m × 20 m.

## Data Sources and Description

| Data or parameter | Description | Source | Licence |
|---|---|---|---|
| Initial pedestrian positions | Synthetic starting coordinates generated within the simulation environment, subject to minimum separation constraints | Generated programmatically by the project | Original project-generated data |
| Desired walking speeds | Synthetic pedestrian speeds sampled from a uniform distribution between 0.8 m/s and 1.6 m/s | Assumed model parameters | Original project-generated data |
| Crowd sizes | Hypothetical crowd sizes used in scenario comparisons and uncertainty experiments | Assumed experimental settings | Not applicable |
| Exit configurations | Hypothetical arrangements containing one, two or three exit openings | Defined by the project model | Original project design |
| Pedestrian movement parameters | Assumed values controlling acceleration, pedestrian interactions, wall repulsion and movement updates | Model assumptions informed by the cited literature in `REFERENCES.md` | Not applicable |

## Synthetic Data Generation

Pedestrian starting positions are generated using a seeded random number generator to support reproducibility. The generation procedure enforces a minimum initial separation of 0.65 m between pedestrians.

Desired walking speeds are sampled uniformly between 0.8 m/s and 1.6 m/s. In the uncertainty experiment, crowd sizes are sampled from a triangular distribution with a minimum of 100, a mode of 300 and a maximum of 500 pedestrians.

The random seeds and generation procedures are documented in the simulation notebook.

## Real-World Data and Limitations

The Kandy Esala Perahera provides the real-world context for this project. However, the simulation does not use measured attendance figures, actual pedestrian trajectories or surveyed street-layout data.

Consequently, the generated data should be interpreted as hypothetical inputs for exploring pedestrian dispersal scenarios, rather than measurements of actual event conditions.

No personal information or identifiable spectator data is collected or stored.

## Data Access and Reproducibility

No external dataset is required to run the simulation. The synthetic inputs are generated within the notebook using Python and its numerical libraries.

For the simulation methodology, parameter definitions and references, see:

- [`notebook/spectator-dispersal-simulator.ipynb`](../notebook/spectator_dispersal_simulator.ipynb)
- [`THEORY.md`](../THEORY.md)
- [`REFERENCES.md`](../REFERENCES.md)