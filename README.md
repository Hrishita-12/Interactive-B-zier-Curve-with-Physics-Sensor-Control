This is an interactive cubic Bézier curve that behaves like a rope reacting to motion input.It is a visual simulation where a cubic Bézier curve dynamically responds to device gyroscope data (iOS) or mouse movement (Web).

The curve moves smoothly, visualize its tangents, and behave like a springy rope when control points are displaced.

LIVE DEMO: https://hrishita-12.github.io/Interactive-B-zier-Curve-with-Physics-Sensor-Control/

CONTROLS:

1.Web Version(Desktop/Mobile Browsers)

Drag Points: Click/touch and drag P₁ or P₂ (yellow circles) to reshape the curve

Adjust Physics:
Stiffness Slider: Controls spring resistance (0.01=soft, 0.2=stiff).
Damping Slider: Controls motion slowing (0.05=floaty, 0.2=sticky).
Reset: Press R key to reset all points to original positions.
Toggle Tangents: Adjust "Tangents" slider to increse/decrease length of tangent vectors.

2.ios version(ipad/iphone)

Tap "Enable Motion" button.
Grant permission when iOS asks.
Tilt device to apply forces:
     --Tilt Forward → Force moves points DOWN
     --Tilt Backward → Force moves points UP
     --Tilt Left → Force moves points LEFT
     --Tilt Right → Force moves points RIGHT

Gentle tilts: Subtle forces
Sharp tilts: Strong forces
Flat surface: No motion force     

UNDERSTANDING THE DISPLAY:

P₁/P₂ Toggle: Switch between monitoring points
Position (x,y): Current location on screen
Target (x,y): Resting position (where point wants to be)
Velocity: Speed and direction of movement
Acceleration: How quickly velocity is changing
Forces: Visual vectors show spring/damping/net forces

READING FORCE VECTORS:

Blue arrow (Fₛ): Spring force pulling toward target
Red arrow (Fₔ): Damping force opposing motion
Yellow arrow (Fₙ): Net force causing movement
Longer arrow = stronger force

     

