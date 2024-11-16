# Autonomous Drone Control using OpenCV

## Features

### Manual Override
- Press any steering key to switch from autonomous to manual mode.
- Actions and corresponding keys are defined in a control table.

### Startup and Livestream
- Displays the front camera livestream in a window.
- Drone waits for autonomous mode activation, which can be triggered before or after takeoff.

### Autonomous Flight Initiation
- Press `w` to start detecting circular shapes in the livestream.

### Object Detection and Initialization
- Detects circular shapes and locates their center.
- Hold the trackable object in view for ~5 seconds to save its color distribution in HSV color-space.
- Thresholds are set to isolate the object from the background.

### Object Tracking with CamShift
- Continuously tracks the object based on its color in each frame.
- Adjusts drone position to keep the object centered.
- Moves forward/backward to maintain the initial object distance.

### Detection and Tracking Stages
1. **HoughCircle Detection**: Identifies circular shapes.
2. **CamShift Algorithm**: Tracks the object based on color or brightness distribution.

### Algorithm Details
- Converts the image to HSV color-space for color-based tracking (hue values).
- Supports brightness-based tracking for flashlight-like objects in varying light conditions.
- Robust in dark environments; optional filters enhance tracking in brighter conditions.

