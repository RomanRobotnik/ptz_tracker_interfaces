# ptz_tracker_interfaces

ROS 2 interface package containing the `TrackTarget` action used by PTZ tracking nodes.

## Action Definition

`action/TrackTarget.action` provides:

- **Goal**
  - `bool start` — simple trigger to start tracking.
- **Result**
  - `bool success`
  - `string message`
  - `float64 final_pan`
  - `float64 final_tilt`
  - `float64 final_zoom`
- **Feedback**
  - `float64 current_pan`
  - `float64 current_tilt`
  - `float64 current_zoom`

## Build

```bash
cd ~/workspaces/robotnik_sim_ws
colcon build --packages-select ptz_tracker_interfaces
source install/setup.bash
```

## Usage

Other packages (e.g., `ptz_tracker`) can depend on this repository to share the action definition:

```cmake
find_package(ptz_tracker_interfaces REQUIRED)
```

```xml
<exec_depend>ptz_tracker_interfaces</exec_depend>
```

This ensures consistent API between PTZ controllers and clients.