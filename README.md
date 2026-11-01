# Asynchronous State Estimation and Lyapunov-Constrained Predictive Tracking for a Voltage-Limited Differential-Drive Robot

[Asynchronous State Estimation and Lyapunov-Constrained Predictive Tracking for a Voltage-Limited Differential-Drive Robot](asynchronous-state-estimation-and-lyapunov-constrained-predictive-tracking-for-a-voltage-limited-differential-drive-robot.pdf) (PDF, 35 pages)

This is the culmination of my work in robotics. It treats localization and path tracking for a VEX V5 drivetrain as one mathematical problem, with derivations throughout.

- Localization: an exact pose update, a bound on the error from sensors that disagree in time, and a geometric test for when range sensors can't determine the robot's pose.
- Tracking: a strict Lyapunov function for the RAMSETE controller, and a predictive controller built on it that plans directly in wheel voltages.
- Saturation: a clock that slows the reference when the motors run out of voltage, so the robot stays on the drawn path.
- Stability: a guard that makes each planned step reduce the tracking error, with a local stability result.

### Results

All results are simulated. Nothing in the paper has been tested on a real robot.

- The predictive controller had the lowest path error of the three controllers compared, across all 8 test conditions and all 11 sensitivity tests.
- RAMSETE ended closer to the target in one test, with a slower speed filter.
- Instruction counts on an emulated V5 processor put the controller under 1% of its 10 ms cycle. The full localization system may overrun its 5 ms cycle with 300 particles. These are estimates, not measurements on a brain.

### How it was made

The problems and requirements came from my experience programming VEX robots and from my earlier robot code. I decided to combine predictive control and RAMSETE into one controller, required that the result be cheap enough to run on the V5 brain, directed the project at each step, and tested and challenged the results throughout. The derivations, software and text were developed with Claude, an AI system by Anthropic, under my direction. The proofs have not been independently reviewed.
