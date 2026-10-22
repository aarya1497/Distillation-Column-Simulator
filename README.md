# Distillation-Column-Simulator
Binary Distillation Column Simulator 🧪

Developer: Aarya Mengle
Institution: BITS Pilani, Dubai Campus — B.E. Chemical Engineering
Method: McCabe-Thiele Graphical Method
Language: Python (Google Colab / Jupyter Notebook)

📌 What This Project Does

This simulator models a binary distillation column — one of the most fundamental unit operations in chemical engineering. Given feed composition, desired product purity, reflux ratio and relative volatility, it:

Plots the equilibrium curve based on vapour-liquid equilibrium (VLE)
Draws the rectifying and stripping operating lines
Automatically steps off theoretical stages using the McCabe-Thiele method
Displays the number of theoretical plates required
Provides interactive sliders to change parameters in real time

Element	Colour	Description
Equilibrium Curve	🔵 Blue	VLE relationship between liquid and vapour
45° Line	⬛ Black dashed	Reference line (x = y)
Rectifying Line	🔴 Red	Operating line — top section of column
Stripping Line	🟢 Green	Operating line — bottom section
Feed Line	🟣 Purple	Where feed enters the column
Stage Staircase	🟠 Orange	Each step = one theoretical plate
⚙️ Input Parameters
Parameter	Symbol	Default	Description
Relative Volatility	α	2.5	Ease of separation between components
Feed Composition	zF	0.50	Mole fraction of component A in feed
Distillate Purity	xD	0.95	Desired top product purity
Bottoms Composition	xB	0.05	Maximum allowable bottoms composition
Reflux Ratio	R	3.0	Ratio of liquid returned vs product taken
📈 Sample Results

For default inputs (α=2.5, R=3.0, xD=0.95, xB=0.05, zF=0.5):

Theoretical Stages Required: 9
Feed Stage: Stage 5

Effect of changing parameters:

Increase R (reflux ratio) → fewer stages, more energy
Increase xD (distillate purity) → more stages required
Increase α (volatility) → fewer stages (easier separation)
Change zF (feed composition) → shifts feed stage location
🧮 Key Equations

Equilibrium Curve (VLE):

y* = αx / (1 + (α-1)x)

Rectifying Operating Line:

y = (R/R+1)x + xD/(R+1)

Stripping Operating Line:

y = (L'/V')x - xB(L'/V' - 1)

Stage Stepping Algorithm:

1. Start at distillate point (xD, xD)
2. Go horizontally LEFT to equilibrium curve
3. Drop vertically DOWN to operating line
4. Repeat until bottoms composition xB is reached
5. Count steps = theoretical stages
🛠️ Libraries Used
python
import numpy as np          # Numerical calculations
import matplotlib.pyplot    # Plotting
import ipywidgets           # Interactive sliders
🚀 How to Run
Option 1 — Google Colab (Recommended)
Open Google Colab
Upload the .ipynb file
Run all cells (Runtime → Run All)
Use sliders to interact
Option 2 — Jupyter Notebook
bash
pip install numpy matplotlib ipywidgets
jupyter notebook Distillation_Simulator.ipynb
Option 3 — VS Code
bash
pip install numpy matplotlib ipywidgets
# Open .ipynb file in VS Code with Jupyter extension
📚 Chemical Engineering Context

Distillation is the most widely used separation process in the chemical industry — used in:

Petroleum refining (crude oil separation)
Pharmaceutical manufacturing
Petrochemical production
Agrochemical processing
Alcohol production

The McCabe-Thiele method is a fundamental design tool taught in every chemical engineering curriculum worldwide. This simulator applies the graphical method computationally, allowing rapid analysis of different operating conditions.

🔮 Future Improvements
 Multi-component distillation (3+ components)
 Murphree tray efficiency
 Minimum reflux ratio calculation
 Energy balance integration
 Aspen HYSYS validation comparison
 Export results to PDF report
👩‍💻 About the Developer

Aarya Mengle is a Chemical Engineering student at BITS Pilani Dubai with interests in process simulation, machine learning applications in chemical engineering, and process safety.

🔗 LinkedIn
🎓 BITS Pilani Dubai | B.E. Chemical Engineering (2025–2029)
🏛️ AIChE Student Member
