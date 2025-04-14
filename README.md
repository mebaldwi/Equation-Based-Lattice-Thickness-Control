# Equation-Based-Lattice-Thickness-Control
This work proposes a new equation-based lattice definition which splits the lattice into build direction and planar components such that their design can be altered to address AM methods restricted to three degrees of freedom, thereby promoting their use in large-scale AM technologies and enables further design control for small-scale AM design. These custom nTop blocks can be used to execute a range of operations which are described in further detail below:

## Gyroid Generator v4 Level Set
Defines the level-set definition of the gyroid using the gyroid function to define an isosurface.

## Uniform Shift:
Defines the method for generating equation-based lattices with a uniform offset of the entire body in order to give the unit cell meaningful values of thickness. This block provides an example of how to combine it with a level-set definition using the block ‘Gyroid Generator v4 Level Set’. This is the recommended block to use if simply looking to discretely define the thickness of your lattices.

## CB Rotation Transformation:
This custom block rotates a vector to align the z-axis to a new defined axis $\mathbf{b}$. The matrix must be applied to a unit vector based on our assumption of $\mathbf{b}$ being a unit vector. This custom block supports the rotation of the axes in order to dynamically define the build direction of our lattices in 'Shift Rotation'. It uses the Signum function to account for the extrema cases.

## Shift Rotation
This defines a block that aims to address the build direction component of manufacturing, which requires separating the layer height and wall thickness into two separate input variables. This projects an ellipsoid along the isosurface to smoothly generate a body with the desired layer height and wall thicknes throughout the geometry. The block accepts a field as well, so it can be used to vary the thicknesses throughout a geometry based simulation results.


# Failed Implementation:
## Ellipse Intersect
This was a definition attempted to use in place of the 'Shift Rotation', but the fundamental equation fails at critical points in the isosurface.

