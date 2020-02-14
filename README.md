﻿# Skeleton Animation Utilities

Utility functions and data structures for skeleton animations loaded from BVH and ASF/AMC files. The library provides functions for inverse kinematics and retargeting. The main dependency, in addition to NumPy, SciPy and Matplotlib, is the transformations library by Christoph Gohlke https://www.lfd.uci.edu/~gohlke/.

 
This module is supposed to be loaded as a submodule in an experiment or tool environment.

## Example 

```python   
from anim_utils.animation_data import BVHReader, MotionVector, SkeletonBuilder   

bvh = BVHReader("example.bvh")   
mv = MotionVector()  
mv.from_bvh_reader(bvh)  
skeleton = SkeletonBuilder().load_from_bvh(bvh)  
point_clouds = []  
for frame in mv.frames:  
    point_cloud = []  
    for j in skeleton.animated_joints:  
        p = skeleton.nodes[j].get_global_position(frame)  
        point_cloud.append(p)  
     point_clouds.append(point_cloud)  

```
## Developers

Erik Herrmann<sup>1</sup>, Han Du<sup>1</sup>, Martin Manns<sup>2</sup>, Markus Mauer<sup>2</sup>
  
<sup>1</sup>DFKI GmbH  
<sup>2</sup>Daimler AG  


## License
Copyright (c) 2019 DFKI GmbH.  
MIT License, see the LICENSE file.

Contributions by Daimler AG in the following files are also licensed under terms of the MIT license:
anim_utils/animation_data/bvh.py  
anim_utils/animation_data/utils.py 

Each file contains a copyright notice.
