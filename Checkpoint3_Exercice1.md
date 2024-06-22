## Partie 1 : Gestion des utilisateurs
### Q.1.1.1
Par simplicité, j'ai copié le profil de Kelly Rhameur et l'ai ajuster en entrant les informations de Lionel Lemarchand
![Capture d'écran 2024-06-21 093644](https://github.com/Sherub1/Checkpoint-3/assets/160050170/8485dd8b-7f46-457e-8b77-6de5eefe9902)

Pour completer le profil de Lionel Lemarchand, je l'ai désigné comme manager de chaque subalternes. Pour exemple Ophélie Poulin

![Capture d'écran 2024-06-21 095059](https://github.com/Sherub1/Checkpoint-3/assets/160050170/992b748f-9a1d-4e47-a651-01d9d74db862)

![Capture d'écran 2024-06-21 095038](https://github.com/Sherub1/Checkpoint-3/assets/160050170/46ba6260-e928-441c-bb5a-2c7b1476d55e)

### Q.1.1.2

Je crée une nouvelle OU appelée DeactivatedUsers (je l'ai faite dans le mauvais répertoire donc je la bouge ou elle doit se trouver)
![Capture d'écran 2024-06-21 100614](https://github.com/Sherub1/Checkpoint-3/assets/160050170/e710a6ed-b7b5-4069-b0a5-ae10a5a25875)

Je désactive le compte de Kelly Rhameur
![Capture d'écran 2024-06-21 100733](https://github.com/Sherub1/Checkpoint-3/assets/160050170/5a840ae0-9eca-4cbe-8201-9fc86079796e)

Et déplace le compte désactivé dans l'OU DeactivatedUser
![Capture d'écran 2024-06-21 100814](https://github.com/Sherub1/Checkpoint-3/assets/160050170/7aacca88-59db-4a42-8164-2a8e344026e9)

### Q.1.1.3

Je vais dans l'OU Direction des Ressources Humaines, et dans le groupe GrpUsersDirectionDesRessourcesHumaine je "remove" Kelly Rhameur

![Capture d'écran 2024-06-21 102009](https://github.com/Sherub1/Checkpoint-3/assets/160050170/57f7d052-117e-4631-8a89-3714e96ebf29)
![Capture d'écran 2024-06-21 102029](https://github.com/Sherub1/Checkpoint-3/assets/160050170/816695c4-7ffd-43e2-8f7e-cbbf3f3ca9a9)

### Q.1.1.4

Création du dossier personnel de Lionel Lemarchand

![Capture d'écran 2024-06-21 103646](https://github.com/Sherub1/Checkpoint-3/assets/160050170/568ec578-bec2-4ead-9fdb-f3cf7f43c94f)

Archivage et mise à jour des droits sur le dossier personelle de Kelly Rhameur

![Capture d'écran 2024-06-21 104300](https://github.com/Sherub1/Checkpoint-3/assets/160050170/122982e2-199c-4197-b0a6-78cffa2e9024)

## Partie 2 : Restriction utilisateurs

### Q.1.2.1

Clique droit sur Gabriel Ghul > Properties > Account > Logon Hours... et ajuster la plage horaire
![Capture d'écran 2024-06-21 105304](https://github.com/Sherub1/Checkpoint-3/assets/160050170/2c1444b2-b294-4c53-918d-aa2642e8a5bf)

### Q.1.2.2

Clique droit sur Gabriel Ghul > Properties > Account > Log On to... et ajouter le nom de la machine

![Capture d'écran 2024-06-21 105837](https://github.com/Sherub1/Checkpoint-3/assets/160050170/222fa516-49a7-465d-a512-33ab13a60918)

### Q.1.2.3

Je crée un groupe dans l'OU LabUsers dans lequel je vais y ajouter tous les autres groupes des sous OU.

![Capture d'écran 2024-06-22 142427](https://github.com/Sherub1/Checkpoint-3/assets/160050170/1d51f525-bf70-4b55-a99d-e39c2346d4a1)

Exemple d'ajouts de groupe dans le groupe GrpLabUsers

![Capture d'écran 2024-06-22 142501](https://github.com/Sherub1/Checkpoint-3/assets/160050170/38d1effd-e5a9-4740-b0db-4a08afe4d347)



![Capture d'écran 2024-06-22 142803](https://github.com/Sherub1/Checkpoint-3/assets/160050170/ef2b9dfd-b51e-439f-94cf-25b335af6252)

Ensuite on se rends dans le Password Settings Container, pour ajouter une politique de mot de passe au groupe GrpLabUsers

![Capture d'écran 2024-06-22 143034](https://github.com/Sherub1/Checkpoint-3/assets/160050170/7488afbc-3a86-4fa5-ad83-5db8b0cee8fc)

## Partie 3 : Lecteurs réseaux

### Q.1.3.1

Mettre les lecteur E: et F: en partage en allant sur Properties>Sharing>Advance Sharing.. et selectionner le partage de lecteur

![Capture d'écran 2024-06-22 151040](https://github.com/Sherub1/Checkpoint-3/assets/160050170/4960db9b-30c7-4abe-8163-cf8274209620)


Une fois les lecteurs configurés, on se rend dans le Group Policy Management et on crée une nouvelle régle appelée "Drive-Mount Policy"

![Capture d'écran 2024-06-22 144509](https://github.com/Sherub1/Checkpoint-3/assets/160050170/390b320c-4795-425d-ac24-bee8d6446c28)

Puis j'édite la nouvelle GPO

![Capture d'écran 2024-06-22 144643](https://github.com/Sherub1/Checkpoint-3/assets/160050170/b4f9ddbb-4023-40a2-8f41-3ff888bbd3cd)

Selectionner New > Mapped Drive


![Capture d'écran 2024-06-22 144725](https://github.com/Sherub1/Checkpoint-3/assets/160050170/d92f937a-7c59-47a3-83a8-18b591e8c741)


J'ajoute le chemin, le label du lecteur et sa lettre. Coche Reconnect et dans l'onglet Common je coche la deuxième option

![Capture d'écran 2024-06-22 151228](https://github.com/Sherub1/Checkpoint-3/assets/160050170/999bcfc8-96d9-4543-9c1c-c68a792adbee)

![Capture d'écran 2024-06-22 150954](https://github.com/Sherub1/Checkpoint-3/assets/160050170/e11f0dc0-c455-4eeb-bc62-6d25de8991c0)



![Capture d'écran 2024-06-22 154311](https://github.com/Sherub1/Checkpoint-3/assets/160050170/e5d1db46-2f30-43c0-8d5c-98597a0b6f8a)

On peut voir que la GPO est activé sur l'OU LabUsers
![Capture d'écran 2024-06-22 154737](https://github.com/Sherub1/Checkpoint-3/assets/160050170/2b489564-8e37-404c-a145-b8cef66a1127)


