---
layout: project
title: Nutcracker Design Analysis
description: ENGRD 2020 Statics OLHW5
technologies: Structure Analysis of Mechanical Advantage
image: /assets/images/nutcracker.jpg
---

For a Homework 4, we were given a design problem to create a device that could crack open a macadamia nut by hand using simple levers and our knowledge of mechanical advantage.

#### Find
Image you have a macadamia nut that you want to crack open by hand using a simple lever nut cracker. Draw a figure of the nut cracker with the nut when it’s about to crack. Calculate the necessary dimensions of the nutcracker and come up with a design to make this task feasible.

#### Given
![table of average nut hardness values]({{ "/assets/images/nut-hardness.png" | relative_url }}){: .inline-image-r style="width: 300px"}
![table of average grip strength for men and women]({{ "/assets/images/grip-strength.png" | relative_url }}){: .inline-image-r style="width: 300px"}

From the first graph, we can see that the average force to crack a macadamia nut is around 225 kg, or 2205 N. A quick google search states that the average size of macademia nuts is about 25 mm.
The second chart shows average grip strengths for men and women across various ages. For the sake of analysis, I chose 40 kg or 392 N as the max grip strength exerted on the nutcracker.

#### Plan
Average force to crack the macadamia nut: 2205 N
Average size of the macadamia nut: 25 mm
Max grip strength: 392 N

Mechanical advantage is described by the following equation:
$$MA = \frac{F_\text{out}}{F_\text{in}}$$
Assuming $F_\text{out}$ is the force required to crack the nut and $F_\text{in}$ is the grip force applied to the lever, we get a MA value of 5.62

#### Solve
To make this a conservative model, I rounded up to MA=6

The following is a free body diagram showing the mechanism of the nutcracker:
![FBD of nutcracker]({{ "/assets/images/nutcracker-fbd.png" | relative_url }}){: .inline-image-l}

Using a moment balance, we get the equation
$$\sum M_o = 0 = F_G(d) - F_N(20\ \text{mm})$$
Where $F_G$ is the grip strength and Force In, $F_N$ is the force to crack the nut and Force Out, and $d$ is the distance from joint $O$ to the location of the applied force.

Solving this, we get 120 mm, or ~5 inches

#### Discussion
This design is feasible but not entirely accessible. The nutcracker is relatively small and would require a fairly substantial amount of grip strength for most women. Making the arms of the nutcracker longer would increase the mechanical advantage and require less grip force to crack the macadamia nut.