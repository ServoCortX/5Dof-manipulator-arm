# 5DOF Manipulator Arm (MG996 Servos)

A simple 5-DOF manipulator built with MG996 servos. The arm uses five servos for the main joints and one servo for the gripper.

## Features
- 5 DOF: base yaw, shoulder, elbow, wrist pitch, wrist roll
- Gripper controlled by one servo
- Simple inverse-kinematics (geometric) for 2D planar arm + base rotation
- Demo motion sequence included

## Files
- `Manipulator5DOF.ino` — Arduino sketch (inverse kinematics + demo)
- `images/` — prototype photos and wiring pictures
- `README.md` — this file

## Hardware
- 6 × MG996 servos
- Arduino Uno / Nano / Mega (any)
- External 5–6V power supply for servos (recommended with sufficient current)
- Power distribution (avoid powering all servos from Arduino 5V)
- Wires, screws, 3D-printed parts or structure

## Setup
1. Connect servos to the pins defined in `Manipulator5DOF.ino`.
2. Provide a stable external 5–6V supply for the servos and common ground with Arduino.
3. Tune geometry values (`L1`, `L2`, `L3`) to match measured link lengths.
4. Tune `offset*` and `inv*` values so that neutral pose matches `offset` values.
5. Test with no load and small movements first.

## Calibration tips
- Manually move the arm to a known neutral position and adjust offsets so servo angles read as expected.
- Use small incremental movements when tuning to prevent mechanical collisions.
- Reduce `steps` or `moveDelay` in `moveToPose` for faster or slower movement.

## Safety & Disclaimer
This project is for educational and prototyping use only. **Do not** use this or similar setups for any medical, surgical, or human-contact critical tasks. Servo-driven hobby arms lack the safety, sensing, precision, and certification required for medical procedures. Use responsibly and test in a safe environment.

## Next steps
- Add limit switches or sensors for safer operation
- Log the current positions and implement closed-loop control
- Create a Python simulator to visualise workspace before hardware motion
