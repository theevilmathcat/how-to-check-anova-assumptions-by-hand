# 🔍 Checking One-Way ANOVA Assumptions by Hand  
### 💪 Weightlifting Example (Max Squat in kg)

We’re using the same dataset (n=5 per group):  

- **Group A** (mean = 110): 100, 105, 110, 115, 120  
- **Group B** (mean = 120): 110, 115, 120, 125, 130  
- **Group C** (mean = 130): 120, 125, 130, 135, 140  

**Grand mean** = 120  
**Within-group variance (MSW)** = 62.5  

Let’s check the **three key assumptions** one by one! ✅

### 1️⃣ **Independence of Observations**  
🛡️ **How to check**: This is **not tested statistically** — it’s ensured by **study design**.  

✅ **What we need**:  
- Different individuals in each group  
- Random assignment or random sampling  
- No repeated measures on the same person  
- No pairing across groups  

💡 **In our example**: We assume lifters are different people, randomly assigned to training programs, and lifts were measured independently.  

✅ **Conclusion**: Assumption met by design.  
⚠️ If violated → use repeated-measures ANOVA instead!

### 2️⃣ **Normality of Residuals**  
🔔 **What to check**: Residuals (observed − group mean) should be approximately normally distributed.  

📊 **All residuals (pooled, N=15)**:  
-10, -5, 0, +5, +10 (repeated identically in each group)  

✨ **By-hand checks**:  
- **Visual** : If you made a histogram → perfect symmetric bell shape. No outliers, no skewness.  
- **Q-Q plot** (imagined): Points would fall exactly on the straight line.  
- **Skewness**: 0 (perfectly symmetric)  
- **Kurtosis**: Close to 0 (normal peak and tails for this pattern)  

📈 **Note**: For small samples, visual inspection is enough. Formal tests like Shapiro-Wilk are hard by hand.  

🛡️ ANOVA is quite **robust** to mild non-normality, especially with equal group sizes.  

✅ **Conclusion**: Normality assumption clearly met.

### 3️⃣ **Homogeneity of Variances (Equal Variances Across Groups)**  
⚖️ **What to check**: All groups should have roughly the same variance.  

🔢 **Calculate variance per group** (s² = Σ(deviations²) / (n-1)):  
Each group: deviations² sum to 250 → variance = 250 / 4 = **62.5**  
→ **All three groups have exactly the same variance!**

✅ **Quick rules of thumb**:  
- Largest variance / smallest variance = 1 (< 2–4 → very good)  
- Boxplots would show identical spread  

🧮 **Simple formal check (Hartley’s Fmax)**:  
Fmax = max variance / min variance = 1 → not significant  

🧪 **Levene’s test by hand (robust)**:  
Take absolute deviations from group mean: 10, 5, 0, 5, 10 in every group  
→ Group mean of absolutes = 6 (identical)  
→ Between-group variation = 0 → F = 0 → p = 1 (no evidence against equality)  

✅ **Conclusion**: Equal variances assumption perfectly met.

### 🎉 **Overall Summary**

| Assumption                  | Status       | Reason                                      |
|-----------------------------|--------------|---------------------------------------------|
| 🛡️ Independence            | ✅ Met       | Ensured by study design                     |
| 🔔 Normality of residuals   | ✅ Met       | Symmetric residuals, no outliers            |
| ⚖️ Equal variances          | ✅ Met       | Identical variances across groups           |

**All three assumptions are satisfied** → Standard one-way ANOVA (and follow-up post hoc tests) are perfectly appropriate here! 🚀

💡 **Real-world tips**:  
- Always verify independence from the design.  
- For normality → plot residuals (Q-Q or histogram).  
- If variances unequal AND group sizes unequal → consider Welch’s ANOVA.  
- ANOVA is fairly robust with equal n, so small deviations are often okay.  

Last Updated: December 2025
License: The Evil Math Cat
Contributions: Gimme me cat food damn it.
