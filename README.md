# Interactive Cubic Bézier Curve with Physics & Sensor Control

This is an interactive cubic Bézier curve that behaves like a rope reacting to motion input. It is a visual simulation where a cubic Bézier curve dynamically responds to device gyroscope data (iOS) or mouse movement (Web).

The curve moves smoothly, visualizes its tangents, and behaves like a springy rope when control points are displaced.


---

## 💡 Features
- Real-time physics simulation with spring-mass-damper system
- Interactive Bézier curve manipulation
- Device motion sensor integration (iOS)
- Visual force vector display
- Adjustable parameters (stiffness, damping, tangents)
- Responsive design for desktop and mobile

---

## 🛠️ Technical Details
- Built with vanilla JavaScript, HTML5 Canvas
- Uses cubic Bézier curve equations
- Physics based on Hooke's law and damping equations
- Works on all modern browsers and iOS devices

---

## 📱 Compatibility
- **Web**: Chrome, Firefox, Safari, Edge (latest versions)
- **iOS**: Safari on iPhone/iPad (iOS 12+)
- **Android**: Chrome (touch works, motion may vary)
- **Desktop**: All major browsers with mouse support

---

## 🔧 Quick Tips
- Use gentle movements for subtle curve changes
- Combine mouse drag with physics adjustments for complex animations
- The simulation works offline after initial load
- Perfect for learning Bézier curves and physics simulations

## 🚀 Live Demo
**[https://hrishita-12.github.io/Interactive-B-zier-Curve-with-Physics-Sensor-Control/](https://hrishita-12.github.io/Interactive-B-zier-Curve-with-Physics-Sensor-Control/)**

---

## 🎮 CONTROLS

### 🌐 **Web Version (Desktop/Mobile Browsers)**
- **Drag Points**: Click/touch and drag P₁ or P₂ (yellow circles) to reshape the curve
- **Adjust Physics**:
  - **Stiffness Slider**: Controls spring resistance (0.01=soft, 0.2=stiff)
  - **Damping Slider**: Controls motion slowing (0.05=floaty, 0.2=sticky)
- **Reset**: Press `R` key to reset all points to original positions
- **Toggle Tangents**: Adjust "Tangents" slider to increase/decrease length of tangent vectors

### 📱 **iOS Version (iPad/iPhone)**
1. **Tap "Enable Motion"** button
2. **Grant permission** when iOS asks
3. **Tilt device** to apply forces:
   - **Tilt Forward** → Force moves points DOWN
   - **Tilt Backward** → Force moves points UP
   - **Tilt Left** → Force moves points LEFT
   - **Tilt Right** → Force moves points RIGHT
4. **Force intensity**:
   - Gentle tilts: Subtle forces
   - Sharp tilts: Strong forces
   - Flat surface: No motion force

---

## 📊 UNDERSTANDING THE DISPLAY

### **Physics Monitor**
- **P₁/P₂ Toggle**: Switch between monitoring points
- **Position (x,y)**: Current location on screen
- **Target (x,y)**: Resting position (where point wants to be)
- **Velocity**: Speed and direction of movement
- **Acceleration**: How quickly velocity is changing
- **Forces**: Visual vectors show spring/damping/net forces

### **Reading Force Vectors**
- 🔵 **Blue arrow (Fₛ)**: Spring force pulling toward target
- 🔴 **Red arrow (Fₔ)**: Damping force opposing motion
- 🟡 **Yellow arrow (Fₙ)**: Net force causing movement
- **Longer arrow = stronger force**

---

