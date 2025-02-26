---
tags:
  - configuration
share: "true"
---
**Si execution d'un dual boot, il est impératif d'installer [Windows 11](./Windows%2011.md) avant toute installation pour éviter les conflit du Boot manager.**
### Updating packages
- `sudo dnf update`
- `sudo dnf upgrade`
### Enroll new MOK *([source](https://www.youtube.com/watch?v=k5uxX2U3tYE))*
- `sudo dnf install kmodtool akmods mokutil openssl`
- `sudo kmodgenca -a`
- `sudo mokutil --import /etc/pki/akmods/certs/public_key.der`
- `systemctl reboot`
- Press *Enroll MOK*
	⚠️ Avec un dual boot, l'interface **Enroll MOK** ne s’affiche pas immédiatement après un redémarrage, si cela est le cas, suivre cette procédure :
	- **Redémarrer le PC** et accède au menu de démarrage GRUB.
	-  Lorsque tu vois l’écran de GRUB, sélectionne l’option Fedora pour démarrer Fedora, mais ne lance pas encore Fedora.
	- Appuie sur **Shift** ou **Esc** pour essayer de forcer l’affichage de l’interface MOK.
	Si cela ne fonctionne pas, il peut arriver que cette interface arrive de manière aléatoire *(comme moi)*.
### Installer dépendances
#### Install NVIDIA Linux Graphics Driver *(on Discover)*
- Check that the Nvidia version is recognized: `modinfo -F version nvidia`
	- Si la commande ne reconnait pas de version, reboot le pc.
#### CoolerControl ([source](https://gitlab.com/coolercontrol/coolercontrol#fedora))
- `sudo dnf install dnf-plugins-core`
- `sudo dnf copr enable codifryed/CoolerControl`
- `sudo dnf install coolercontrol`
- `sudo systemctl enable --now coolercontrold`
### Activation du GameMode

### Montage automatique des disques
#### Format des disks
- games_nvme
	- ext4
	- Droit d'accès: Tout le monde
- replays_ssd
	- ntfsπ
- files_dd
	- ntfs
#### Set default mount disks
*Gestionnaire de partitions de KDE > Modifier le point de montage*
- Cocher Identifier par: `UUID`
- Emplacement: `/mnt/'sujet'_'type'/`
### Logiciels
- [1password](https://1password.com/fr/downloads/linux) *(RPM)*
- [Cider](https://itch.io/my-collections ) *(Flatpak)*
- [OpenDeck](https://github.com/ninjadev64/OpenDeck) *(RPM)*
#### Launchers
- Steam: `sudo dnf install steam`
- Rockstar Games Launcher *([source](https://www.youtube.com/watch?v=ZQ5ct-WqN2Y&t=175s))*
	- Install [RockstarGamesLauncher.exe](https://socialclub.rockstargames.com/rockstar-games-launcher)
	- Add on Steam
	- Install in C: disk (link in `/home/mblgr/.var/app/com.valvesoftware.Steam/.local/share/Steam/steamapps/compatdata/'NUMBERS'/pfx/drive_c/Program Files/Rockstar Games/Launcher/Launcher.exe`)
#### Discover
- Flatseal *(Flatpak)*
- Flatsweep (Flatpak)
- Brave or Zen Browser *(Flatpak)*
- Goofcord *(Flatpak)*
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
### Démarrage automatique
*Configuration du système > Démarrage automatique > Ajouter un nouveau*
- CoolerControl
- Steam
- 1password
- Goofcord
### Patch problème plein écran
*Configuration du système > Affichage & Écran > Synchro adaptative > Jamais*