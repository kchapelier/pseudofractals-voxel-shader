# pseudofractals-voxel-shader

Voxel shader (for [MagicaVoxel](https://ephtracy.github.io/)) to generate pseudofractal volumes.

## Installing and updating

Copy the files in `shaders` to the `shader` in your installation of MagicaVoxel.

## Usage

In MagicaVoxel, execute **xs pseudofractal 1.0 1.0 1.0 1.01 26. 0.4 0** in its console.

## Parameters

``xs pseudofractal xscale yscale zscale distOrder seed threshold cleaning``

- **xscale :** The scale on the X axis. Small number stretches the axis, large number condenses it.
- **yscale :** The scale on the Y axis. Small number stretches the axis, large number condenses it.
- **zscale :** The scale on the Z axis. Small number stretches the axis, large number condenses it.
- **distOrder :** The algorithm uses [Minkowski distance](https://en.wikipedia.org/wiki/Minkowski_distance) which is a generalization of Euclidean and Manhattan distance. This parameter control the "order" of the distance. Values larger than 2 tend to result in squarish structure with flat surfaces. Values very close to 1 (i.e. 1.001) tend to result in regular octahedra. Recommended values are between 0.5 and 2.5.
- **seed :** The "magic" value used to generate the pseudofractal. To be specific it is used as a modulus. A value of 0 will always result in an empty volume.
- **threshold :** Controls the ratio of live (solid) voxels. A value of 0 means that all voxels are considered as dead. A value of 1 means that all voxels are considered as alive.
- **cleaning :** If set and above 0, single / isolated voxels will be removed from the resulting volume.

## Recommended workflow

 * Start with the scales set to 1, distOrder set to 2. or 1.001, seed set to a number other than 1 and 0, threshold sets to 0.5
 * Tweak the scales, distOrder and seed until you have an interesting volume.
 * Fine tune the threshold and eventually enable orphanRemoval if there too many isolated voxels.
 * For best result, render in MagicaVoxel with marching cubes (requires 0.98.2 or lower as the current version do not support voxel shapes).

## Additionnal notes

 * Thank to [Alien](https://twitter.com/LienTheAlien) who first introduced me to pseudofractals ;)
 * Check Jes Wolfe's talk on the subject ([youtube](https://t.co/NcJOgdn0bu)) if you want to learn more about pseudofractals.
 * If you're interested in this kind of structure generation but want something more predictable and less random, please check [cellular-automata-voxel-shader](https://github.com/kchapelier/cellular-automata-voxel-shader).

 ## History

 ### 1.0.0 (2018-09-18) :

 * First implementation.