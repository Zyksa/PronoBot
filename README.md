# 🎲 PronoBot — Bot Discord de Bookmaker (Pronostics en tout genre) 100% configurable

![Discord](https://img.shields.io/badge/Discord-Bot-7289da?style=for-the-badge&logo=discord)
![Node.js](https://img.shields.io/badge/Node.js-v18+-339933?style=for-the-badge&logo=node.js)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

PronoBot est un bot Discord pensé pour gérer des paris sportifs sur votre serveur avec une économie virtuelle, des classements, des grades et un système de certification. Simple à utiliser et complétement configurable, il permet de créer des matchs, placer des paris, suivre les statistiques et organiser des compétitions entre membres.

Il y a 2 types de match disponibles:

- Le match sport, on rentre le nom de l'équipe A, sa côte, le nom de l'équipe B, sa côte ainsi que la côte du Match Nul.
- Le match libre, question personnalisée et jusqu'à 9 choix possibles (avec côte pour chaques choix) à la manière des sondages twitch ou encore des paris avec comme réponse "Oui/Non"

---

Le code du bot n'est **pas open source** mais il est **certifié** par discord _(+ de 100 serveurs l'ont déjà adopté)_. 

Si vous êtes propriétaire d'un serveur et que vous souhaitez **visualiser le code du bot** c'est avec plaisir, ouvrez un ticket sur le [discord officiel](https://discord.gg/rbrPpWbEnV) puis si vous décidez de nous faire confiance, pourquoi pas devenir partenaire 😁

| Application Vérifiée ☺️ |
| :---: |
| ![Statistiques](https://i.imgur.com/3uAEI0s.png) |

---

## Ajouter le bot à votre serveur

Pour ajouter le bot à votre serveur il vous suffit de vous rendre sur ce [lien](https://discord.com/oauth2/authorize?client_id=835256483356737546&permissions=8&integration_type=0&scope=bot+applications.commands)

Ensuite, suivez les étapes indiquée dans la partie "**Configuration initiale**"

---

## Aperçu

Les visuels présentés sont des versions beta et sont susceptibles d’évoluer 😏.  
À noter : la génération de visuels personnalisés (canvas customisés) est réservé aux serveurs premium/partenaires.

| Pari | Configuration |
| :---: | :---: |
| ![Pari](https://i.imgur.com/mNPSkra.png) | ![Configuration](https://i.imgur.com/fl4Gztl.png) |

| Gain | Match Libre |
| :---: | :---: |
| ![Gain](https://i.imgur.com/NeeEMtr.png) | ![Match Libre](https://i.imgur.com/lhqItPA.png) |

| Match Sport | Match Terminé |
| :---: | :---: |
| ![Match Sport](https://i.imgur.com/dbXH3o0.png) | ![Match Terminé](https://i.imgur.com/ccg81BA.png) |

| Statistiques |
| :---: |
| ![Statistiques](https://i.imgur.com/cgf6isq.png) |

---

## Sommaire

- Présentation
- Fonctionnalités principales
- Commandes (pour tous, gestionnaires, admins)
- Grades & Certifications
- Classements
- Configuration initiale (rapide)
- Premium et partenariats
- Support & Aide
- Crédits
- Roadmap

---

## Présentation

PronoBot transforme votre serveur Discord en plateforme de paris amicaux :
- Créez des matchs (sportifs ou personnalisés).
- Les membres peuvent parier des pièces virtuelles.
- Résolution automatique des matchs et mise à jour des statistiques.
- Classements et grades pour encourager la compétition.

Tout est pensé pour être accessible au grand public — pas besoin de connaissances techniques.

---

## Fonctionnalités principales

- Économie virtuelle : pièces initiales, récompenses quotidiennes, gains/pertes.
- Paris simples et rapides (choix, montant).
- Création et gestion de matchs (sport ou libre).
- Résolution automatique et distribution des gains.
- Classements (victoires, taux de réussite, défaites, ratio gains/pertes).
- Grades globaux (Joueur, VIP, Champion, Partenaire, Staff, etc.) et badges de certification.
- Permissions par rôles (Admin, Manager, Restreint).
- Commandes slash, menu contextuel et interface conviviale.
- Possibilité d’activer/désactiver des commandes par serveur.

---

## Commandes principales

Toutes les commandes sont en Slash Commands **{/}**. Il y a aussi des commandes dans le menu contextuel d'un utilisateur _(clic droit sur un utilisateur > Applications)_

### Commandes utilisateurs

Les commandes ci‑dessous sont destinées aux utilisateurs lambda.

- /pb open  
    Créer un compte PronoBot sur le serveur et recevoir les pièces de bienvenue.

- /pb close  
    Supprimer définitivement votre compte sur ce serveur (confirmation requise).

- /pb balance  
    Voir votre solde actuel.

- /pb daily  
    Récupérer la récompense quotidienne (cooldown et gain configurable).

- /pb coinflip <choix>  
    Lancer une pièce pour tenter le pile ou face.

- /pb stats [utilisateur]  
    Voir les statistiques détaillées d'un joueur (classements, gains, etc.).

- /pb mybets  
    Voir vos paris en cours.

- /pb top [catégorie]  
    Voir les classements (par défaut Top 5, sinon Top 10 pour une catégorie donnée).  
    Catégories : wins, winrate, losses, profitratio

- /bet  
    Placer un pari sur un match disponible (sélection du match → choix → montant).

- /removebet  
    Annuler un pari tant que le match n'est pas clos.

- Menu contextuel (clic droit > Apps)  
    Voir rapidement les stats ou informations d’un utilisateur.


### Commandes de gestion (Rôle "Manager" configurable)

Ces commandes sont réservés aux utilisateurs qui possèdent le rôle assigné comme Manager (configurable)

- /creatematch  
    Créer un match sport (_2 equipes, et un match nul_) ou un match libre (_plusieurs choix possible comme un sondage twitch_). Titre, choix, et date/heure pour terminer les paris configurable

- /editmatch  
    Modifier un match existant.

- /deletematch  
    Supprimer un match et rembourser les paris (confirmation requise).

- /closematch  
    Clôturer un match et définir le résultat — distribution automatique des gains/pertes.

- /setdeadline <match>  
    Modifier la date limite pour parier sur un match.

- /listmatches  
    Lister tous les matchs actifs (possibilité de voir les match terminés également).

- /serverinfo, /botinfo  
    Informations sur le serveur et sa configuration ainsi que l'état technique du bot.

### Commandes administrateur (Rôle "Admin" configurable)

Ces commandes sont réservés aux utilisateurs qui ont la permission administrateur ou qui possèdent le rôle assigné comme Admin (configurable)

- /pbconfig [option] [valeur]  
    Configurer le serveur (rôles, canaux, montants, etc.). Exemple: /pbconfig initialcoins 500

    Conseil: Configurer en 1er le role administrateur avec /pbconfig adminrole <role admin de votre serveur> ainsi que le role manager avec /pbconfig managerrole <role qui permettra de gérer les matchs)

- /pbviewconfig  
    Afficher la configuration actuelle du serveur.

- /togglecommand <action> <commande>  
    Activer/désactiver une commande sur le serveur (ainsi qu'une liste pour voir celles désactivées).

- /pb userinfo <utilisateur>  
    Informations complètes sur un utilisateur (infos Discord + infos PronoBot).
    (disponible aussi dans le menu contextuel)

- /wipeuserdata  
    **⚠️ COMMANDE DANGEREUSE** - Réinitialise toutes les données utilisateurs du serveur (pièces, statistiques, paris). 
    Nécessite de taper "CONFIRMER" dans une modal pour valider. Les paramètres du serveur sont conservés.
    _par exemple pour faire un système de saisons?_
    **Cette action est irréversible !**

---

## Grades & Certifications

Les grades sont globaux et visibles sur tous les serveurs où PronoBot est présent :

- Joueur — grade par défaut.
- VIP — accès premium.
- Champion — joueurs d'élite.
- Partenaire — partenaires officiels.
- Staff — équipe de modération du bot.
- Owner — propriétaire du bot.

Certification : badge visible indiquant que le joueur est vérifié

Les grades servent surtout à reconnaitre les meilleurs joueurs et différencier les membres de confiance (staff).

---

## Classements

Quatre catégories principales :

1. Victoires — nombre total de paris gagnés.
2. Taux de victoire — pourcentage de paris gagnés (minimum requis : 5 paris).
3. Défaites — nombre total de paris perdus.
4. Ratio Gains/Pertes — pièces gagnées / pièces perdues (minimum : au moins 1 perte).

Affichage clair avec position : exemple "#2 sur 25". Les joueurs qui n'ont pas assez de données n'apparaissent pas dans certaines catégories.

---

## Configuration initiale (rapide)

1. Invitez le bot sur votre serveur.
2. Définissez les rôles via /pbconfig (adminrole, managerrole, restrictedrole).
3. Définissez les canaux via /pbconfig : annonces, salon réservés aux paris, salon d'annonces des matchs.
4. Définissez les paramètres économiques : initialcoins (montant donné à la création d'un compte pronobot sur votre serveur), dailyamount (montant donné par le /pb daily, 1 fois par jour).
5. Créez un premier match avec /creatematch et testez les paris en tant qu’utilisateur.

Conseil : commencez avec de petites valeurs (pièces de départ et récompense quotidienne) pour tester le système avant d’augmenter.

---

## Premium et Partenariats

La version premium permet de faire passer votre serveur à un niveau supérieur, le bot aura des fonctionnalités uniques telles que la génération d'**images personnalisées** qui remplaceront les embeds classiques de discord !

Pour devenir un **partenaire officiel** de PronoBot et ainsi avoir accès à un support direct avec le staff et l'abonnement **Premium gratuitement**, veuillez ouvrir un ticket sur le [discord officiel](https://discord.gg/rbrPpWbEnV) _(https://discord.gg/rbrPpWbEnV)_

## Support & Aide

- Rejoignez le serveur Discord (https://discord.gg/rbrPpWbEnV) pour demander de l'aide.
- Ouvrez un ticket sur le discord si vous rencontrez un bug ou que vous souhaitez faire une suggestion
- FAQ rapide :  
    - "Le bot ne répond pas" → vérifier que le bot est en ligne et a les permissions nécessaires.
    - "Je ne peux créer des matchs" → vérifier que vous avez bien configurer les rôles admins et manager ainsi que les salons dans le /pbconfig
    - "Vous n'avez pas de compte" → utilisez /pb open.  
    - "Commande désactivée" → un administrateur l’a peut‑être désactivée (/togglecommand list).

---

## Crédits

Développé par Zyksa et Hokanosekai ❤️

Utilise Node.js et une base de données (supabase) pour stocker les comptes et statistiques.

---

## Roadmap (idées futures)

- Ligues et divisions
- Matchs dynamiques (côte qui fluctuent en fonction du nombres de paris posés dessus)
- Paris combinés
- Événements saisonniers
- Boutique de récompenses
- Quêtes journalières et achievements
- Dashboard web et API pour les statistiques

---

Merci d'utiliser PronoBot ! Transformez votre serveur en arène de paris conviviale et compétitive. 🎲🏆
