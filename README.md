# Satellite Orbit Decay Model

A Python model that estimates how long a satellite stays in orbit before atmospheric drag causes it to re-enter, based on its starting altitude, mass, and cross-sectional area.

## Overview

Satellites in low Earth orbit experience drag from the upper atmosphere, which slowly lowers their altitude over time. This project models that decay process using atmospheric density and orbital mechanics calculations, then tracks altitude over time until the satellite reaches ~180 km (considered re-entry).

The notebook walks through:

- **A baseline model** of the International Space Station's decay
- **Varying starting altitude** (200–500 km) to see its effect on orbital lifespan
- **Varying cross-sectional area** (0.1–5 m²) to see how drag surface affects decay rate
- **Varying satellite mass** (10–500 kg) to see how mass affects decay rate

Each experiment is visualized as a plot of altitude vs. time.

## Key findings

- **Higher starting altitude** → longer orbital lifespan
- **Smaller cross-sectional area** → longer orbital lifespan (less drag)
- **Higher mass** → longer orbital lifespan (more inertia relative to drag force)

## How it works

The model uses:
- Atmospheric temperature and density estimated from solar radio flux (F10.7) and geomagnetic index (Ap)
- Orbital period calculated from semi-major axis
- Rate of change of orbital period due to drag, based on satellite mass, drag coefficient, and cross-sectional area
- An iterative hour-by-hour simulation that updates altitude until the satellite decays below 180 km

## Sources

Bureau of Meteorology. *Satellite Orbital Decay Calculations.* Space Weather Services.

## Getting started

### Requirements

Install dependencies with:

```bash
pip install -r requirements.txt
```

### Running

Open the notebook and run all cells:

```bash
jupyter notebook notebooks/satellite_orbit_decay.ipynb
```

## Project structure

```
satellite-orbit-decay/
├── README.md
├── LICENSE
├── requirements.txt
└── notebooks/
    └── satellite_orbit_decay.ipynb
```

## Background

This project was originally built as an independent final project for a course assignment. The idea, modeling approach, and implementation are my own work.
