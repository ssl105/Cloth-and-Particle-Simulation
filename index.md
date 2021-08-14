# Background

Particle systems have various uses in graphics since it mimics the elementary particles in the real world. Particles can be used to simulate fire, water, explosions, and other phenomena. When particles are combined with different forces, they can be used to simulate fabric animations.

# Physics

In order to animate particles, we can use Newtonian mechanics to apply forces on the particle.

Using variables we can define a particles position over time as a function $$\mathbf{r}(t)$$ where $$t$$ is the time when a particle is in position $$\mathbf{r}(t)$$.\
Then the velocity $$\mathbf{v}$$ of the particle is the derivative of position:\
&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{v}(t) = \frac{\mathrm{d} \mathbf{r}}{\mathrm{d} t}$$\
And the acceleration $$\mathbf{a}$$ is the derivative of the velocity:\
&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{a}(t) = \frac{\mathrm{d} \mathbf{v}}{\mathrm{d} t}$$

In the real world, gravity is constantly acting on every object. The constant acceleration from gravity is about $$9.81 \ m/s^{2}$$. So when a particle undergoes constant acceleration, we can derive the equation for distance:

&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{a}(t) = \mathbf{a}_{0}$$\
&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{v}(t) = \int{\mathbf{a}\mathrm{d}t} = \mathbf{v}_{0} + \mathbf{a}_{0}t$$\
&nbsp;&nbsp;&nbsp;&nbsp;$$\mathbf{r}(t) = \int{\mathbf{v}\mathrm{d}t} = \mathbf{r}_{0} + \mathbf{v}_{0}t + \frac{1}{2}\mathbf{a}_{0}t^{2}$$

$$\mathbf{a}_{0}$$ represents intial acceleration at time $$t = 0$$. Additionaly, $$\mathbf{v}_{0}$$ and $$\mathbf{r}_{0}$$ represent initial velocity and position.

{% include lib/mathjax.html %}
