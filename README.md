# INVICTUS II – Flight Simulation (RocketPy)

## 🧭 Objective

Flight simulation is critical to guarantee the **safety**, **performance**, and **optimization** of a rocket before any real launch. For INVICTUS II, simulations ensure:

- ✅ Compliance with EuRoC requirements (e.g., 30 m/s rail exit speed, 3000 m apogee)
- 🔧 Rocket optimization through parametric studies
- 🔒 Safe launch operation

---

## 🚀 RocketPy

[**RocketPy**](https://github.com/Projeto-Sirius/RocketPy) is an open-source Python library for 6-DOF rocket flight simulation. INVICTUS II uses the following RocketPy classes:

- `Environment` – atmospheric conditions
- `Motor` – hybrid propulsion configuration
- `Rocket` – rocket structure and aerodynamics
- `Flight` – simulation execution and results

---

## 🔥 Motor Configuration (Hybrid)

### Tank Geometry

| **Tank Geometry** | **Value**       |
|-------------------|-----------------|
| Type              | Cylindrical     |
| Radius            | 0.0815 m        |
| Height            | 0.550 m         |
| Spherical Caps    | YES             |

### Oxidizer Properties

| **Fluids**             | **Value**                           |
|------------------------|-------------------------------------|
| Oxidizer Liquid        | N₂O 785.1 kg/m³ (20 °C)              |
| Oxidizer Gas           | N₂O 157.99 kg/m³ (20 °C)             |
| Flux Time              | 4.2 s                               |
| Initial Liquid Mass    | 6.3 kg                              |
| Initial Gas Mass       | 0 kg                                |
| Liquid Flow Out        | 1.5 kg/s                            |

### Solid Fuel Grain

| **Grain**            | **Value**    |
|----------------------|--------------|
| Number               | 1            |
| Outer Radius         | 0.0575 m     |
| Initial Inner Radius | 0.020 m      |
| Height               | 0.35 m       |
| Density              | 888 kg/m³    |

### Motor Configuration

| **Hybrid Motor**             | **Value**                              |
|-----------------------------|----------------------------------------|
| Dry Mass                    | 21.5 kg                                |
| Inertia (xx, yy, zz)        | (6.635, 6.635, 0.06135) kg·m²          |
| Nozzle Throat Radius        | 0.030 m                                |
| Tank Position               | 1.345 m                                |

---

## 🧩 Rocket Assembly

### Drag Coefficient Table (Mach-based)

| Mach Number | C<sub>d</sub>   |
|-------------|-----------------|
| 0.1         | 0.301532        |
| 0.2         | 0.285133        |
| 0.3         | 0.273940        |
| 0.4         | 0.265850        |
| 0.5         | 0.259435        |
| 0.6         | 0.254271        |
| 0.7         | 0.249975        |
| 0.8         | 0.246279        |

### General Specs

| **Structure**     | **Value**                      |
|-------------------|--------------------------------|
| Radius            | 0.0815 m                       |
| Mass              | 20.0 kg                        |
| Center of Mass    | 2.09 m                         |
| Inertia           | (31.99; 31.99; 0.2049)         |

### Components

| **Nose Cone**     | **Value**     |
|-------------------|---------------|
| Length            | 0.385 m       |
| Type              | Von Karman    |

| **Fins**          | **Value**     |
|-------------------|---------------|
| Quantity          | 4             |
| Root Chord        | 0.28 m        |
| Tip Chord         | 0.14 m        |
| Span              | 0.160 m       |
| Position          | 3.45 m        |

| **Tail**          | **Value**     |
|-------------------|---------------|
| Top Radius        | 0.0815 m      |
| Bottom Radius     | 0.058 m       |
| Length            | 0.121 m       |
| Position          | 3.75 m        |

### Rail Buttons

| **Position**      | **Value**     |
|-------------------|---------------|
| Upper             | 1.306 m       |
| Lower             | 2.8635 m      |
| Angle             | 45°           |

### Parachutes

| **Parachute** | **Trigger** | **C<sub>d</sub>S** | **Lag** | **Sampling** |
|---------------|-------------|--------------------|--------|---------------|
| Main          | 450 m       | 13.8991            | 1 s    | 10 Hz         |
| Drogue        | Apogee      | 0.7354             | 1 s    | 10 Hz         |

---

## 📈 Flight Parameters

| **Launch Rail** | **Value**         |
|------------------|-------------------|
| Length           | 12 m              |
| Inclination      | 84° ± 1°          |
| Heading          | 0°                |

---

## 📊 Results (Preliminary)

> Note: This simulation does not yet reflect the dual-tank system of INVICTUS II. Final CAD and physical data are under development.

| **Parameter**             | **Value**     |
|---------------------------|---------------|
| Apogee                    | 2996.41 m     |
| Min. Stability Margin     | 2.108 c       |
| Max. Stability Margin     | 2.816 c       |
| Vertical Impact Velocity  | –7.22 m/s     |
| Rail Exit Velocity        | 33.2 m/s ✅    |

---

## 🔮 TODO

- Implement two-tank hybrid simulation
- Conduct Monte Carlo dispersion analysis for risk assessment
