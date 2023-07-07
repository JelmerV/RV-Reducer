# RV reduces

The RV reduces is an improved version of the cycloidal drive. It fixes the weakest part of a typical cycloidal drive: the eccentric shaft. Instead it has three shaft, driven by spur gears, this adds an additional stage allowing even higher reductions. These three eccentric shafts cause the cycloidal disc to wobble in place. This causes the outer ring to rotate, meaning the outer cyclidal gear form the output.

With an ideal cycloidal gear, all teets are in contact at the same time, this gives it a high shock absorptions, and is a large advantage. esspecially when this gear is made of softer materials, such as in a 3d printed version. They often have very low backlash and friction, making them back-drivable even at very high reductions.

## The design

### Cycloidal disks

The disk requires a very specific design defined by 3 parameters

- R_d: radius of the outer gear
- R_p: radius of the rollers (pins in the outer hub)
- E: eccentricity of the rotor (how much does it wobble back and forth?)
- N: number of rollers (reduction will be N)

These parameters are entered into the following equations (functions of t):

$$X = R_d*cos(t) - R_p * cos(t+\frac{arctan(sin((1-N)*t)}{(R_d/E*N)-cos((1-N)*t)}) - E*cos(N*t)$$
$$Y = -R_d*sin(t) + R_p*sin(t+ \frac{arctan(sin((1-N)*t)}{(R_d/E*N)-cos((1-N)*t)}) + E*sin(N*t)$$

Or in a form that can be pasted into Solidworks parametric equations:
```
X = ( "Rd"*cos(t)) - ("Rp"*cos(t + arctan(sin((1-"N")*t)/(("Rd"/("E"*"N"))-cos((1-"N")*t))) )) - ("E"*cos("N"*t))
Y = (-"Rd"*sin(t)) + ("Rp"*sin(t + arctan(sin((1-"N")*t)/(("Rd"/("E"*"N"))-cos((1-"N")*t))) )) + ("E"*sin("N"*t))
```

The result is an ideal cycloidal disk. The outer gear can be modeled as $N$ pins spaced evenly accross a circle of radius $R_d

### Housing

The housing uses the same parameters.
