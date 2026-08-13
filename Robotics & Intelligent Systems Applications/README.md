# Robotics & Intelligent Systems Applications

Three components of a mobile robot's autonomy stack, each demonstrated
standalone with visualization, plus a reference ROS2 node showing how they
fit together in a real sense-plan-act loop.

## 1. A* path planning (`--task path_planning`)
Plans a shortest path from start to goal across a 2D occupancy grid with
randomly-placed rectangular obstacles, using 8-connected movement (diagonal
moves allowed, correctly cost `√2` instead of `1`) and a Euclidean
heuristic. Saves a visualization (`astar_path.png`) showing the grid,
obstacles, and resulting path.

## 2. PID heading control (`--task pid_control`)
Simulates a **unicycle-model** robot (position + heading, constant linear
velocity) driving through a sequence of waypoints, using a PID controller
on heading error to compute the angular velocity command at each timestep —
the same structure used to steer a real differential-drive robot toward a
planned path. Saves a trajectory visualization (`pid_tracking.png`).


## Why these three
This mirrors the real architecture of a mobile robot's navigation stack:
**perceive → plan (A*) → control (PID) → actuate**, which is the same
sense-plan-act loop used in ROS-based systems (`move_base`/`nav2`), just
implemented from first principles here to show the underlying logic rather
than only calling a library.

## Tech stack
`numpy`, `matplotlib`; task 3 additionally references `rclpy` and standard
ROS2 message types (`nav_msgs`, `geometry_msgs`).

## Usage

```bash
python robotics_applications.py --task path_planning
python robotics_applications.py --task pid_control
```

## Possible extensions
- Swap A* for RRT*/Hybrid-A* for kinodynamically-feasible planning
- Add obstacle-avoidance re-planning (re-run A* when the costmap updates)
- Extend the PID controller to a full path-tracking controller (Pure
  Pursuit or Stanley controller) for smoother curvature tracking
- Actually build and test `nav_node.py` in a ROS2 + Gazebo/Nav2 simulation
