<div align="center">

<p><sub>KINEMATICS OF SERIAL CHAINS &nbsp;·&nbsp; MCMLV</sub></p>

<h1>The Denavit–Hartenberg Convention</h1>

<p><em>Wherein a manipulator is reduced to four numbers per joint, those numbers to four elementary motions, and the motions to a single chain of matrix products, with a working model the reader may turn.</em></p>

<p><sub>A PRACTICAL TREATISE FOR STUDENTS OF MACHINES</sub></p>

<p>❦</p>

</div>

An interactive treatise on the Denavit–Hartenberg method for two- and three-link manipulators. The whole work is a single HTML file: open it, turn the joints, edit the table, and watch the matrices and the drawing follow.

<p align="center">
  <img src="docs/plate.jpg" alt="Plate I: the chain of frames, drawn from the parameter table" width="820">
</p>

<p align="center"><sub><em>Plate I: the chain of frames, drawn live from the table beneath it.</em></sub></p>

---

## Contents

- **I. The Mechanism.** An orbitable plate with a coordinate frame at every joint, view controls, and a live readout of the tool position.
- **II. The Table of Parameters.** Edit θ, d, a, and α for each joint, mark a joint revolute or prismatic, and load or restore a preset.
- **III. Four Motions, One Matrix.** The four elementary transformations for a selected joint, multiplied in order to compose its link matrix.
- **IV. The Chain of Transformations.** The cumulative products, the tool frame's axes and origin, and the orientation angles.
- **V. A Check by Hand.** For planar chains, the closed-form trigonometry set beside the matrix product.
- **VI. Notes on the Convention.** The standard (distal) convention, reading a homogeneous matrix, and exercises for the student.

## To turn the pages

No installation, no build step, and no server are required. Open `index.html` in any modern browser.

1. Choose **Two Links** or **Three Links** at the top of the page.
2. Drag the plate to orbit the model, or use the **Isometric**, **Elevation**, and **Plan** views.
3. Edit any number in the table. The elementary matrices, the composed link matrices, and the tool pose are recalculated at once.
4. Press **Animate the joints** to sweep the joint variables around their set values.
5. In § V, load a planar preset and compare the hand calculation with the matrix result.

The **R / P** button beside each joint switches it between a revolute joint, whose variable is θ, and a prismatic joint, whose variable is d.

## The convention

This page follows the **standard**, or **distal**, convention: frame {*i*} is fastened to link *i*, its *z* axis lies along the axis of joint *i*, and its *x* axis lies along the common normal from *z*<sub>*i*−1</sub> to *z*<sub>*i*</sub>. The transform from frame {*i*−1} to frame {*i*} is then

<p align="center">
  <img src="docs/link-matrix.png" alt="The link matrix: A_i equals R_z of theta_i, T_z of d_i, T_x of a_i, R_x of alpha_i, and equals the four-by-four matrix with rows [c theta, minus s theta c alpha, s theta s alpha, a c theta], [s theta, c theta c alpha, minus c theta s alpha, a s theta], [0, s alpha, c alpha, d], [0, 0, 0, 1]." width="760">
</p>

with *c*<sub>θ</sub> = cos θ<sub>*i*</sub>, *s*<sub>θ</sub> = sin θ<sub>*i*</sub>, and likewise for α.

| Symbol | Elementary motion | What it measures |
|:---:|:---|:---|
| θ<sub>*i*</sub> | rotation about *z*<sub>*i*−1</sub> | the joint angle, from *x*<sub>*i*−1</sub> to *x*<sub>*i*</sub> |
| d<sub>*i*</sub> | translation along *z*<sub>*i*−1</sub> | the link offset, from the origin of {*i*−1} to the common normal |
| a<sub>*i*</sub> | translation along *x*<sub>*i*</sub> | the link length, along the common normal |
| α<sub>*i*</sub> | rotation about *x*<sub>*i*</sub> | the link twist, from *z*<sub>*i*−1</sub> to *z*<sub>*i*</sub> |

The chain is carried out to the tool by the product

$$
T_n^0 = A_1 A_2 \cdots A_n
$$

whose columns are the tool axes and whose last column is its position.

## Colophon

Set in EB Garamond, IM Fell English, and Courier Prime, with serif and monospace fallbacks for offline reading. The plate is drawn as SVG, the arithmetic is plain JavaScript, and the page keeps no dependencies beyond its web fonts. Prepared for students of machines.

### Reference

> J. Denavit and R. S. Hartenberg, “A kinematic notation for lower-pair mechanisms based on matrices,” *Journal of Applied Mechanics*, 22(2):215 to 221, 1955.

<div align="center"><sub>❦</sub></div>
