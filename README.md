1. GAM Baseline
\[
\log(N_t) = \alpha + s(Y_t) + \epsilon_t
\]

2. Month Baseline Growth
\[
g(t) = \log N^0(t+1) - \log N^0(t)
\]

3. GAM-derived Demographic Terms
\[
b(t) = \max(g(t),0)
\]
\[
d_{\mathrm{nat}}(t) = \max(-g(t),0)
\]

4. HPAI Pressure Index
\[
p(t) = \frac{C(t)}{\max_t C(t)}
\]

5. Pressure-Dependent Reproduction Number
\[
R_0(t) = R_{0,\mathrm{base}} + R_{0,\mathrm{amp}}p(t)
\]

6. Transmission Rate
\[
\beta(t) = R_0(t)(\gamma+\mu)
\]

7. Imported Infections
\[
\Lambda(t) = \rho C(t)S(t)
\]

8. The Population
\[
N(t) = S(t)+E(t)+I(t)+R(t)
\]

9. Integrated GAM-SEIRD Model
\[
\begin{aligned}
\frac{dS}{dt}
&= b(t)N(t)
-\frac{\beta(t)S(t)I(t)}{N(t)}
-\Lambda(t)-d_{\mathrm{nat}}(t)S(t),\\
\frac{dE}{dt}
&= \frac{\beta(t)S(t)I(t)}{N(t)}
+\Lambda(t)-\sigma E(t)
-d_{\mathrm{nat}}(t)E(t),\\
\frac{dI}{dt}
&= \sigma E(t)-\gamma I(t)-\mu I(t)
-d_{\mathrm{nat}}(t)I(t),\\
\frac{dR}{dt}
&= \gamma I(t)-d_{\mathrm{nat}}(t)R(t),\\
\frac{dD}{dt}
&= \mu I(t).
\end{aligned}
\]


\begin{table}[h]
\raggedright
\renewcommand{\arraystretch}{1}
\begin{tabular}{ll}
\toprule
\textbf{Symbol} & \textbf{Interpretation} \\
\midrule
$S(t)$ & Susceptible Adélie penguins \\
$E(t)$ & Exposed but not yet infectious penguins \\
$I(t)$ & Infectious penguins \\
$R(t)$ & Recovered penguins \\
$D(t)$ & Cumulative disease-related deaths \\
$N(t)$ & Living population, $S+E+I+R$ \\
$\beta(t)$ & Time-varying transmission rate \\
$\sigma$ & Transition rate from exposed to infectious \\
$\gamma$ & Recovery rate \\
$\mu$ & Disease-induced mortality rate \\
$C(t)$ & External HPAI pressure signal \\
$p(t)$ & Normalised HPAI pressure index \\
$\Lambda(t)$ & Imported infection pressure \\
$\rho$ & External pressure scaling parameter \\
$b(t)$ & GAM-derived baseline growth term \\
$d_{\mathrm{nat}}(t)$ & GAM-derived natural decline term \\
\bottomrule
\end{tabular}
