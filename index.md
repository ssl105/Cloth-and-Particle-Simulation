# Background

Particle systems have various uses in graphics since it mimics the elementary particles in the real world. Particles can be used to simulate fire, water, explosions, and other phenomena. When particles are combined with different forces, they can be used to simulate fabric animations.

# Physics

In order to animate particles, we can use Newtonian mechanics to apply forces on the particle.

Using variables we can define a particles position over time as a function $$\mathbf{r}(t)$$ where $$t$$ is the time when a particle is in position $$\mathbf{r}(t)$$.\
Then the velocity $$\mathbf{v}$$ of the particle is the derivative of position:   
&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{v}(t) = \frac{\mathrm{d} \mathbf{r}}{\mathrm{d} t}$$.  
And the acceleration $$\mathbf{a}$$ is the derivative of the velocity:   
&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{a}(t) = \frac{\mathrm{d} \mathbf{v}}{\mathrm{d} t}$$

In the real world, gravity is constantly acting on every object. The constant acceleration from gravity is about $$9.81 \ m/s^{2}$$. So when a particle undergoes constant acceleration, we can derive the equation for distance:

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{a}(t) = \mathbf{a}_{0}$$.  
&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{v}(t) = \int{\mathbf{a}\mathrm{d}t} = \mathbf{v}_{0} + \mathbf{a}_{0}t$$.  
&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{r}(t) = \int{\mathbf{v}\mathrm{d}t} = \mathbf{r}_{0} + \mathbf{v}_{0}t + \frac{1}{2}\mathbf{a}_{0}t^{2}$$

$$\mathbf{a}_{0}$$ represents intial acceleration at time $$t = 0$$. Additionaly, $$\mathbf{v}_{0}$$ and $$\mathbf{r}_{0}$$ represent initial velocity and position.

We can assume each particle has a constant mass $$m$$. Momentum $$\mathbf{p}$$ is defined:

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{p} = m\mathbf{v}$$

Force is defined as the rate of change of momentum:

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{f} = \frac{\mathrm{d} \mathbf{p}}{\mathrm{d} t}$$

With constant mass this expands to:

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{f} = \frac{\mathrm{d} \mathbf{p}}{\mathrm{d} t} = \frac{\mathrm{d} (m\mathbf{v})}{\mathrm{d} t} = m\frac{\mathrm{d} \mathbf{v}}{\mathrm{d} t} = m\mathbf{a}$$

### Newton's Laws of Motion

- The first law states that an object in motion will stay in motion or object at rest will stay at rest unless acted upon by a force. From the equation $$\mathbf{r}(t) = \mathbf{r}_{0} + \mathbf{v}_{0}t + \frac{1}{2}\mathbf{a}_{0}t^{2}$$ we see that without a force acting on an object meaning $$\mathbf{a} = 0$$ the distance $$\mathbf{r}$$ will be dependent on the initial values $$\mathbf{r}_{0}$$ and $$\mathbf{v}_{0}$$.
- The second law defines force as:

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{f} = \frac{\mathrm{d} \mathbf{p}}{\mathrm{d} t} = m\mathbf{a}$$

- The third law states any force applied from body A to body B is met with an equal and opposite force:

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{f}_{AB} = -\mathbf{f}_{BA}$$

Since a particle can be subjected to many forces, the total force on a particle is simply the sum of all the forces:

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{f}_{total} = \sum{\mathbf{f}_{i}}$$

# Integration

In order to carry out the simulation, the position of each particle needs to be updated each frame. Integration is necessary since the distance $$\mathbf{r}(t)$$ is the integral of the velocity which is the integral of acceleration. However, not all functions can be analytically integrated. Therefore we must rely on numerical integration to approximate distances.

### Forward Euler Integration

The forwards euler integration uses the derivative to approximate the next value. To calculate the next velocity, we use the current acceleration of the particle mulitplied by the change in time added by the previous velocity:

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{v}_{i+1} = \mathbf{v}_{i} + \mathbf{a}_{i}\Delta{t}$$

To calculate the next distance, we use the new velocity we just calculated mulitplied by the change in time added by the previous distance:

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{r}_{i+1} = \mathbf{r}_{i} + \mathbf{v}_{i+1}\Delta{t}$$

# Basic Forces

### Gravity

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{f}_{gravity} = m\mathbf{g}_0$$

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{g}_0 = [0 \ -9.8 \ 0 ]\frac{m}{s^2}$$

### Aerodynamic Drag Force

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{f}_{drag} = \frac{1}{2}\rho\mid\mathbf{v}\mid^2c_da\mathbf{e}$$

- $$\rho$$ is the density of the fluid. The default density of air is $$1.225 kg/m^3$$. 
- $$\mathbf{v}$$ is the relative velocity so $$\mathbf{v} = \mathbf{v}_{particle} - \mathbf{v}_{fluid}$$. 
- $$\mathbf{e}$$ is a unit vector in the opposite direction of velocity: $$\mathbf{e} = -\frac{\mathbf{v}}{\mid\mathbf{v}\mid}$$

### Spring - Damper Force

# Particle Systems

# Cloth Simulation

# Video Demos

# Resources

{% include lib/mathjax.html %}
