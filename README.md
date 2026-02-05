import pandas as pd
import matplotlib.pyplot as plt

# 1. Préparation des données (Scénario A vs Scénario B)
annees = [1, 2, 3, 4, 5]
investissement_A = [100, 120, 150, 190, 240] # Croissance organique
investissement_B = [80, 110, 160, 230, 320]  # Croissance avec IA (Optimisée)

data = {
    'Année': annees,
    'Sénario_Classique': investissement_A,
    'Scénario_IA_Optimisé': investissement_B
}

df = pd.DataFrame(data)

# 2. Calcul automatique de l'écart (ROI)
df['Gain_IA'] = df['Scénario_IA_Optimisé'] - df['Sénario_Classique']

# 3. Visualisation stratégique
plt.figure(figsize=(10, 6))
plt.plot(df['Année'], df['Sénario_Classique'], label='Classique', marker='x', linestyle='--')
plt.plot(df['Année'], df['Scénario_IA_Optimisé'], label='Optimisé (IA)', marker='o', linewidth=2)
plt.fill_between(df['Année'], df['Sénario_Classique'], df['Scénario_IA_Optimisé'], color='green', alpha=0.1)

plt.title("Impact de l'Optimisation sur la Croissance")
plt.legend()
plt.grid(True)
plt.show()

print("Tableau de bord stratégique :")
print(df)
