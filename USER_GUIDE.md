# User Guide: Spectator Dispersal Simulator Web Demo

**Open the demo:** [Spectator Dispersal Simulator](https://sashanka2001.github.io/spectator-dispersal-simulator/)

The application runs directly in a modern browser such as Google Chrome, Microsoft Edge or Firefox. No additional software installation or data upload is required.

To run it locally, download the repository, open the `docs` folder and double-click `index.html`.

![Spectator Dispersal Simulator web demo](figures/web-demo.png)

## Controls

The simulator provides three main parameters that can be adjusted before starting a simulation.

| Control | Description | Range | Default |
| ------- | ----------- | ----- | ------- |
| **Number of pedestrians** | Sets the initial number of pedestrian agents in the environment. | 50–500 pedestrians, in increments of 10 | 100 |
| **Exit configuration** | Selects the number of available exit openings along the right boundary. | One, two or three exits | One exit |
| **Walking-speed multiplier** | Scales the baseline desired walking speeds of all pedestrians. A value of `1.00×` retains the original speeds. | `0.70×`–`1.30×`, in increments of `0.05×` | `1.00×` |
| **Start** | Begins the simulation using the selected settings. | — | — |
| **Pause** | Temporarily stops the simulation and retains its current state. | — | — |
| **Reset** | Restarts the simulation using the currently selected settings. | — | — |

## Reading the Outputs

The application provides a live visualisation and several numerical measurements.

- **Pedestrian visualisation:** Represents the hypothetical 40 m × 20 m environment. Blue dots are active pedestrians, green markings indicate exit openings, and pedestrian movement can be observed as agents move towards their selected exits.
- **Simulation time:** The elapsed simulated time, in seconds.
- **Exited pedestrians:** The number of pedestrians who have successfully left the environment.
- **T95:** The time required for at least 95% of the initial pedestrians to exit, in seconds.
- **Clearance time:** The total time required for all pedestrians to leave the environment, in seconds.
- **Peak local density:** The highest recorded pedestrian density in any 2 m × 2 m grid cell, in persons/m².
- **Exit utilisation:** The number of pedestrians who used each available exit.

A lower T95 and clearance time indicate faster dispersal. A lower peak local density indicates a lower maximum concentration of pedestrians within an individual grid cell.

## Try This

The following scenario can be used to investigate how additional exits influence pedestrian dispersal.

1. Set the number of pedestrians to 100, select one exit and retain the walking-speed multiplier at 1.00×. Press **Start** and allow the simulation to finish. Record T95, clearance time and peak local density.

2. Reset the simulator and repeat the experiment using two exits, keeping the crowd size and walking-speed multiplier unchanged.

3. Repeat the experiment with three exits.

4. Compare the recorded outputs. Observe whether additional exits reduce dispersal time and peak local density, and examine how pedestrians are distributed across the available exits.

For a separate experiment, keep the exit configuration unchanged and increase the crowd size from 100 to 300 and then to 500 pedestrians. Observe how increasing the initial crowd size affects dispersal time and local congestion.

## Check Against the Notebook

The web demo includes a reference case for 100 pedestrians with a walking-speed multiplier of 1.00×. The following values are embedded as reference outputs for the three exit configurations:

| Exit configuration | T95 (s) | Clearance time (s) | Peak density (persons/m²) |
| ------------------ | ------: | -----------------: | ------------------------: |
| One exit | 40.20 | 47.75 | 1.25 |
| Two exits | 40.20 | 46.55 | 1.00 |
| Three exits | 39.85 | 45.20 | 1.00 |

These values are browser-demo reference values and should be checked against a fresh execution of the corresponding 100-pedestrian notebook scenario before being treated as verified notebook matches.

The comparison applies only to the specified 100-pedestrian case at the original walking-speed multiplier. Other crowd sizes and speed settings are intended for exploratory use and are not direct reproductions of the notebook's Monte Carlo experiments.

## Limitations

- The web demo uses a simplified rectangular environment rather than the actual street layout of Kandy.
- Pedestrian positions and desired walking speeds are based on synthetic information and assumed parameters, not measured event data.
- The model simplifies pedestrian behaviour and does not fully represent group movement, obstacles, complex route choices, vehicles or emergency responses.
- The browser simulation is deterministic for a given configuration and does not perform the notebook's repeated Monte Carlo analysis.
- The results are intended for educational exploration and comparison of hypothetical scenarios. They should not be used as real-world crowd-safety predictions.
