# stirring

What happens within your mug when you stir your coffee? In this OpenFOAM case we get to see this process unfold, courtesy of Computation Fluid Dynamics (CFD).

The mesh for this case is generated using snappyHexMesh. A cylindrical set of faces is generated, which is then duplicated and transformed into a pair of Arbitrary Mesh Interface patches (AMI) patches. When doing so, the mesh gets divided into two regions: the inner part of the cylinder, containing the spoon, is free to rotate at a fixed angular velocity, while the outer part remains fixed. The pair of AMI patches are coupled together on each timestep to provide a continuous solution across this boundary. This mesh motion technique is often employed when simulating turbomachinery, propellers, and wind turbines.

The model, solved with interMixingFoam contains three fluid phases: air, water, and sugar. The last two are configured to be missible, while the air interface remains immissible. The vortices produced by stirring tend to mix the sugar, initially concentrated on the bottom of the mug.

This simulation would benefit from using a finer mesh, and solving more of the turbulent scales, but I could not spare the computational resources required this week. Maybe sometime in the future :).

## Getting Started

* Run the `prepare.sh` to generate the mesh and setup the simulation.
* Then run the case with `interMixingFoam`

## Results

[![Watch the video](https://img.youtube.com/vi/qQmnty3gCW0/default.jpg)](https://youtu.be/qQmnty3gCW0)

## License

This project is licensed under the MIT License - see the LICENSE.md file for details

## Author

Nicolás Diego Badano (https://www.linkedin.com/in/nicolas-diego-badano/)
