# Creation d'utilisateur
 **Ouvrir ADUC** (`dsa.msc`)  
 **Naviguer vers l'OU** où se trouve Kelly Rhameur  
**Clic droit → Nouvel utilisateur**  
   - Prénom : `Lionel`  
   - Nom : `Lemarchand`  
   - Nom de connexion : `llomarchand` (selon convention)  
 **Copier les attributs de Kelly** :  
   - Onglet **Organisation** (Service, Manager, etc.)  
   - Onglet **Membre de** (Groupes)  
 **Définir un mot de passe temporaire** + "L'utilisateur doit changer le mot de passe..."
# Creation d'une OU DeactivatedUsers et déplacer Kelly
 **Créer l'OU** :  
   - Clic droit sur le domaine → **Nouveau → Unité d'organisation**  
   - Nom : `DeactivatedUsers`  
 **Déplacer Kelly Rhameur** :  
   - Clic droit sur son compte → **Déplacer** → Sélectionner `DeactivatedUsers`  
**Désactiver le compte** :  
   - Clic droit → **Désactiver le compte**
# Modifification groupe kelly les groupes
**Ouvrir les propriétés de Lionel Lemarchand**  
**Onglet "Membre de"** → **Ajouter**  
**Sélectionner les mêmes groupes que Kelly**
# Creation d'un dossier Individuel du nouvel utilisateur et archive celui de Kelly Rhameur en le suffixant par ARCHIVE
**Pour Lionel** :  
   - Créer un dossier `\\SRVWIN01\Profils\Lionel_Lemarchand`  
   - **Partager** → Ajouter `llomarchand` (Permissions : **Contrôle total**)  
**Pour Kelly** :  
   - Renommer son dossier en `\\SRVWIN01\Profils\Kelly_Rhameur-ARCHIVE`  
   - **Retirer ses permissions** via l'onglet Sécurité  


# Restriction horaire (Gabriel Ghul)
**Propriétés de Gabriel Ghul** → **Onglet "Compte"**  
 **Heures de connexion** :  
   - **Refuser toutes les plages**  
   - **Autoriser** : Lundi-Vendredi (7h-17h)
# Restriction machine 
1. **Propriétés de Gabriel Ghul** → **Onglet "Compte"**  
2. **Se connecter à...** → **"Les ordinateurs suivants"**  
3. **Ajouter** `CLIENT01`
# Mise en place stratégie de mot de passe pour durcir les comptes des utilisateurs de l'OU LabUsers. 
**Créer une GPO** liée à `LabUsers`  
 **Configurer** :  
   - **Longueur minimale** : 10 caractères  
   - **Complexité** : Activée  
   - **Historique** : 5 mots de passe  
   - **Durée max** : 60 jours  
