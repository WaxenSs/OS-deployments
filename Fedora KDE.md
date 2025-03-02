---
tags:
  - configuration
share: "true"
---
**Si execution d'un dual boot, il est impératif d'installer [Windows 11](./Windows%2011.md) avant toute installation pour éviter les conflit du Boot manager.**
# Updating packages
- `sudo dnf update`
- `sudo dnf upgrade`
# Enroll new MOK
[*source*](https://youtu.be/k5uxX2U3tYE?si=SgpC0_ZlddDBkrWl&t=83)
-  ⚠️ Si dual boot [Windows 11](./Windows%2011.md): Désactiver le boot dans le [BIOS](./BIOS.md) ⚠️
- `sudo dnf install kmodtool akmods mokutil openssl -y`
- `sudo kmodgenca -a`
- `sudo mokutil --import /etc/pki/akmods/certs/public_key.der`
- `systemctl reboot`
- Press `Enroll MOK`
- ⚠️ Si dual boot [Windows 11](./Windows%2011.md): Réactiver le boot dans le [BIOS](./BIOS.md) ⚠️
# Dépendances
## NVIDIA driver
- Installer `NVIDIA Linux Graphics Driver` sur Discover.
- `systemctl reboot`
- `modinfo -F version nvidia` *(doit indiquer la version)*
### Driver casser suite MAJ
Lors d'une mise à jour Fedora, le driver peut cesser de fonctionner. Voici une solution qui peut fonctionner, elle permet de rebuild le kernel:
- `sudo akmods --kernels $(uname -r) --rebuild --force`
# Disques
## Formats
- games_nvme
	- ext4
	- Droit d'accès: Tout le monde
- replays_ssd
	- ntfs
- files_dd
	- ntfs
## Montage automatique des disques
*Gestionnaire de partitions de KDE > Modifier le point de montage*
- Cocher Identifier par: `UUID`
- Emplacement: `/mnt/'sujet'_'type'/`
# Logiciels
## CoolerControl
[*source*](https://gitlab.com/coolercontrol/coolercontrol#fedora)
- `sudo dnf install dnf-plugins-core`
- `sudo dnf copr enable codifryed/CoolerControl`
- `sudo dnf install coolercontrol`
- `sudo systemctl enable --now coolercontrold`
## Discord
[source](https://github.com/Brunight/discord-rpm-packager?tab=readme-ov-file)
1. [Télécharger](https://github.com/RPM-Outpost/discord/archive/master.zip) et extraire le .zip.
2. Aller dans le directoire `discord-master` depuis le terminal.
3. Créer le paquet Discord Canary avec `./create-package.sh canary`.
*Cette version beta de Discord règle le problème du partage d'écran, étant une version officielle, elle permet également la modification des raccourcis.*
## RPM
- [1password](https://1password.com/fr/downloads/linux) *(RPM)*
- [Cider](https://itch.io/my-collections ) *(Flatpak)*
- [OpenDeck](https://github.com/ninjadev64/OpenDeck) *(RPM)*
- [r2modmanPlus](https://github.com/ebkr/r2modmanPlus) *(RPM)*
## Launchers
- Steam: `sudo dnf install steam`
- Rockstar Games Launcher *([source](https://www.youtube.com/watch?v=ZQ5ct-WqN2Y&t=175s))*
	- Install [RockstarGamesLauncher.exe](https://socialclub.rockstargames.com/rockstar-games-launcher)
	- Add on Steam
	- Install in C: disk (link in `/home/mblgr/.var/app/com.valvesoftware.Steam/.local/share/Steam/steamapps/compatdata/'NUMBERS'/pfx/drive_c/Program Files/Rockstar Games/Launcher/Launcher.exe`)
## Discover
- Flatseal *(Flatpak)*
- Flatsweep *(Flatpak)*
- Brave or Zen Browser *(Flatpak)*
- Add to Steam *(Boutique KDE)*
- ProtonUp-Qt *(Flathub)*
- VLC *(Fedora Linux)*
- qBittorent *(Fedora Linux)*
- Obsidian *(Flatpak)*
- Prism *(Flatpak)*
- Osu! *(Flatpak)*
- Vintage Story *(Flatpak)*
- OpenRGB *(Fedora Linux)*
- Sublime Text *(Flatpak)*
# Démarrage automatique
*Configuration du système > Démarrage automatique > Ajouter un nouveau*
- CoolerControl
- Steam
- 1password
- Discord
# GameMode
[*source*](https://youtu.be/tHAtX_aou_E?si=UtnU0IEFl1nasW3_)
Combinaison démon/bibliothèque pour Linux qui permet aux jeux de demander qu'un ensemble d'optimisations soit temporairement appliqué au système d'exploitation hôte et/ou à un processus de jeu. Lorsque qu'il est actif celui-ci permet également de désactiver temporairement le mode vieille automatique.
## Activation
Le démon GameMode est déjà installé sur Fedora, une simple activation est nécéssaire pour les jeux qui n'intègrent pas la prise en charge du GameMode nativement:
- Ajouter le jeu sur Steam
- Clique droit > Propriétés
- Général > Options de lancement
- `gamemoderun %command%`
*D'autres solutions d'intégrations sont disponibles sur le [repo GitHub](https://github.com/FeralInteractive/gamemode)*.
## Vérification du fonctionnement
- Lancer le jeu
- `gamemoded -s`

# Problèmes rencontrés
## Patché*s*
### Écran noir après plein écran
*Configuration du système > Affichage & Écran > Synchro adaptative > Jamais*

## Non patché*s*
- Les jeux flatpaks ne peuvent pas avoir l'overlay Steam *(et donc ne peuvent être enregistrés avec la fonction de replay)*
- les partitions en ntfs peuvent avoir un problème de lecture/écriture