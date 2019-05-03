# AWS DeepRacer 

model-3 results (100% track completed):
---
Track: re:Invent 2018
- 00:00:14.826
- 00:00:15.013
- 00:00:15.272
- 00:00:15.289
- 00:00:15.620


### params

```
{
    "all_wheels_on_track": Boolean,    # flag to indicate if the vehicle is on the track
    "x": float,                        # vehicle's x-coordinate in meters
    "y": float,                        # vehicle's y-coordinate in meters
    "distance_from_center": float,     # distance in meters from the track center 
    "is_left_of_center": Boolean,      # Flag to indicate if the vehicle is on the left side to the track center or not. 
    "heading": float,                  # vehicle's yaw in degrees
    "progress": float,                 # percentage of track completed
    "steps": int,                      # number steps completed
    "speed": float,                    # vehicle's speed in meters per second (m/s)
    "steering_angle": float,          # vehicle's steering angle in degrees
    "track_width": float,              # width of the track
    "waypoints": [[float, float], … ], # list of [x,y] as milestones along the track center
    "closest_waypoints": [int, int]    # indices of the two nearest waypoints.
}
```



all_wheels_on_track
---

Type: Boolean

Range: True|False

A Boolean flag to indicate whether the vehicle is on-track or off-track. It's off-track (False) if any of its wheels are outside of the track borders. It's on-track (True) if all of the wheels are inside the two track borders. The following illustration shows that the vehicle is on-track.

 
closest_waypoints
---

Type: [int, int]

Range: [0:48,1:49]

The zero-based indices of the two neighboring waypoints closest to the vehicle's current position of (x, y). The distance is measured by the Euclidean distance from the center of the vehicle.


distance_from_center
---

Type: float

Range: 0:~track_width/2

Displacement, in meters, between the vehicle center and the track center. The observable maximum displacement occurs when any of the agent's wheels are outside a track border and, depending on the width of the track border, can be slightly smaller or larger than half the track_width. 

heading
---

Type: float

Range: -180:+180

Heading direction, in degrees, of the vehicle with respect to the x-axis of the coordinate system.

 
is_left_of_center
---

Type: Boolean

Range: True | False

A Boolean flag to indicate if the vehicle is on the left side to the track center (True) or on the right side (False).


progress
---

Type: float

Range: 0:100

Percentage of track completed.


speed
---

Type: float

Range: 0.0:5.0

The observed speed of the vehicle, in meters per second (m/s). 


steering_angle
---

Type: float

Range: -30:30

Steering angle, in degrees, of the front wheels from the center line of the vehicle. The negative sign (-) means steering to the right and the positive (+) sign means steering to the left. The vehicle center line is not necessarily parallel with the track center line as is shown in the following illustration.

steps
---

Type: int

Range: 0:Nstep

Number of steps completed. A step corresponds to an action taken by the vehicle following the current policy.


track_width
---

Type: float

Range: 0:Dtrack

Track width in meters.

x, y
---

Type: float

Range: 0:N

Location, in meters, of the vehicle center along the x and y axes, of the simulated environment containing the track. The origin is at the lower-left corner of the simulated environment.

 
waypoints
---

Type: list of [float, float]

Range: [[xw,0,yw,0] … [xw,49, yw,49]]

An ordered list of milestones along the track center. Each milestone is described by a coordinate of (xw,i, yw,i). 
