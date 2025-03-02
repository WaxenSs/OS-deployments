---
tags: []
share: "true"
---
[Configuration](./Configuration.md)
[Logiciels](./Logiciels.md)

### Pré-configuration
- Autoriser Microsoft et les applications à utiliser votre emplacement: `Non`
- Localiser mon appareil: `Oui`
- Envoyer des données de diagnostic à Microsoft: `Obligatoire uniquement`
- Améliorer l'écriture manuscrite et la saisie: `Non`
- Obtenir des expériences personnalisées avec des données de diagnostic: `Non`
- Autoriser les applications à utiliser l'identifiant de publicité: `Non`
- Personnalisons votre expérience utilisateur: `Ignorer` *(en bas à droite, à côté du bouton "Accepter")*
- Utiliser votre téléphone à partir de votre PC: `Ignorer` *(en bas à droite, à côté du bouton "Accepter")*
- Sauvegarder vos fichier avec OneDrive: `Ne pas sauvegarder mes fichiers`
- Poursuivez là où vous en êtes arrêté en important à partir de votre autre navigateur: `Pas maintenant.`
- Vous en avez de la chance : vous avez réussi un essai gratuit de Microsoft 365 Famille: `Refuser Microsoft 365` *(en bas à droite, à côté du bouton "Continuer")*
- Obtenir plus d'espace de stockage cloud avec Microsoft 365 Basic: `Refuser` *(en bas à droite, à côté du bouton "Continuer")*
- Saviez-vous que vous pouvez utiliser Microsoft 365 gratuitement ?: `Suivante`
- Rejoignez PC Games Pass pour seulement 11,99 € par mois: `Ignorer pour le moment` *(en bas à droite, à côté du bouton "Rejoindre pour 11,99 €")*

### Configuration
#### Win11Debloat *[source](https://github.com/Raphire/Win11Debloat)*

Windows PowerShell: `& ([scriptblock]::Create((irm "https://debloat.raphi.re/")))`
- Custom mode: `2`
	- Remove default selection of bloatware apps, aswell as mail & calendar apps, developper apps and gaming apps: `2`
	- Disable telemetry, diagnostic data, activity history, app-launch tracking and targeted ads ?: `y`
	- Disable tips, tricks, suggestions and ads in start, settings, notifications, explorer, desktop and lockscreen ?: `y`
	- Disable & remove bing web search, bing AI & cortana in Windows search ?: `y`
	- Disable & remove Windows Copilot ? This applies all users: `y`
	- Disable Windows Recall snapshots ? This applies all users: `y`
	- Restore the old Windows 10 style context menu ?: `y`
	- Turn off Enhance Pointer Precision, also known as mouse acceleration ?: `y`
	- Do you want to disable any context menu options ?: `y`
		- Hide the 'Include in library' option in the context menu ?: `y`
		- Hide the 'Give access to' option in the context menu ?: `y`
		- Hide the 'Share' option in the context menu ?: `y`
	- Do you want to make any changes to the start menu ?: `y`
		- Remove all pinned apps from start menu ?: `Remove all pinned apps from the start menu for all existing and new users (2)`
		- Disable & hide the recommended section in the start menu ?  This applies all users: `y`
	- Do you want to make any changes to the taskbar and related services ?: `y`
		- Align taskbar buttons to the left side ?: `n`
		- Hide or change the search icon on the taskbar ?: `Show search icon on the taskbar (2)`
		- Hide the taskview button from the taskbar ?: `y`
		- Disable the widgets service and hide the icon from the taskbar ?: `y`
	- Do you want to make any changes to Files Explorer ?: `y`
		- Change the default location that File Explorer opens to ?: `n`
		- Show hidden files, folders and drives ?: `y`
		- Show file extensions, folders and drives ?: `y`
		- Hide the Home section from the File Explorer sidepanel ?: `y`
		- Hide the Gallery section from the File Explorer sidepanel ?: `y`
		- Hide duplicate removable drive entries from the File Explorer sidepanel so they only show under This PC ?: `y`
#### Paramètres
##### Écran
- Éclairage nocturne
	- Panifier l'éclairage nocturne: `20:45 à 7:45`
- HDR
	- Luminosité du contenu DTS: `100%`
	- HDR automatique: Activé
- Paramètres avancés de l'écran
	- Choisir une fréquence d'actualisation: `fréquence (Hz) maximum`
##### Réseau
- Désactivation du Bluetooth
- Désactivation du Wi-Fi
##### Jeux
- Désactivation du Game Bar
##### Windows Update
- Effectuer les mise à jour Windows Update
##### Disques
 ⚠️ Si dual boot [Fedora KDE](./Fedora%20KDE.md): Désactiver le "Démarrage rapide"
		`Panneau de configuration > Matériel et audio > Options d'alimentation > Paramètres système > Activer le démarrage rapide`: Décocher
*Permet de rendre possible l'écriture des disques en `NTFS` possibles sur Linux.*
### Apps
- Désinstaller `OneDrive`
- Asus `Armory Crate` *(demande d'installation automatique lors de la première connexion sur Windows)*
	- Faire les mises à jour de pilotes
- Firefox
- Discord
- Logitech G Hub
- Valorant
- Elgato Stream Deck
- Elgato Wave Link