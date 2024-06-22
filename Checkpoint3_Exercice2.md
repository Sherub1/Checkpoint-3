## Partie 1 : Gestion des utilisateurs

### Q.2.1.1

Création de l'utilisateur sebastien et vérification dans /etc/passwd

![Capture d'écran 2024-06-21 115109](https://github.com/Sherub1/Checkpoint-3/assets/160050170/da0b05cd-1511-4a1e-9414-4841867da06c)

### Q.2.1.2

Créer l'utilisateur avec la commande ``adduser`` pour qu'il puisse bénéficier d'un /home necessaire pour la connection via ssh
Eviter d'ajouter l'utilisateur au groupe Root, si on veut les droits administrateur on peut passer par la commade ``su``+ password root.

## Partie 2 : Configuration de SSH

### Q.2.2.1

Editer le fichier de configuration situé /etc/ssh/sshd_config
avec la ligne `PermitRootLogin no`

### Q.2.2.2

Editer le fichier de configuration situé /etc/ssh/sshd_config
avec la ligne `AllowUsers sebastien`

![Capture d'écran 2024-06-21 115215](https://github.com/Sherub1/Checkpoint-3/assets/160050170/f53d585b-6902-4542-af43-b301fa33b0cc)

### Q.2.2.3

Depuis une machine client je lance la commande  `ssh-keygen` ensuite `ssh-copy-id sebastien@172.16.10.11`

Pour interdire la connection avec mot de passe ,il faut éditer le fichier `sshd_config` avec un `PasswordAuthentication no`

![Capture d'écran 2024-06-22 162043](https://github.com/Sherub1/Checkpoint-3/assets/160050170/e6c328ac-efb8-4acd-a9f2-5d96625943ff)


La connexion se fait avec la clef ssh générée plus tôt,comme le montre le screen ci-dessous.

![Capture d'écran 2024-06-22 161302](https://github.com/Sherub1/Checkpoint-3/assets/160050170/7682d0fc-1b5d-420a-948e-0dbb5e71a444)

## Partie 3 : Analyse du stockage

### Q.2.3.1 

EXT2, EXT4 et SWAP

![Capture d'écran 2024-06-21 123331](https://github.com/Sherub1/Checkpoint-3/assets/160050170/2194c59d-7bfd-45b8-b98b-435f035ca203)

### Q.2.3.2 

RAID1 et LVM

![Capture d'écran 2024-06-21 123421](https://github.com/Sherub1/Checkpoint-3/assets/160050170/f48fddc5-5d5b-4513-a94a-e7b1ab2882ef)

### Q.2.3.3

J'ajoute un disk via Virtual Box qui apparait en tant que SDB

![Capture d'écran 2024-06-22 165228](https://github.com/Sherub1/Checkpoint-3/assets/160050170/a82b75b8-cddb-4c7f-87a4-362a31bf1bb7)

Ce nouveau disk va servir a réparer le RAID1, donc il faut le configurer.
``fdisk /dev/sdb``
``n`` puis on laisse tout par défaut, jusqu'a la selection du type de partition ``t``ou on choisira FD.

Ajouter le nouveau disk au RAID existant avec la commande:
``mdadm --manage /dev/md0 --add /dev/sdb1``

Et vérifier si le RAID1 fonctionne avec la commande: 
``mdadm --detail /dev/md0``

![Capture d'écran 2024-06-22 165801](https://github.com/Sherub1/Checkpoint-3/assets/160050170/0ce4ee46-3562-4337-80bb-7580b56e8c9d)

### Q.2.3.4

![Capture d'écran 2024-06-22 204145](https://github.com/Sherub1/Checkpoint-3/assets/160050170/4f92e13a-4050-4e34-b85b-084d7c76aaa7)

Après avoir vérifié l'espace disponible, on crée le volume logique 'Save'

![Capture d'écran 2024-06-22 204619](https://github.com/Sherub1/Checkpoint-3/assets/160050170/8099d384-50a7-44d6-bcb8-5a20ef418897)

On le formate en EXT4

![Capture d'écran 2024-06-22 204824](https://github.com/Sherub1/Checkpoint-3/assets/160050170/175c96d9-4fab-4869-8299-419302149d5d)

On monte le volume comme indiqué

![Capture d'écran 2024-06-22 205235](https://github.com/Sherub1/Checkpoint-3/assets/160050170/764a3459-0113-400f-8032-3f46b0de0444)

Ensuite, on édite le fichier fstab pour monter le volume au démarrage


![Capture d'écran 2024-06-22 210300](https://github.com/Sherub1/Checkpoint-3/assets/160050170/2c0d1d00-221b-4a74-a658-ea2542efbd9d)


