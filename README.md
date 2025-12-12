#Kies Douaa , Biochimie Appliquée , 07/12/2025
#soumia mehenni 
#romaissaa otmane
#lokbani kawther
#Pandas with Kies Douaa , Mehenni Soumia , Otmane Romaissaa and Lokbani Kawther 
#for applied biochemistry Tlemcen...07/12/2025

import pandas as pd
# Donnée : Séquences ADN, Longueur, pourcentage de GC
data = {
     "Séquence": ["ATGCGTACGTA", "GCTAGCTAGGCC", "ATGCGCGTAAGT", "TACGATCGTA", "ATGAAAGGCTT", "CGTACGTAGC", "TTAACCGGAT"],
     "Longueur": [11, 12, 12, 10, 11, 10, 10],
     "pourcentage GC":[50, 66.67, 58.33, 40, 45.45, 60 ,50]
}

# Création d'un DataFrame (tableau pandas)
df = pd.DataFrame(data)
print("**************** Creation et affichage ****************")

# Affichage du tableau 
print("Tableau des séquences ADN :")
print(df, "\n\n")

# Operation sur les tableaux:
print("**************** Operations ****************")
 #1) Sélectionner la colonne "Séquence"
sequences = df["Séquence"]
print(sequences)

 #2) Affichage avec une bibliothèque de visualisation (matplotib)
 #import matplotib.pyplot as plt
 # Données
#Longueur = [11, 12, 12, 10, 11, 10, 10]
# Création d'un DataFrame
#data = {"Longueur":longueur
 #df = pd.DataFrame(data)
     
# Affichage du tableau de données sous forme de graphique
#plt.figure(figsize=(10))
#plt.bar(df["Séquence"], df["pourcentage GC"],color='skyblue')
#plt.xlabel("Séquences")
#plt.ylabel("pourcentage GC")
#plt.title("pourcentage de GC par séquence")
#plt.show()

#3)Filtrer les séquences avec un pourcentage de GC supérieur à 10%
print("****************Filtrage avec pourcentage % ****************")
# Filtrer les séquences avec un pourcentage % ****************")
filtered_df = df[df["pourcentage GC"] > 10] 
print(filtered_df, "\n\n")

#4)Calculer la moyenne du pourcentage de GC
print("****************Calcul de la moyenne****************")
#Calculer la moyenne du pourcentage de GC
average_gc = df["pourcentage GC"].mean()
print(f"pourcentage moyen de GC : {average_gc:.3f}%", "\n\n")

#5)Ajouter une nouvelle colonne avec des calculs
print("****************Ajout d'une nouvelle colonne****************")
# Ajouter une nouvelle colonne "longueur catégorisée"
df["Catégorie GC"] = df["Longueur"].apply(lambda x:"longue" if x>50 else "Riche" if 45 <= x <= 55 else"moyen" if x<45 else "faible")
print(df)

#6) Ajouter une nouvelle colonne donnant le nombre de 'G' dans chaque séquence
df["nombre de G"] = df["Séquence"].str.count("G")


#7) calculer  l'écart-type du pourcentage GC
print("*************calcul de l'écart-type *************")
#calculer l'écart-type du pourcentage de GC
average_=df["pourcentage GC" ].mean()
print(f"pourcentage l' ecart-type de GC) :{average_gc:2f}%","\n\n")

#8)sauvegarde et changementdes données avec panda 
#sauvegarder le DataFrame dans un fichier csv
df.to_csv("tableau _ sequences.csv",index=False)
















