# Discrete-Time (DT) Systems

 [[MIT6.003.Lec1#The 6.003 Abstraction]]

DT learning transfers to CT learning
Taking a look at difference equations and block diagrams

## Difference Equations
$$y[n] = x[n] - x[n-1]$$
Let $x [n]$ equal the "unit sample" signal $\delta [n]$ where it equals 1 at n = 0 and 0 otherwise. 
- Domain is also $-2<n$
We use the unit sample signal as a primitive (building block signal) to construct more complex  signals

A block diagram can be used to represent the configuration of hardware.