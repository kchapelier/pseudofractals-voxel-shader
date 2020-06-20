# pseudofractals-voxel-shader

Voxel shader (for [MagicaVoxel](https://ephtracy.github.io/)) to generate pseudofractal volumes.

![pseudofractals-voxel-shader example](https://github.com/kchapelier/pseudofractals-voxel-shader/raw/master/images/header.png "")

## Installing and updating

Copy the files in `shaders/` to the `shader/` folder in your installation of MagicaVoxel.

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

 * Start with the `*scale` set to 1, `distOrder` set to 2. or 1.001, `seed` set to a number other than 1 and 0 and `threshold` set to 0.5.
 * Tweak the `*scale`, `distOrder` and `seed` until you have an interesting volume.
 * Fine tune the `threshold` and eventually enable `cleaning` if there too many isolated voxels.
 * For best result, render in MagicaVoxel with marching cubes.

## Variants

Included are two variants of the shader.

`pseudofractal-sub` allows to carve an existing volume with the negative space of the pseudofractal.

`pseudofractal-add` allows to add the pseudofractal to an existing volume without affecting any of its own voxels.

Both variants use the same parameters as the main shader.

## Examples

 * https://twitter.com/kchplr/status/1042853519244636160
 * https://twitter.com/kchplr/status/1043258155118014464
 * https://twitter.com/ephtracy/status/1044071076379185152
 * https://twitter.com/ephtracy/status/1044087775526604801
 * https://twitter.com/NNNenov/status/1044068357367058432
 * https://twitter.com/Omegafoxxx/status/1043324264529649664
 

#### xs pseudofractal 1.0 1.0 1.0 1.0 0.7 0.4 1

![xs pseudofractal 1.0 1.0 1.0 1.0 0.7 0.4 1](https://github.com/kchapelier/pseudofractals-voxel-shader/raw/master/images/pseudo00b.png "")

#### xs pseudofractal 1.10 1.10 1.10 1.00001 0.1 0.5 1

![xs pseudofractal 1.10 1.10 1.10 1.00001 0.1 0.5 1](https://github.com/kchapelier/pseudofractals-voxel-shader/raw/master/images/pseudo01b.png "")

#### xs pseudofractal .25 .25 .25 1.33 1.91 0.55 1

![xs pseudofractal .25 .25 .25 1.33 1.91 0.55 1](https://github.com/kchapelier/pseudofractals-voxel-shader/raw/master/images/pseudo02b.png "")

#### xs pseudofractal .5 .5 .5 1.995 0.751 0.55 1

![xs pseudofractal .5 .5 .5 1.995 0.751 0.55 1](https://github.com/kchapelier/pseudofractals-voxel-shader/raw/master/images/pseudo03b.png "")

#### xs pseudofractal 1.5 1.5 0.5 2.0 0.179929 0.5 1

![xs pseudofractal 1.5 1.5 0.5 2.0 0.179929 0.5 1](https://github.com/kchapelier/pseudofractals-voxel-shader/raw/master/images/pseudo04b.png "")


## Additional notes

 * Thank to [Alien](https://twitter.com/LienTheAlien) who first introduced me to pseudofractals ;)
 * Check Jes Wolfe's talk on the subject ([youtube](https://t.co/NcJOgdn0bu)) if you want to learn more about pseudofractals.
 * If you're interested in this kind of structure generation but want something more predictable and less random, please check [cellular-automata-voxel-shader](https://github.com/kchapelier/cellular-automata-voxel-shader).

## History

### 1.2.0 (2020-06-20) :

 * Add experimental brush shader for the new voxel brush feature in MagicaVoxel (0.99.5.1).

### 1.1.0 (2018-10-05) :

 * Add sub and add variants.
 * Add examples in doc.

### 1.0.1 (2018-09-19) :

 * Fixed an issue which would make the shader fail to work properly on some GPU.

### 1.0.0 (2018-09-18) :

 * First implementation.
