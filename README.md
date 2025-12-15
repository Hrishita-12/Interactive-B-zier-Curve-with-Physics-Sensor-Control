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
## 📐 **Mathematical Foundation**

### **Cubic Bézier Equations**
The curve is defined by four control points (P₀, P₁, P₂, P₃) using Bernstein polynomials:
B(t) = (1-t)³·P₀ + 3(1-t)²·t·P₁ + 3(1-t)·t²·P₂ + t³·P₃
Where `t ∈ [0,1]` parameterizes the curve from start to end.

### **Tangent Calculation**
The derivative (tangent) at any point `t`:
B'(t) = 3(1-t)²(P₁-P₀) + 6(1-t)·t(P₂-P₁) + 3t²(P₃-P₂)
Normalized to show direction vectors along the curve.

### **Implementation Details**
- 200 segments for smooth rendering
- Real-time recalculation on point movement which is shown on physics monitor.
- Visual tangents updated dynamically


---

## ⚛️ **Physics Model**

### **Spring-Mass-Damper System**
Each draggable point (P₁, P₂) behaves as a mass connected to its rest position by a spring-damper:
Fₛ = -K·(x - x₀) (Spring force - Hooke's Law)
Fₔ = -D·v (Damping force - viscous friction)
Fₙ = Fₛ + Fₔ (Net force)
a = Fₙ / m (Newton's Second Law)

### **Parameters**
- **K (Stiffness)**: 0.01-0.2 (controls spring tension)
- **D (Damping)**: 0.05-0.2 (controls energy dissipation)
- **m (Mass)**: 1.0 kg (fixed for simplicity)
- **dt**: 1/60 s (fixed timestep for stability)

### **Numerical Integration**
Using Euler integration for real-time performance:
v += a·dt
x += v·dt

### **External Forces**
- **Mouse/Touch**: Direct position override when dragging
- **Device Motion**: Tilt-derived acceleration forces

---

## 🎨 **Design Choices**

### **Visual Hierarchy**
1. **Primary Curve** (#8e80ed with 4px stroke): Main focus
2. **Control Points**: 
   - Yellow (#fbbf24): Draggable points P₁/P₂
   - Green (#10b981): Fixed endpoints P₀/P₃
3. **Guidelines**: Dashed white lines showing control polygon
4. **Force Vectors**: Color-coded for immediate understanding
5. **Tangents**: Red (#f72585) showing curve direction

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

