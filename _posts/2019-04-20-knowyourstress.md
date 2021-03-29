---
usemathjax: true
title: "Mechanics of Materials Review - Bending, Shear, and Axial Stresses"
categories:
  - Structural-Engineering
---


One thing I struggled with as I started working in structural engineering was having a complete, and comprehensive understanding of where stresses occur and how they interact with each other. This really comes in handy when it comes to determining boundary conditions and design connections, especially welds. 


>  I am an MC over I enginer.

The above quote was told to me by a senior technical lead when I was starting out, and it has since followed me through all the work I've done. I mention this because many engineers don't understand how critical knowledge of the fundamentals are - a mentality that inevitably leads to *garbage in garbage out* design.
## Key Concepts

### Bending Stress
This is literally what it sounds like - you bend something, stresses will result in that thing, usually at the top and bottom or sides of the section (shape). 

![Image of Bending Stress Distribution]({{ '/assets/images/bendingdistribution.png' | prepend: site.baseurl | prepend: site.url }} "Bending Stress Distribution")

This is the flexural stress distribution of a section, as you can see the stresses are highest at the top and the bottom and they are zero in the center - that is the neutral axis. The fact that the stresses point in either direction mean that one side is in tension and the other is in compression.

> To visualize how this works take a pencil, grab it with both hands, put your thumbs to the center, and apply force. The side opposite your thumbs is in tension and the side your thumbs are pressing on is in compression. This happens because the force you are applying to the center of the pencil is causing a bending moment in the pencil.

We'll now look exactly how to calculate bending stress. We will use the variable f with subscript b to represent bending stress ($f_b$), although you will find many books use sigma ($\sigma$) or other variables in their nomenclature. Equation 1 below 

$$\begin{equation} f_b =\frac{Mc}{I} \end{equation}$$

$${M =} \text{ Bending Moment}$$

$${c =} \text{ Distance to the Point to extreme fiber from the Neutral Axis}$$

$${I =} \text{ Second Moment of Area }$$

Equation 1 is the classic formula for determining bending stress in a beam based Euler-Bernoulli Beam Bending Theory. The implication here is that if you know that given you know the section properties of an element and the stress being applied, you can calculate the stress at any point. 

### Shear Stress

Shear stress can be a bit more difficult to visualize and understand then bending stress. Both stresses occur from a force acting ona nelement however with shear stress the main idea  is that the stress is acting across the face of a material rather than towards the face like with bending stress. 

![Image of Shear Stress Distribution]({{ '/assets/images/sheardistribution.png' | prepend: site.baseurl | prepend: site.url }} "Shear Stress Distribution")

This is the shear stress distribution of a section, you can see that the highest concentration of shear is in the center of the section and the lowest is on the top of the section - opposite of bending stress. 

> Remember the pencil you just pushed against with your thumbs? That was also seeing shear stress. In fact, if you were to continue to apply more force, it would break in one of two ways: the wood fibers in the top or bottom of the pencil would reach their yield point and rip apart, or the whole section would "cut" across do to the high concentration of shear.

We'll now look exactly how to calculate shear stress. We will use the variable f with subscript v to represent shear stress ($f_v$), although you will find many books use tau ($\tau$) or other variables in their nomenclature. Equation 1 below 

$$\begin{equation} f_v =\frac{VQ}{Ib} \end{equation}$$

$${V =} \text{ Shear Force}$$

$${Q =} \text{ First Moment of Area}$$

$${b =} \text{ Width of Section (Perpendicular to Shear) }$$

$${I =} \text{ Second Moment of Area }$$

### Axial Stress

Axial stresses seem to be the easiest to understand (at least they always were for me). These stresses occur along the longitudinal axis of whatever your are pulling or pushing on. 

![Image of Axial Stress Distribution]({{ '/assets/images/axialdistribution.png' | prepend: site.baseurl | prepend: site.url }} "Axial Stress Distribution")

This is the axial stress distrbution of a section. Simple right? It occurs uniformly over the shape of a section, just the force over the area.

> Grab your pencil again. This time don't place your thumbs on the center of the pencil, but rather, place both hands on it and pull them away from each other as hard as you can. You can imagine that if you were superman, you would pull the pencil so hard that it would split apart. Axial stress.

$$\begin{equation} f_a =\frac{N}{A} \end{equation}$$

$${N =} \text{ Axial Force}$$

$${A =} \text{ Area}$$

## Example
### Problem
Consider a simply supported beam with a load acting at the center and an axial load at the end. Calculate the maximum bending, shear, and axial stresses.
![Image of Example 1]({{ '//assets/images/example1.png' | prepend: site.baseurl | prepend: site.url }} "Example Problem")

### Solution
The reactions for the beam are resolved as follows:

![Image of Example 1]({{ '/assets/images/example1reactions.png' | prepend: site.baseurl | prepend: site.url }} "Example Problem")

**Beam Properties:**

$$b = 18in$$

$$h = 30in$$

$$c = \frac{h}{2} = 15in$$

$$A = b*h = 18in * 30in = 540 in^2$$

$$Q =\frac{A}{2} * \frac{h}{4} = \frac{18in*30in}{2} * \frac{30in}{4} = 2025 in^3$$

$$I =\frac{bh^3}{12} =  \frac{18in*(30in)^3}{12} = 40500in^4$$

**Maximum Forces in Beam:**

Axial Force: $$ N = 10 kip $$

Shear Force: $$ V = 2.5 kip $$

Bending Moment: $$ M =\frac{P * L}{4} = \frac{5 kip * 20ft}{4} = 25 kip*ft $$

**Maximum Stresses in Beam:**

Axial Stress: $$f_a =\frac{N}{A} = \frac{10 kip}{540 in^2} = 0.018 ksi$$

Shear Stress: $$f_v =\frac{VQ}{Ib} = \frac{2.5 kip * 2025 in^3}{40500 in^4 * 18in} = 0.007 ksi$$

Bending Stress: $$f_b =\frac{Mc}{I} = \frac{25 kip*ft * 15 in}{40500 in^4} = 0.009 ksi$$