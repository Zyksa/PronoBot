# 🎲 PronoBot — Bot Discord de Bookmaker (Pronostics en tout genre) 100% configurable

**[🇫🇷 Français](#-pronobot--bot-discord-de-bookmaker-pronostics-en-tout-genre-100-configurable) | [🇬🇧 English](#-pronobot--customizable-discord-bookmaker-bot)**

![Discord](https://img.shields.io/badge/Discord-Bot-7289da?style=for-the-badge&logo=discord)
![Node.js](https://img.shields.io/badge/Node.js-v18+-339933?style=for-the-badge&logo=node.js)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

PronoBot est un bot Discord pensé pour gérer des paris sportifs sur votre serveur avec une économie virtuelle, des classements, des grades, un système de certification et un système de **niveaux et XP**. Simple à utiliser et complétement configurable, il permet de créer des matchs, placer des paris, suivre les statistiques et organiser des compétitions entre membres.

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

### 🎮 Système de Progression
- **⭐ Niveaux et XP** : Gagnez de l'expérience à chaque action (récompense quotidienne, paris gagnés ou perdus) et montez en niveau ! Chaque serveur possède son propre système de progression indépendant.
- **🏆 Classements dynamiques** : 5 catégories de classement (niveau, victoires, taux de réussite, défaites, ratio gains/pertes) pour une compétition saine entre membres.
- **🎖️ Grades globaux** : Grades visibles sur tous les serveurs (Joueur, VIP, Champion, Partenaire, Staff, Owner) avec badges de certification.

### 💰 Économie Virtuelle
- **Pièces virtuelles** : Montant de départ configurable, récompenses quotidiennes et gestion complète des gains/pertes.
- **💳 Affichage en temps réel** : Votre solde actuel et mise maximale sont affichés directement dans la modal de pari pour plus de clarté.
- **📊 Notifications de solde** : Recevez un message privé après chaque pari avec votre nouveau solde mis à jour.

### 🎲 Gestion des Matchs
- **Deux types de matchs** : Matchs sportifs (2 équipes + match nul) ou matchs libres (jusqu'à 9 choix personnalisables).
- **Paris simples et rapides** : Interface intuitive pour choisir et miser en quelques clics.
- **Résolution automatique** : Distribution instantanée des gains lors de la clôture d'un match.

### 🛡️ Administration & Modération
- **🚫 Système de restriction** : Les managers peuvent restreindre des utilisateurs pour les empêcher de parier via un rôle configurable.
- **🔐 Permissions par rôles** : Gestion fine des permissions (Admin, Manager, Restreint) pour un contrôle total.
- **⚙️ Commandes activables/désactivables** : Possibilité d'activer ou désactiver des commandes spécifiques par serveur.

### ✨ Interface Moderne
- **Commandes slash (/)** : Toutes les commandes utilisent le système moderne de Discord.
- **Menu contextuel** : Accès rapide aux statistiques via clic droit sur un utilisateur.
- **Emojis visuels** : Statuts de matchs clairs (✅ ouvert, 🔒 fermé, ⏳ en attente).

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
    Catégories : level, wins, winrate, losses, profitratio

- /vote
    Voter pour PronoBot sur Top.gg et soutenir le projet. L'embed explique pourquoi voter est important pour nous aider à grandir.

- /pbpremium
    Afficher des informations sur l'abonnement premium.

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
    Modifier un match existant. **Désormais avec menu de sélection** - plus besoin de chercher l'ID du match !

- /deletematch
    Supprimer un match et rembourser les paris. **Désormais avec menu de sélection** - choisissez le match dans une liste interactive.

- /closematch
    Clôturer un match et définir le résultat — distribution automatique des gains/pertes.

- /setdeadline <match>
    Modifier la date limite pour parier sur un match.

- /listmatches
    Lister tous les matchs actifs (possibilité de voir les match terminés également).

- /listallmatches
    Afficher TOUS les matchs (ouverts, fermés, terminés) sans filtre pour une vue d'ensemble rapide.

- /restrict <utilisateur>
    Restreindre un utilisateur en lui appliquant le rôle restreint configuré, l'empêchant de parier.

- /unrestrict <utilisateur>
    Retirer la restriction d'un utilisateur pour qu'il puisse à nouveau parier normalement.

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

- /pbadmin [add/remove/set/giveall] <utilisateur> <montant>
    Gérer les pièces des joueurs.
    _Exemple : /pbadmin add @user 100_

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

## Classements et Système de Niveaux

### 🏆 Classements

Cinq catégories principales :

1. **Niveau** — progression basée sur l'XP gagnée (propre à chaque serveur).
2. Victoires — nombre total de paris gagnés.
3. Taux de victoire — pourcentage de paris gagnés (minimum requis : 5 paris).
4. Défaites — nombre total de paris perdus.
5. Ratio Gains/Pertes — pièces gagnées / pièces perdues (minimum : au moins 1 perte).

### ⭐ Système d'Expérience et Niveaux

Le système d'XP et de niveaux est **entièrement propre à chaque serveur** — vos niveaux et XP sont indépendants d'un serveur à l'autre.

**Comment gagner de l'XP :**
- **Récompense quotidienne (/pb daily)** : +10 XP fixe
- **Paris gagnés** : 20 XP de base + 5% des pièces gagnées (min 20 XP, max 200 XP par pari)
- **Paris perdus** : +5 XP (récompense de participation)

**Progression de niveau :**
- La formule d'XP requise est : `(Niveau - 1)² × 100`
  - Niveau 1 : 0 XP (départ)
  - Niveau 2 : 100 XP
  - Niveau 3 : 400 XP
  - Niveau 4 : 900 XP
  - Niveau 5 : 1,600 XP
  - Niveau 10 : 8,100 XP

**Affichage :**
- Votre niveau et XP sont visibles dans `/pb stats`
- Barre de progression indiquant l'avancement vers le prochain niveau
- Classement par niveau disponible dans `/pb top level`

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

---
---
---

# 🎲 PronoBot — Customizable Discord Bookmaker Bot

**[🇫🇷 Français](#-pronobot--bot-discord-de-bookmaker-pronostics-en-tout-genre-100-configurable) | [🇬🇧 English](#-pronobot--customizable-discord-bookmaker-bot)**

![Discord](https://img.shields.io/badge/Discord-Bot-7289da?style=for-the-badge&logo=discord)
![Node.js](https://img.shields.io/badge/Node.js-v18+-339933?style=for-the-badge&logo=node.js)
![License](https://img.shields.io/badge/License-MIT-blue?style=for-the-badge)

PronoBot is a Discord bot designed to manage betting on your server with a virtual economy, rankings, ranks, a certification system, and a **Level & XP system**. Easy to use and fully configurable, it allows you to create matches, place bets, track statistics, and organize competitions among members.

There are 2 types of matches available:

- Sports match: enter Team A's name, its odds, Team B's name, its odds, and the Draw odds.
- Free match: custom question and up to 9 possible choices (with odds for each choice) like Twitch polls or "Yes/No" bets.

---

The bot's code is **not open source** but it is **verified** by Discord _(over 100 servers have already adopted it)_.

If you are a server owner and would like to **view the bot's code**, we'd be happy to show you — open a ticket on the [official Discord](https://discord.gg/rbrPpWbEnV), and if you decide to trust us, perhaps become a partner 😁

| Verified Application ☺️ |
| :---: |
| ![Statistics](https://i.imgur.com/3uAEI0s.png) |

---

## Add the Bot to Your Server

To add the bot to your server, simply go to this [link](https://discord.com/oauth2/authorize?client_id=835256483356737546&permissions=8&integration_type=0&scope=bot+applications.commands)

Then, follow the steps in the "**Initial Setup**" section.

---

## Preview

The visuals shown are beta versions and may evolve 😏.
Note: Custom visual generation (custom canvases) is reserved for premium/partner servers.

| Bet | Configuration |
| :---: | :---: |
| ![Bet](https://i.imgur.com/mNPSkra.png) | ![Configuration](https://i.imgur.com/fl4Gztl.png) |

| Win | Free Match |
| :---: | :---: |
| ![Win](https://i.imgur.com/NeeEMtr.png) | ![Free Match](https://i.imgur.com/lhqItPA.png) |

| Sports Match | Completed Match |
| :---: | :---: |
| ![Sports Match](https://i.imgur.com/dbXH3o0.png) | ![Completed Match](https://i.imgur.com/ccg81BA.png) |

| Statistics |
| :---: |
| ![Statistics](https://i.imgur.com/cgf6isq.png) |

---

## Table of Contents

- Overview
- Main Features
- Commands (for everyone, managers, admins)
- Ranks & Certifications
- Leaderboards
- Initial Setup (quick)
- Premium and Partnerships
- Support & Help
- Credits
- Roadmap

---

## Overview

PronoBot transforms your Discord server into a friendly betting platform:
- Create matches (sports or custom).
- Members can bet virtual coins.
- Automatic match resolution and statistics updates.
- Leaderboards and ranks to encourage competition.

Everything is designed to be accessible to the general public — no technical knowledge required.

---

## Main Features

- **⭐ Level and XP System**: Earn experience with every action (daily, won/lost bets) and level up! Each server has its own progression system.
- **💰 Real-time Balance Display**: Your balance and maximum bet are displayed directly in the betting modal for clarity.
- **📊 New Balance After Each Bet**: Receive a private message after each win/loss with your updated new balance.
- **🚫 Restriction System**: Managers can restrict users to prevent them from betting (configurable role).
- **✨ Improved Interface**: Visual emojis for match statuses (✅ open, 🔒 closed, ⏳ pending).
- Virtual economy: initial coins, daily rewards, winnings/losses.
- Simple and fast betting (choice, amount).
- Match creation and management (sports or free).
- Automatic resolution and winnings distribution.
- Leaderboards (level, wins, win rate, losses, profit ratio).
- Global ranks (Player, VIP, Champion, Partner, Staff, etc.) and certification badges.
- Role-based permissions (Admin, Manager, Restricted).
- Slash commands, context menus, and user-friendly interface.
- Ability to enable/disable commands per server.

---

## Main Commands

All commands are Slash Commands **{/}**. There are also commands in a user's context menu _(right-click on a user > Apps)_

### User Commands

The commands below are for regular users.

- /pb open
    Create a PronoBot account on the server and receive welcome coins.

- /pb close
    Permanently delete your account on this server (confirmation required).

- /pb balance
    See your current balance.

- /pb daily
    Claim your daily reward (configurable cooldown and reward).

- /pb coinflip <choice>
    Flip a coin to try heads or tails.

- /pb stats [user]
    See detailed statistics of a player (rankings, winnings, etc.).

- /pb mybets
    See your active bets.

- /pb top [category]
    See leaderboards (default Top 5, or Top 10 for a specific category).
    Categories: level, wins, winrate, losses, profitratio

- /vote
    Vote for PronoBot on Top.gg and support the project. The embed explains why voting is important to help us grow.

- /pbpremium
    Display information about premium subscription.

- /bet
    Place a bet on an available match (select match → choice → amount).

- /removebet
    Cancel a bet as long as the match isn't closed.

- Context menu (right-click > Apps)
    Quickly view stats or information about a user.


### Management Commands (Configurable "Manager" Role)

These commands are reserved for users with the Manager role (configurable).

- /creatematch
    Create a sports match (_2 teams and a draw_) or a free match (_multiple choices like a Twitch poll_). Title, choices, and bet closing deadline configurable.

- /editmatch
    Edit an existing match. **Now with selection menu** - no need to search for the match ID!

- /deletematch
    Delete a match and refund bets. **Now with selection menu** - choose the match from an interactive list.

- /closematch
    Close a match and set the result — automatic winnings/losses distribution.

- /setdeadline <match>
    Modify the betting deadline for a match.

- /listmatches
    List all active matches (option to view completed matches too).

- /listallmatches
    Display ALL matches (open, closed, completed) without filters for a quick overview.

- /restrict <user>
    Restrict a user by applying the configured restricted role, preventing them from betting.

- /unrestrict <user>
    Remove a user's restriction so they can bet normally again.

- /serverinfo, /botinfo
    Server configuration and bot technical status information.

### Administrator Commands (Configurable "Admin" Role)

These commands are reserved for users with administrator permission or the Admin role (configurable).

- /pbconfig [option] [value]
    Configure the server (roles, channels, amounts, etc.). Example: /pbconfig initialcoins 500

    Tip: First configure the admin role with /pbconfig adminrole <your server admin role> and the manager role with /pbconfig managerrole <role that will manage matches>

- /pbviewconfig
    Display the server's current configuration.

- /togglecommand <action> <command>
    Enable/disable a command on the server (includes list to see disabled ones).

- /pb userinfo <user>
    Complete information about a user (Discord info + PronoBot info).
    (also available in context menu)

- /wipeuserdata
    **⚠️ DANGEROUS COMMAND** - Resets all user data on the server (coins, statistics, bets).
    Requires typing "CONFIRM" in a modal to validate. Server settings are preserved.
    _e.g., for a season system?_
    **This action is irreversible!**

- /pbadmin [add/remove/set/giveall] <user> <amount>
    Manage player coins.
    _Example: /pbadmin add @user 100_

---

## Ranks & Certifications

Ranks are global and visible on all servers where PronoBot is present:

- Player — default rank.
- VIP — premium access.
- Champion — elite players.
- Partner — official partners.
- Staff — bot moderation team.
- Owner — bot owner.

Certification: visible badge indicating the player is verified.

Ranks mainly serve to recognize top players and distinguish trusted members (staff).

---

## Leaderboards and Level System

### 🏆 Leaderboards

Five main categories:

1. **Level** — progression based on earned XP (unique to each server).
2. Wins — total number of won bets.
3. Win Rate — percentage of won bets (minimum 5 bets required).
4. Losses — total number of lost bets.
5. Profit Ratio — coins won / coins lost (minimum: at least 1 loss).

### ⭐ Experience and Level System

The XP and level system is **entirely unique to each server** — your levels and XP are independent from server to server.

**How to earn XP:**
- **Daily reward (/pb daily)**: +10 fixed XP
- **Won bets**: 20 base XP + 5% of coins won (min 20 XP, max 200 XP per bet)
- **Lost bets**: +5 XP (participation reward)

**Level progression:**
- Required XP formula: `(Level - 1)² × 100`
  - Level 1: 0 XP (starting point)
  - Level 2: 100 XP
  - Level 3: 400 XP
  - Level 4: 900 XP
  - Level 5: 1,600 XP
  - Level 10: 8,100 XP

**Display:**
- Your level and XP are visible in `/pb stats`
- Progress bar showing advancement to next level
- Level leaderboard available in `/pb top level`

Clear display with position: example "#2 out of 25". Players without enough data don't appear in certain categories.

---

## Initial Setup (Quick)

1. Invite the bot to your server.
2. Set roles via /pbconfig (adminrole, managerrole, restrictedrole).
3. Set channels via /pbconfig: announcements, bet-only channel, match announcement channel.
4. Set economic parameters: initialcoins (amount given when creating a PronoBot account), dailyamount (amount given by /pb daily, once per day).
5. Create a first match with /creatematch and test betting as a user.

Tip: start with small values (starting coins and daily reward) to test the system before increasing.

---

## Premium and Partnerships

The premium version takes your server to the next level — the bot will have unique features like **custom image generation** that replace Discord's classic embeds!

To become an **official PronoBot partner** and get direct support from staff plus **free Premium subscription**, please open a ticket on the [official Discord](https://discord.gg/rbrPpWbEnV) _(https://discord.gg/rbrPpWbEnV)_

## Support & Help

- Join the Discord server (https://discord.gg/rbrPpWbEnV) to ask for help.
- Open a ticket on Discord if you encounter a bug or want to make a suggestion.
- Quick FAQ:
    - "Bot doesn't respond" → check that the bot is online and has necessary permissions.
    - "I can't create matches" → verify you've configured admin and manager roles plus channels in /pbconfig
    - "You don't have an account" → use /pb open.
    - "Command disabled" → an administrator may have disabled it (/togglecommand list).

---

## Credits

Developed by Zyksa and Hokanosekai ❤️

Uses Node.js and a database (Supabase) to store accounts and statistics.

---

## Roadmap (Future Ideas)

- Leagues and divisions
- Dynamic matches (odds fluctuate based on bet numbers)
- Combo bets
- Seasonal events
- Reward shop
- Daily quests and achievements
- Web dashboard and API for statistics

---

Thank you for using PronoBot! Transform your server into a friendly and competitive betting arena. 🎲🏆
