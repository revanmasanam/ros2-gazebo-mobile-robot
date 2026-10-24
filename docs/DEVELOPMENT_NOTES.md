# Development Notes

This file tracks implementation observations from the repository snapshot. Update it when a fix is verified on the target ROS 2/Gazebo installation.

## First validation pass

- [ ] Build both packages with `colcon build --symlink-install`.
- [ ] Launch `my_robot_description display.launch.xml` and check that the robot model and fixed links appear in RViz2.
- [ ] Launch `my_robot_bringup my_robot_gazebo.launch.xml` and verify that the robot is spawned in `warehouse_world`.
- [ ] Confirm the Gazebo source joint-state topic exists and publishes data.
- [ ] Confirm `/joint_states` publishes and wheel link TFs become available in RViz2.
- [ ] Confirm `/camera/image_raw` and `/camera/camera_info` publish.
- [ ] Publish a small `/cmd_vel` command and confirm the simulated robot moves as expected.
- [ ] Confirm the ROS clock is using simulation time where required.

## Known follow-up work

- Fix the joint-state pipeline if the source topic exists but `/joint_states` remains silent.
- Consider adding a ROS `/odom` bridge if odometry is needed by downstream nodes.
- Replace spherical wheel collisions with more appropriate wheel collision geometry and retest the dynamics.
- Add screenshots or a short GIF to the README once a stable, validated simulation is running.
- Record the exact tested OS, ROS 2 distribution, and Gazebo Sim version after validation.
