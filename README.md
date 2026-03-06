# Geometry-controlled competition between axis centering and detwinning in fivefold-twinned gold nanoparticles

This directory contains molecular dynamics (MD) simulation trajectories and analysis data supporting the findings in the article "Geometry-controlled competition between axis centering and detwinning in fivefold-twinned gold nanoparticles".
## Directory Structure
### `starting_structures/`
Contains the `.xyz` files of the starting structures for all analyzed simulations.
**Naming convention:** `auA_cutB_concaveCL.xyz`
- **A**: Size of the nanoparticle.
- **B**: Size of the Marks decahedron from which they are obtained.
- **convex/concave**: Geometry type.
- **C**: Number of layers over the five-fold axis.

### `Fig*/` Directories
Each figure directory (e.g., `Fig8-9`, `Fig10`) contains specific simulation data organized as follows:

#### `trajectory/`
Contains the frames of the trajectory of the simulation reported in the corresponding figure with a sampling rate of 1 frame/ns.
- **Filename format:** `p.n_frame-ttemperature-nsize` (e.g., `p.10000t0550n0216`).

#### `quenched_traj/`
Contains the corresponding trajectory frames (`q_p.*`) locally minimized using the L-BFGS algorithm.
- **Data files:** `quenched.out`, `quenched_ener.out`, `quenched_sig.out` contain potential energies and the main CNA signatures for each frame.

#### `CNA/`
Contains Common Neighbor Analysis (CNA) data. Atoms in `q_p.*_cna_map.xyz` are mapped to specific elements to visualize their local structural environment.

**Key Element Mappings (from `elenco_cna.txt`):**
- **Co**: Inner FCC
- **Zn**: Inner HCP (twin planes)
- **Cu**: Inner five-fold axis


#### `zoom*/`
Contains high-resolution trajectory data (e.g., 100 frames/ns) to capture rapid mechanisms.
- `photo_intervals.in`: Specifies the starting time, ending time, and photo rate.

#### Further Analysis
- **Pressure**: For each frame, a file `p_*` contains columns: `n_frame`, `element`, `pressure`, `stress_x`, `stress_y`, `stress_z` (as defined in Eq. 3 and 2 of the manuscript).
- **Mean Pressure**: `mean_press.out` reports the average absolute pressure of each frame.
- **Neighbors**: The last column of `nn_count.out` indicates the average number of near neighbors.
