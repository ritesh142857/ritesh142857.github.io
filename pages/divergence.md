---
layout: article
title: The Elegance of Divergence
---

<h2>The Elegance of Divergence</h2>
<hr>
Gauss's Law is one of the best examples to show how intricately the bonds between Mathematics and Physics are woven. The Classical Electromagnetic Theory was the first physical theory to be successfully described using mathematics, in particular, using the language of vector calculus. One of the most interesting property of a vector field is its divergence. In electrostatics, one form of Gauss's Law states that the divergence of the electric field at any point is proportional to the charge density at that point. The integral form states that the surface integral of the electric field about a closed surface is proportional to the charge enclosed by that surface. The Divergence Theorem relates the two forms of the law. The usefulness of this law is clearly seen when trying to find the electric fields of symmetric charge distributions. But Gauss's law is more subtle and intrinsic to the electromagnetic theory than that.

First, it is important to note that the divergence of a vector field is always defined at a particular point. Now, the implications of Gauss's law are entirely due to its mathematical structure. To be specific, the divergence term in the Gauss's law is what makes it special. It is a known fact that the divergence of an inverse-square field is 0 everywhere except at the origin, where the field blows up. So, the divergence in this case is actually equal to a mathematical function called the Dirac delta function.
<br>
      $$\nabla.(\hat{r}/\overline{r}^2) = 4\pi\delta^3(\overline{r})$$

The Gauss's law states that,
<br>
      $$\nabla.\overline{E} = \rho/\epsilon_{0}$$

where 'ρ' is the charge density in the region. Coulomb's law states that,
<br>
<center>$$\overline{E} = q/4\pi\epsilon_{0}r^2$$</center>

Observing the first two divergence equations, the similarity between them is quite clear. According to the Gauss's law equation, the source which is the charge density on the right hand side produces the electric field on the left hand side of the equation. So in order to produce a field of form given in the third equation, the charge density would have to be proportional to the delta function. This kind of charge density is simply a point charge. So any point charge produces an electric field which is inverse-square in nature. This is nothing but the Coulomb's law, which was formulated based purely on observations! The Coulomb's law is therefore contained in the Gauss's law. Another very interesting point about divergence is the following. The divergence always refers to the divergence of the vector field at a particular point. So going by Gauss's law, if the divergence of the electric field at a point is 0, then there is no charge at that point. Therefore, the divergence can be thought of as some sort of scanning operation to check if charge is present at a point or not*.

<center><img src="../cap_picture.png"></center>

Take the example of a parallel plate capacitor. The electric field between the plates of the capacitor is uniform going from the positive plate to the negative plate. If the divergence of this field is calculated between the plates, then the result will be 0 as expected i.e. there is no charge in the region between the plates. Now, suppose that a point charge is placed between the plates which is somehow tightly held in its position so that it is immovable. If we now calculate the divergence of the electric field between the plates, the result will not be 0. This is because the point charge produces an inverse-square divergent field which vectorially adds to the uniform field due to the plates resulting in an electric field with non-zero divergence.

This clearly shows how elegantly mathematical the world around us is.

<script type="text/javascript" async
  src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-MML-AM_CHTML">
</script>
