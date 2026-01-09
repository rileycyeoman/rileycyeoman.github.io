---
title: Stepped Foam Panel Calculator
layout: home
parent: MultiTool
nav-order: 3
---
{: .text-center }
### <u>Stepped Panel Foam Calculator</u>
--- 
<img
  style="display:block;margin-left:auto;margin-right:auto;"
  src="{{ site.baseurl }}/images/StepPanelDim3.png"
  alt="PIC Valve">

Stepped Panel design foam calcualtion. This calculator outputs the volume, costs, and shot times for a given panel design. The inputs are length, width, and depth. Depth is relagated to 2", 3", and 4", as there will be no deviation from these depths in production.


#### Variables
---
<script>
window.MathJax = {
  tex: {
    inlineMath: [['$', '$'], ['\\(', '\\)']],
    displayMath: [['$$', '$$'], ['\\[', '\\]']]
  }
};
</script>

<script
  src="https://cdn.jsdelivr.net/npm/mathjax@3/es5/tex-chtml.js"
  async>
</script>
The following are the current variables that are kept constant in the code:
- $\rho_{steel} = 0.284\frac{lb}{in^3}$, Density of steel 
- $\rho_{foam} = 2.5\frac{lb}{ft^3}$, Foam Density
- $22ga = 0.03\text{"}$, Steel gauge
- $\text{Thickness} = 2 * Gauge$, Both sides of panel to be subtracted from length  
- Foam Ratio: $ ratio = 0.47$
-  Inner Flange:
$$
\text{Inner Flange} = \begin{cases}
    0.73\text{"} & \text{if } Depth = 2\text{"} \\ 
    1.64\text{"} & \text{if } Depth = 3\text{"} \\ 
    2.64\text{"} & \text{if } Depth = 4\text{"} 
\end{cases}
$$
- Depth of outer panel: $\text{outer\_depth} = 1.138\text{"}$ 
- Offset $= 0.255\text{"}$, Distance from inner to outer panel
- $cut\_out =  4 * 17.4 in^2$. Cutout of sheet metal, this is the total surface area of hypothetical rectangular sheet metal minus the true value. This is essentially the sheet metal minus the corners.



#### Formulas
---
<u>Interior Volume of Outer Panel</u>
$$ \text{Outer Length} = \text{Length} - \text{Thickness} -  \text{Bend Deduction}$$ 
$$ \text{Outer Width} = \text{Width} - \text{Thickness} -  \text{Bend Deduction}$$
$$ \text{Outer Volume} = \text{Outer Length} * \text{Outer Width} *  \text{Outer Depth}$$


<u>Interior Volume of Inner Panel</u>
$$ \text{Inner Length} = \text{Length} - \text{Thickness} -  \text{Bend Deduction}$$ 
$$ \text{Inner Width} = \text{Width} - \text{Thickness} -  \text{Bend Deduction}$$
$$ \text{Inner Volume} = \text{Inner Length} * \text{Inner Width} *  \text{Outer Depth}$$