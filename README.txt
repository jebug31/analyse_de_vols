

I) on charge le fichier h5, on supprime avec la bibliothèque os s'il le fichier clean.h5 existe déjà pour repartir de 0

II) on recréée un nouveau fichier h5 en filtrant les données
    - 1),2),3)  On enlève les dataframes ayant pour dimension (~,0) et celle qui n'ont pas de colonne altitude 
               afin de ne pas crée de bug lors du remplacement de nom. 
    - 4),5)6)   On utilise l'écart type, la moyenne et le max d'altitude afin d'enlever tout les bruits 
    - 7) On convertie les feet en mètre 
    - 8) Remplace le nom ALT [FT] par ALT
    - 9) je crée une nouvelle colonne CR qui met TRUE si l'altitude est compris entre altitude.max -150 et altitude et FALSE sinon 
        de telle sort que je sais si l'avion est en croisère ou pas

III) extraction des données décollage 
    - 1),2) on calcule la pente tout en faisant un lissage pour éviter les petits sauts 
    - 3) On extrait les sauts 

VI) extration des données : phases de croisières
    -1) On reprend la colonne CR, en utilisant TRUE on récupère les lignes où l'avion est phase de croisère
    -2) On extrait les données 



