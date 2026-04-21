# Die charakteristische Gleichung: drei Fälle, drei Lösungstypen

## Lernziele

```{admonition} Lernziele
:class: attention
* [ ] Sie können den **Exponentialansatz** $y(x) = e^{\lambda x}$ in die homogene lineare DGL 2. Ordnung einsetzen und daraus die **charakteristische Gleichung** $\lambda^2 + a\lambda + b = 0$ herleiten.
* [ ] Sie können die charakteristische Gleichung über $\mathbb{C}$ lösen und die Diskriminante $D = \tfrac{a^2}{4} - b$ zur Fallunterscheidung heranziehen.
* [ ] Sie können anhand der folgenden Tabelle die Fundamentallösungen $y_1$ und $y_2$ in Abhängigkeit der Eigenwerte bestimmen:
  - $D > 0$: zwei reelle Eigenwerte $\lambda_1 \neq \lambda_2$, Lösungen $e^{\lambda_1 x}$ und $e^{\lambda_2 x}$
  - $D < 0$: zwei komplexe Eigenwerte, Lösungen $e^{-\alpha x}\cos(\omega_0 x)$ und $e^{-\alpha x}\sin(\omega_0 x)$
  - $D = 0$: ein doppelter Eigenwert $\lambda$, Lösungen $e^{\lambda x}$ und $xe^{\lambda x}$
* [ ] Sie können für jeden der drei Fälle die allgemeine Lösung $y_h(x) = C_1 y_1(x) + C_2 y_2(x)$ angeben.
```
