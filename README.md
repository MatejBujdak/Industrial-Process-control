# Industrial-Process-control
PLC &amp; HMI simulation – Siemens TIA Portal

# Conveyor Bottle Line – PLC & HMI Simulation (Siemens TIA Portal)

Simulated conveyor-based bottle production line controlled by Siemens PLC logic with HMI (WinCC Advanced/Comfort style screens).
The project demonstrates architecture and typical industrial features: Auto/Manual modes, sequence control (GRAPH), interlocks, alarms, E-STOP, soft stop, recipes, PID control, and production statistics.

## Features
- **Auto / Manual mode**
- **Conveyor motor control** (forward/reverse in manual, hold-to-run)
- **Sequence control in GRAPH** (stations: Start → Fill → Cap → Label → End)
- **Interlocks & supervision** (safe start conditions, station readiness)
- **Fault handling** (alarm state + reset workflow)
- **E-STOP simulation** (immediate stop, requires release + reset)
- **Soft stop** (finish current piece, then stop safely)
- **Recipe system** (temperature + tank fill setpoints)
- **PID control** (temperature + liters)
  - PID tuning available from HMI
  - technology behavior simulated in **SCL** (pump inflow + outflow disturbance during filling)
- **Station enable/disable during run**
- **Production statistics**
  - daily counts by weekday
  - production stop counter
  - last restart timestamp
- **HMI template/permanent area**
  - Home, alarms, production info, system info
  - user login / authorization (admin/operator roles)
  - language switch, HMI shutdown

## Screenshots
> (See `/screenshots`)

- Main screen – Conveyor overview, Auto/Manual, Start/Stop/Reset
- Start/Stop confirmation dialogs
- PID screen – trends, parameters, tuning
- Recipe screen – record selection and values
- Info screen – daily counts, stops, last restart
- User management – groups/rights
- System info – HMI/PLC IP address overview

## How it works (short)
1. If **interlock conditions** are OK, the line can start.
2. Conveyor moves the bottle between stations.
3. **GRAPH** controls the step sequence and triggers station actions based on sensors/conditions.
4. Filling station uses **recipe parameters** and **PID regulation** for temperature and tank level.
5. Faults or E-STOP move the system into error state until **released + reset**.
6. Counters and timestamps are stored and displayed on HMI screens.

## Tech stack
- Siemens **TIA Portal**
- **GRAPH** for sequence
- **SCL** for technology simulation
- WinCC HMI screens + template/permanent area
- Faceplates for controllers/objects

## Project files
Because TIA/WinCC projects can be large, the repository focuses on documentation + screenshots + code samples.
If you need the full project archive, contact me.
