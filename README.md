# CEC Pose

Pose detection made easy!

This is a plug-and-play package for pose detection. Originally developed for the TMM-HRI project, it extracts the pose of a person given an RGB image, a depth image, the person's bounding box and segmentation mask, and the robot/camera's own pose.

The library was designed to be as easy to use as possible.

## Install

This package uses setuptools to make it accessible across your system.

Open a terminal and clone the git repository anywhere in your system, ideally not in the same folder as your project code.

`git clone https://github.com/gt-cec/cec-pose`

Install the package.

`pip install -e cec-pose`

And that's it!

## Usage

Using the package is quite easy, here is an example:

```
# import the package, this will cause some spam from mmengine
import cec_pose

# create a pose detector object, this will cause some spam from mmengine
pose_detector = cec_pose.PoseDetector()

# obtain a person's pose in 3D space
pred_person_loc, predicted_heading, (rw_coordinates, mean_depth, first_person_3d, keypoints, pred_skeleton) = pose_detector.get_heading_of_person(rgb, depth, detected_humans, robot_pose)
```

The outputs of `get_heading_of_person` are:

- `pred_person_loc`
- `predicted_heading`
- `rw_coordinates`
- `mean depth`