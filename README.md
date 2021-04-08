## Gradient-Informed Path Smoothing for Wheeled Mobile Robots (GRIPS)
C++ implementation of a post-smoothing approach that improves the quality of paths generated by sampling-based planners.

> Planning smooth trajectories is important for the safe, efficient and
> comfortable operation of mobile robots, such as wheeled robots moving in
> crowded environments or cars moving at high speed. Asymptotically optimal
> sampling-based motion planners can be used to generate such trajectories
> eventually. However, to achieve the necessary efficiency for the real-time
> operation of robots, one often uses their initial feasible trajectories or the
> trajectories of non-optimal planners instead, typically after a post-smoothing
> step. We propose a gradient-informed post-smoothing algorithm, called GRIPS,
> that deforms given trajectories by locally optimizing the placement of
> vertices while satisfying the system's kinodynamic constraints.  We show
> experimentally that GRIPS typically produces trajectories of significantly
> higher smoothness and smaller length than several existing post-smoothing
> algorithms.

If using GRIPS for scientific publications, please cite the following paper:

```
@inproceedings{heiden2018grips,
  author={Heiden, Eric and Palmieri, Luigi and Koenig, Sven and Arras, Kai O. and Sukhatme, Gaurav S.},
  booktitle={IEEE International Conference on Robotics and Automation (ICRA)},
  title={Gradient-Informed Path Smoothing for Wheeled Mobile Robots},
  year={2018}
}
```

## Requirements
* CMake >=3
* Eigen 3
* [OMPL ~1.3.1](https://github.com/ompl/ompl/releases)
* Qt5 (ensure the Qt Charts and SVG packages are installed)
* sudo apt install libqt5svg5-dev libqt5charts5-dev

## Content
The following CMake targets are available:

| CMake target      | Description                                                                        |
| ----------------- | ---------------------------------------------------------------------------------- |
| `homotopy_test`   | Compares paths from Theta* and A* before/after post-smoothing w.r.t homotopy class |
| `benchmark`       | Compares different post-smoothing and path planning algorithms (cf. Table 1) and generates statistics JSON in `log` folder |
| `shortening_test` | Compares path-shortening results on hand-crafted path (Fig. 2)                     |
| `showcase`        | Visualizes post-smoothing of Theta* path in S-shaped environment (Fig. 3)          |


## Used third-party tools
* [nlohmann/json](https://github.com/nlohmann/json) to store path statistics data for plotting
* [palmieri/posq](https://github.com/palmieri/posq) steer function for differential drive robots
