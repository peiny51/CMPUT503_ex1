# CMPUT503_ex1

## Set up dashboard
go to http://csc22932.local or http://csc22932 (chrome may generate disconnection issue, try using other broswers)

## Make it move
`dts duckiebot keyboard_control csc22932`: open an arrows interface window

## Make it see
`dts start_gui_tools csc22932`: start a container with access to the ROS messages of the Duckiebot
`rqt_image_view`: open a window where you can view the image.

## Camera calibration
`dts duckiebot calibrate_intrinsics csc22932`: launch the intrinsic calibration application
`dts duckiebot calibrate_extrinsics csc22932`: launch the entrinsic calibration application

## Wheels calibration
`dts start_gui_tools csc22932`: 
`rostopic list`: see a list of ROS topics currently active on your Duckiebot
`rostopic echo /csc22932/camera_node/image/compressed`: listen to topics and show you incoming images as the Duckiebot sees them
`rosparam set /csc22932/kinematices_node/trim 0.02`: if right drifting, -trimming value if left drifting
`rosservice call /csc22932/kinematics_node/save_calibration`: save parameters
