# 🎲 PronoBot — Bot Discord de Bookmaker (Pronostics en tout genre) 100% configurable

**[🇫🇷 Français](#-pronobot--bot-discord-de-bookmaker-pronostics-en-tout-genre-100-configurable) | [🇬🇧 English](#-pronobot--customizable-discord-bookmaker-bot)**

![Discord](https://img.shields.io/badge/Discord-Bot-7289da?style=for-the-badge&logo=discord)
![Node.js](https://img.shields.io/badge/Node.js-v24+-339933?style=for-the-badge&logo=node.js)
![License](https://img.shields.io/badge/License-GPL--3.0-blue?style=for-the-badge)

PronoBot est un bot Discord pensé pour gérer des paris sportifs sur votre serveur avec une économie virtuelle, des classements, des grades, un système de certification et un système de **niveaux et XP**. Simple à utiliser et complétement configurable, il permet de créer des matchs, placer des paris, suivre les statistiques et organiser des compétitions entre membres.

Il y a 3 types de match disponibles :

- Le match sport, on rentre le nom de l'équipe A, sa côte, le nom de l'équipe B, sa côte ainsi que la côte du Match Nul.
- Le match libre, question personnalisée et jusqu'à 9 choix possibles (avec côte pour chaques choix) à la manière des sondages twitch ou encore des paris avec comme réponse "Oui/Non"
- Le match **Bookmaker**, sans image personnalisée : les cotes 1/N/2 évoluent en direct selon les mises. La cote acceptée est figée pour chaque pari et ce pari ne peut pas être retiré.

---

Le code source est distribué sous licence **GPL-3.0** et le bot est **certifié** par Discord _(+ de 100 serveurs l'ont déjà adopté)_. Pour les questions d'exploitation ou de partenariat, rejoignez le [Discord officiel](https://discord.gg/VU3q8MKkDJ).

| Application Vérifiée ☺️ |
| :---: |
| ![Statistiques](https://i.imgur.com/3uAEI0s.png) |

---

## Ajouter le bot à votre serveur

Pour ajouter le bot à votre serveur il vous suffit de vous rendre sur ce [lien](https://discord.com/oauth2/authorize?client_id=835256483356737546&permissions=8&integration_type=0&scope=bot+applications.commands)

Ensuite, suivez les étapes indiquée dans la partie "**Configuration initiale**"

---

## Aperçu

Les visuels présentés peuvent évoluer au fil des mises à jour 😏.
À noter : la génération de visuels personnalisés (canvas customisés) est réservé aux serveurs premium/partenaires.

Tous les Canvas utilisent la même direction artistique sombre premium, avec une hiérarchie et des couleurs d'état communes. Pour générer localement une planche de prévisualisation de tous les visuels :

```bash
npm run preview:canvas
```

Les PNG sont créés dans `docs/assets/canvas-previews/`. Un autre dossier peut être fourni en argument avec `npm run preview:canvas -- /chemin/de/sortie`.

| Pari | Configuration |
| :---: | :---: |
| ![Pari](https://i.imgur.com/91F5sDA.png) | ![Configuration](https://i.imgur.com/cXIf4QX.png) |

| Gain | Match Libre |
| :---: | :---: |
| ![Gain](https://i.imgur.com/SAaciFC.png) | ![Match Libre](https://i.imgur.com/zI6aDQZ.png) |

| Match Sport | Match Terminé |
| :---: | :---: |
| ![Match Sport](https://i.imgur.com/W7Ary4P.png)<br>![Match Sport Canva](https://i.imgur.com/wZGsryT.png) | ![Match Terminé](https://i.imgur.com/XFypLC6.png)<br>![Match Terminé Canva](https://i.imgur.com/yH4GQYj.png) |

| Statistiques |
| :---: |
| ![Statistiques](https://i.imgur.com/dhJKZqT.png) |
| *Stats d'un utilisateur sur un serveur anglophone!* |

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
- **🏆 Classements dynamiques** : 6 catégories de classement (niveau, victoires, taux de réussite, défaites, ratio gains/pertes, solde) pour une compétition saine entre membres.
- **🎖️ Grades globaux** : Grades visibles sur tous les serveurs (Joueur, VIP, Champion, Partenaire, Staff, Owner) avec badges de certification.

### 💰 Économie Virtuelle
- **Pièces virtuelles** : Montant de départ configurable, récompenses quotidiennes et gestion complète des gains/pertes.
- **Orbes globales** : Le solde d'Orbes `<:orbes:1522970669929861322>` d'un joueur est identique sur tous les serveurs et visible uniquement dans `/pb stats`.
- **💳 Affichage en temps réel** : Votre solde actuel et mise maximale sont affichés directement dans la modal de pari pour plus de clarté.
- **📊 Notifications de solde** : Recevez un message privé après chaque pari avec votre nouveau solde mis à jour.
- **💰 Classement par solde** : Classement dédié pour voir qui possède le plus de pièces sur le serveur (`/baltop` ou `/pb top balance`).

### 🎲 Gestion des Matchs
- **Trois types de matchs** : sportifs, libres, ou Bookmaker à cotes dynamiques.
- **Marché dynamique solvable** : chaque match Bookmaker possède une réserve de risque. PostgreSQL refuse atomiquement toute mise qui ferait dépasser `paiement maximal ≤ mises collectées + réserve`.
- **Cote garantie** : la cote visible est contrôlée à la validation. Si elle a changé, aucun débit n'a lieu; une fois acceptée, le paiement potentiel reste figé même si le marché évolue.
- **Embed live** : l'annonce est actualisée après les paris, sans Canvas ni image premium. Les paris Bookmaker sont définitifs; seuls l'annulation ou la suppression administrative les remboursent.
- **Paris simples et rapides** : Interface intuitive pour choisir et miser en quelques clics.
- **Résolution automatique** : Distribution instantanée des gains lors de la clôture d'un match.

#### 📈 Comment fonctionne un match Bookmaker ?

1. **Création du marché** : un gestionnaire choisit le type `Bookmaker`, renseigne les deux équipes et définit les cotes de départ pour la victoire de l'équipe 1, le match nul et la victoire de l'équipe 2 (1/N/2).
2. **Cotes en mouvement** : les cotes sont recalculées après chaque pari accepté. Plus un résultat attire de mises, plus sa cote tend à diminuer; les autres résultats peuvent alors devenir plus intéressants. La réserve de risque évite les variations excessives et protège l'économie du serveur.
3. **Affichage en direct** : le message Discord du match est un embed sans image personnalisée. Il affiche les dernières cotes disponibles, la cagnotte totale, la réserve, la mise maximale et la deadline, puis s'actualise automatiquement après les paris.
4. **Validation au dernier instant** : lorsque le joueur confirme sa mise, PronoBot compare la cote affichée avec la cote réellement disponible. Si elle a changé entre-temps, le pari est refusé sans débiter de pièces et le joueur peut recommencer avec la nouvelle cote.
5. **Cote et gain verrouillés** : dès que le pari est accepté, sa cote et son gain potentiel sont enregistrés définitivement. Par exemple, un pari validé à `4,00` reste à `4,00`, même si la cote descend ensuite à `2,50`.
6. **Protection contre la création excessive de pièces** : la base de données vérifie en une seule opération que le paiement maximal promis reste couvert par les mises collectées et la réserve du match. Une mise trop risquée est refusée sans débit.
7. **Pari non annulable** : un pari Bookmaker accepté ne peut pas être retiré par le joueur, même avant la deadline, afin d'empêcher toute manipulation des cotes. `/pb mybets` le range dans **« Non annulables (match à cotes dynamiques) »**. Si un gestionnaire supprime ou annule le match, les mises sont néanmoins remboursées.
8. **Clôture du résultat** : à la fin du match, le gestionnaire choisit le résultat gagnant et PronoBot distribue les gains à partir de la cote individuelle enregistrée pour chaque pari.

### 🛡️ Administration & Modération
- **🚫 Système de restriction** : Les managers peuvent restreindre des utilisateurs pour les empêcher de parier via un rôle configurable.
- **🔐 Permissions par rôles** : Gestion fine des permissions (Admin, Manager, Restreint) pour un contrôle total.
- **⚙️ Commandes activables/désactivables** : Possibilité d'activer ou désactiver des commandes spécifiques par serveur.
- **🔔 Ping de rôle** : Configurez un rôle à mentionner automatiquement lors de la création d'un nouveau match pour notifier les membres.

### ✨ Interface Moderne
- **Commandes slash (/)** : Toutes les commandes utilisent le système moderne de Discord.
- **Menu contextuel** : Accès rapide aux statistiques via clic droit sur un utilisateur.
- **Emojis visuels** : Statuts de matchs clairs (🟢 ouvert, 🔴 fermé, 🏁 terminé).
- **🌍 Descriptions bilingues** : Les descriptions des commandes s'affichent automatiquement en français ou en anglais selon la langue du client Discord.

### ⚡ Performances et fiabilité
- **Réponses plus rapides** : Les statistiques, classements, configurations et listes de matchs sont chargés plus efficacement.
- **Économie atomique** : Les paris, récompenses et gains restent fiables lorsque plusieurs joueurs agissent simultanément.
- **Infrastructure optimisée** : La base de données, le sharding et la mémoire ont été retravaillés pour améliorer la fluidité et la stabilité du bot.

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
    Voir votre solde actuel. L'option `privee` permet de rendre la réponse éphémère.

- /pb daily
    Récupérer la récompense quotidienne (cooldown et gain configurable).

- /pb coinflip <choix>
    Lancer une pièce pour tenter le pile ou face.

- /pb stats [utilisateur]
    Voir les statistiques détaillées d'un joueur, dont son solde global d'Orbes. Les options `utilisateur` et `privee` sont facultatives.

- /pb mybets
    Voir vos paris en cours, séparés entre paris annulables, Bookmaker non annulables et matchs fermés/deadline dépassée. L'option `privee` est facultative.

- /pb top [catégorie]
    Voir les classements (par défaut Top 5, sinon Top 10 pour une catégorie donnée).
    Catégories : `level`, `wins`, `winrate`, `losses`, `profitratio`, `balance`. L'option `privee` est facultative.

- /balance <joueur>
    Consulter le solde en pièces d'un joueur spécifique, publiquement ou avec l'option `privee`.

- /baltop
    Voir le classement des joueurs par solde (Top 10), publiquement ou avec l'option `privee`.

- /history
    Consulter et parcourir vos 50 derniers mouvements de pièces : paris, gains, remboursements, récompenses et opérations administratives.

- /help [mode]
    Ouvrir l'aide interactive. Le mode facultatif `joueurs` affiche les commandes publiques et `staff` inclut les commandes de gestion.

- /ping
    Vérifier la latence Discord, la base de données, la mémoire et l'état du bot.

- /partenaires
    Afficher la liste des serveurs partenaires officiels de PronoBot.

- /vote
    Voter pour PronoBot sur Top.gg et soutenir le projet. L'embed explique pourquoi voter est important pour nous aider à grandir.

- /support
    Contacter le support PronoBot, proposer une amélioration ou rejoindre le serveur officiel. Les demandes sont privées et transmettent automatiquement le contexte du serveur à l'équipe.

- /pbpremium
    Afficher des informations sur l'abonnement premium.

- /bet
    Placer un pari sur un match disponible. Naviguez entre les matchs avec ◀ ▶, consultez la liste complète des matchs actifs avec 📋, puis choisissez votre option et misez.

- /removebet
    Annuler un pari tant que le match n'est pas clos. Un pari Bookmaker à cotes dynamiques n'est jamais retirable par le joueur.

- /listmatches [status]
    Lister les matchs en filtrant facultativement par `open`, `closed`, `completed` ou `all`.

- /listallmatches
    Afficher tous les matchs ouverts, fermés et terminés sans filtre.

- Menu contextuel (clic droit > Apps)
    Voir rapidement les stats ou informations d’un utilisateur.


### Commandes de gestion (Rôle "Manager" configurable)

Ces commandes sont réservés aux utilisateurs qui possèdent le rôle assigné comme Manager (configurable)

- /match create
    Créer un match sport, libre ou Bookmaker à cotes dynamiques. Pour Bookmaker, saisissez les cotes de base 1/N/2; l'annonce live sans image est créée automatiquement.

- /match edit
    Modifier un match existant.

- /match delete
    Supprimer un match et rembourser les paris.

- /match cancel
    Annuler un match, rembourser tous les paris et envoyer aux parieurs un message privé contenant la raison de l'annulation.

- /match close
    Clôturer un match et définir le résultat — distribution automatique des gains/pertes.

- /match deadline
    Modifier la date limite pour parier sur un match.

- /restrict <utilisateur>
    Restreindre un utilisateur en lui appliquant le rôle restreint configuré, l'empêchant de parier.

- /unrestrict <utilisateur>
    Retirer la restriction d'un utilisateur pour qu'il puisse à nouveau parier normalement.

- /serverinfo, /botinfo
    Informations sur le serveur et sa configuration ainsi que l'état technique du bot.

- /contact <message>
    Envoyer un message à l'administration de PronoBot avec le contexte du serveur. Cette commande historique destinée aux gestionnaires coexiste avec `/support`, accessible à tous.

### Commandes administrateur (Rôle "Admin" configurable)

Ces commandes sont réservés aux utilisateurs qui ont la permission administrateur ou qui possèdent le rôle assigné comme Admin (configurable)

- /pb config [option] [valeur]
    Configurer le serveur (rôles, canaux, montants, paramètres de notification, etc.). Exemple: /pb config initialcoins 500

    Rôles : `adminrole`, `managerrole`, `restrictedrole`.

    Économie : `initialcoins`, `dailyamount`, `minbet`, `maxbet`, `dynamicreserve`.

    Canaux : `announcementschannel`, `betschannel`, `matcheschannel`, `logschannel`, `levelupchannel`, `activitemembreschannel`.

    Interface et comportement : `language` (`fr`/`en`), `usepremiumimages`, `logslevel` (`none`/`normal`/`detailed`), `pingenabled`, `pingrole`, `closerecap`, `levelupenabled`, `activitemembres`, `cacherparis`, `commandesdejeux`.

    Option Bookmaker : `dynamicreserve` définit le risque net maximal de chaque **nouveau** match dynamique. La réserve et la mise maximale sont figées à sa création. Exemple : `/pb config dynamicreserve 10000`.

    La réserve est une cagnotte de sécurité virtuelle : elle n'est ni prélevée sur un joueur ni distribuée automatiquement. Une réserve élevée stabilise les cotes; une réserve faible les fait réagir plus vite. La valeur conseillée est d'environ **20 × la mise maximale** (`10 000` pour une mise maximale de `500`).

    Conseil: Configurer en 1er le role administrateur avec /pb config adminrole <role admin de votre serveur> ainsi que le role manager avec /pb config managerrole <role qui permettra de gérer les matchs>

- /pb viewconfig
    Afficher la configuration actuelle du serveur.

- /pb config (option commandesdejeux)
    Activer ou désactiver les jeux (coinflip, etc.) sur le serveur.

- /togglecommand <disable|enable|list> [commande]
    Désactiver, réactiver ou lister les commandes désactivées sur le serveur.

- /tutorial
    Publier dans le salon courant le tutoriel interactif de prise en main de PronoBot.

- /pb userinfo <utilisateur>
    Informations complètes sur un utilisateur (infos Discord + infos PronoBot).
    (disponible aussi dans le menu contextuel)

- /wipeuserdata
    **⚠️ COMMANDE DANGEREUSE** - Réinitialise toutes les données utilisateurs du serveur (pièces, statistiques, paris).
    Nécessite de taper "CONFIRMER" dans une modal pour valider. Les paramètres du serveur sont conservés.
    _par exemple pour faire un système de saisons?_
    **Cette action est irréversible !**

- /coins add|remove|set <utilisateur> <montant>
    Ajouter, retirer ou définir les pièces d'un joueur. _Exemple : `/coins add @user 100`._

- /coins giveall <montant>
    Ajouter des pièces à tous les comptes du serveur. Cette sous-commande est également accessible au rôle Manager.

### Commandes du propriétaire du bot

Ces commandes sont déployées uniquement sur le serveur d'administration et vérifient l'identité du propriétaire du bot.

- /giveorbs <all ou ID utilisateur> <montant>
    Distribuer des Orbes globales à un utilisateur ou à tous les comptes existants.

- /broadcast <message> [title]
    Diffuser une annonce sur tous les serveurs où PronoBot est présent.

- /certify add|remove|check <userid> et /certify list
    Gérer et consulter les certifications globales.

- /setrank <userid> <rank> et /listrank
    Attribuer un grade global (`player`, `vip`, `champion`, `partner`, `staff`, `owner`) et lister les utilisateurs gradés.

- /setpremium activate|deactivate|extend|check
    Activer, désactiver, prolonger ou consulter le Premium d'un serveur à partir de son ID.

- /globalstats [période], /performance [action], /server getinfo <serverid>
    Consulter les statistiques globales, les performances et les informations d'un serveur.

- /reload
    Recharger les commandes du bot après une mise à jour.

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

Six catégories principales :

1. **Niveau** — progression basée sur l'XP gagnée (propre à chaque serveur).
2. Victoires — nombre total de paris gagnés.
3. Taux de victoire — pourcentage de paris gagnés (minimum requis : 5 paris).
4. Défaites — nombre total de paris perdus.
5. Ratio Gains/Pertes — pièces gagnées / pièces perdues (minimum : au moins 1 perte).
6. Solde — nombre de pièces actuellement possédées.

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
2. Définissez les rôles via /pb config (adminrole, managerrole, restrictedrole).
3. Définissez les canaux via /pb config : annonces, salon réservés aux paris, salon d'annonces des matchs.
4. Définissez les paramètres économiques : `initialcoins`, `dailyamount`, `minbet`, `maxbet` et, pour les matchs Bookmaker, `dynamicreserve` (10 000 par défaut).
5. (Optionnel) Activez les pings de match avec `/pb config pingenabled true` et définissez le rôle à mentionner avec `/pb config pingrole <rôle>`.
6. Créez un premier match avec /match create et testez les paris en tant qu'utilisateur.

Conseil : commencez avec de petites valeurs (pièces de départ et récompense quotidienne) pour tester le système avant d’augmenter.

---

## Premium et Partenariats

La version premium permet de faire passer votre serveur à un niveau supérieur, le bot aura des fonctionnalités uniques telles que la génération d'**images personnalisées** qui remplaceront les embeds classiques de discord ! Les matchs Bookmaker conservent toujours leur embed live sans image afin que les cotes puissent être actualisées immédiatement.

Pour devenir un **partenaire officiel** de PronoBot et ainsi avoir accès à un support direct avec le staff et l'abonnement **Premium gratuitement**, rejoignez le [Discord officiel](https://discord.gg/VU3q8MKkDJ).

## Support & Aide

- Utilisez `/support` pour envoyer une demande d'aide ou une suggestion directement à l'équipe.
- Rejoignez le serveur Discord officiel : https://discord.gg/VU3q8MKkDJ
- FAQ rapide :
    - "Le bot ne répond pas" → vérifier que le bot est en ligne et a les permissions nécessaires.
    - "Je ne peux créer des matchs" → vérifier que vous avez bien configurer les rôles admins et manager ainsi que les salons dans le /pb config
    - "Vous n'avez pas de compte" → utilisez /pb open.
    - "Commande désactivée" → un administrateur peut avoir désactivé les jeux (/pb config commandesdejeux).

---

## Crédits

Développé par Zyksa et Hokanosekai ❤️

Utilise Node.js et une base de données (supabase) pour stocker les comptes et statistiques.

---

## Roadmap (idées futures)

- Ligues et divisions
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
![Node.js](https://img.shields.io/badge/Node.js-v24+-339933?style=for-the-badge&logo=node.js)
![License](https://img.shields.io/badge/License-GPL--3.0-blue?style=for-the-badge)

PronoBot is a Discord bot designed to manage betting on your server with a virtual economy, rankings, ranks, a certification system, and a **Level & XP system**. Easy to use and fully configurable, it allows you to create matches, place bets, track statistics, and organize competitions among members.

There are 3 match types available:

- Sports match: enter Team A's name, its odds, Team B's name, its odds, and the Draw odds.
- Free match: custom question and up to 9 possible choices (with odds for each choice) like Twitch polls or "Yes/No" bets.
- **Sportsbook match**, always rendered without custom images: 1/X/2 odds update live as stakes arrive. Every accepted bet keeps its quoted odds and cannot be removed.

---

The source code is distributed under the **GPL-3.0** license, and the bot is **verified** by Discord _(over 100 servers have already adopted it)_. For operations or partnership questions, join the [official Discord](https://discord.gg/VU3q8MKkDJ).

| Verified Application ☺️ |
| :---: |
| ![Statistics](https://i.imgur.com/3uAEI0s.png) |

---

## Add the Bot to Your Server

To add the bot to your server, simply go to this [link](https://discord.com/oauth2/authorize?client_id=835256483356737546&permissions=8&integration_type=0&scope=bot+applications.commands)

Then, follow the steps in the "**Initial Setup**" section.

---

## Preview

The visuals shown may evolve over future updates 😏.
Note: Custom visual generation (custom canvases) is reserved for premium/partner servers.

Every Canvas follows the same dark premium art direction, shared hierarchy and status colours. Generate a local preview sheet for every visual with `npm run preview:canvas`; PNG files are written to `docs/assets/canvas-previews/` by default.

| Bet | Configuration |
| :---: | :---: |
| ![Bet](https://i.imgur.com/91F5sDA.png) | ![Configuration](https://i.imgur.com/cXIf4QX.png) |

| Win | Free Match |
| :---: | :---: |
| ![Win](https://i.imgur.com/SAaciFC.png) | ![Free Match](https://i.imgur.com/zI6aDQZ.png) |

| Sports Match | Completed Match |
| :---: | :---: |
| ![Sports Match](https://i.imgur.com/W7Ary4P.png)<br>![Sports Match Canvas](https://i.imgur.com/wZGsryT.png) | ![Completed Match](https://i.imgur.com/XFypLC6.png)<br>![Completed Match Canvas](https://i.imgur.com/yH4GQYj.png) |

| Statistics |
| :---: |
| ![Statistics](https://i.imgur.com/dhJKZqT.png) |
| *User stats on an English-speaking server!* |

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

### 🎮 Progression System
- **⭐ Level and XP**: Earn experience with every action (daily reward, won or lost bets) and level up! Each server has its own independent progression system.
- **🏆 Dynamic Leaderboards**: 6 ranking categories (level, wins, win rate, losses, profit ratio, balance) for healthy competition among members.
- **🎖️ Global Ranks**: Ranks visible across all servers (Player, VIP, Champion, Partner, Staff, Owner) with certification badges.

### 💰 Virtual Economy
- **Virtual Coins**: Configurable starting amount, daily rewards, and complete winnings/losses management.
- **Global Orbs**: A player's Orb balance is shared across every server and is only displayed in `/pb stats`.
- **💳 Real-time Display**: Your current balance and maximum bet are displayed directly in the betting modal for clarity.
- **📊 Balance Notifications**: Receive a private message after each bet with your updated new balance.
- **💰 Balance Leaderboard**: Dedicated leaderboard to see who has the most coins on the server (`/baltop` or `/pb top balance`).

### 🎲 Match Management
- **Three match types**: sports, free, and Sportsbook with dynamic odds.
- **Solvent dynamic market**: every Sportsbook match snapshots a risk reserve. PostgreSQL atomically rejects a stake if it would violate `maximum payout ≤ collected stakes + reserve`.
- **Guaranteed quote**: the displayed quote is checked at submission. If it moved, no coins are debited; after acceptance, the potential payout remains locked even when later odds change.
- **Live embed**: the announcement refreshes after bets and never uses Canvas or a premium image. Sportsbook bets are final; only an administrative cancellation or deletion refunds them.
- **Simple and fast betting**: Intuitive interface to choose and bet in just a few clicks.
- **Automatic resolution**: Instant winnings distribution when closing a match.

#### 📈 How does a Sportsbook match work?

1. **Market creation**: a manager selects `Sportsbook`, enters both teams, and sets the starting odds for team 1, the draw, and team 2 (1/X/2).
2. **Moving odds**: odds are recalculated after every accepted bet. As an outcome attracts more stakes, its odds tend to decrease while the other outcomes may become more attractive. The risk reserve smooths those movements and protects the server economy.
3. **Live display**: the Discord announcement is an image-free embed showing the latest odds, total pool, reserve, maximum stake, and deadline. It refreshes automatically after bets.
4. **Last-second validation**: when a player confirms a stake, PronoBot compares the displayed odds with the currently available quote. If it moved, the bet is rejected without debiting coins and the player can try again using the new odds.
5. **Locked quote and payout**: once accepted, the bet's odds and potential payout are permanently recorded. For example, a bet accepted at `4.00` remains at `4.00` even if the market later drops to `2.50`.
6. **Protection against excessive coin creation**: the database atomically verifies that the highest promised payout remains covered by collected stakes and the match reserve. An unsafe stake is rejected without a debit.
7. **Final bet**: players cannot remove an accepted Sportsbook bet, even before the deadline, preventing odds manipulation. `/pb mybets` lists it under **“Not cancelable (dynamic-odds match)”**. Stakes are still refunded if a manager deletes or cancels the match.
8. **Settlement**: when the event ends, the manager selects the winning result and PronoBot distributes winnings using the individual odds stored for each bet.

### 🛡️ Administration & Moderation
- **🚫 Restriction System**: Managers can restrict users to prevent them from betting via a configurable role.
- **🔐 Role-based Permissions**: Fine-grained permission management (Admin, Manager, Restricted) for total control.
- **⚙️ Toggleable Commands**: Ability to enable or disable specific commands per server.
- **🔔 Role Ping**: Configure a role to be automatically mentioned when a new match is created to notify members.

### ✨ Modern Interface
- **Slash Commands (/)**: All commands use Discord's modern system.
- **Context Menu**: Quick access to statistics via right-click on a user.
- **Visual Emojis**: Clear match statuses (🟢 open, 🔴 closed, 🏁 completed).
- **🌍 Bilingual Descriptions**: Command descriptions automatically display in French or English based on the user's Discord client language.

### ⚡ Performance and reliability
- **Faster responses**: Statistics, leaderboards, configurations, and match lists are loaded more efficiently.
- **Atomic economy**: Bets, rewards, and payouts remain reliable when several players act simultaneously.
- **Optimized infrastructure**: Database access, sharding, and memory management were reworked to improve speed and overall stability.

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
    See your current balance. The optional `privee` switch makes the response ephemeral.

- /pb daily
    Claim your daily reward (configurable cooldown and reward).

- /pb coinflip <choice>
    Flip a coin to try heads or tails.

- /pb stats [user]
    See detailed player statistics, including their global Orb balance. The `utilisateur` and `privee` options are optional.

- /pb mybets
    See active bets grouped into cancelable bets, locked Sportsbook bets, and closed/deadline-expired matches. The `privee` option is optional.

- /pb top [category]
    See leaderboards (default Top 5, or Top 10 for a specific category).
    Categories: `level`, `wins`, `winrate`, `losses`, `profitratio`, `balance`. The `privee` option is optional.

- /balance <player>
    Check a player's coin balance publicly or with the optional `privee` switch.

- /baltop
    See the top 10 players ranked by balance, publicly or with the optional `privee` switch.

- /history
    Browse your latest 50 coin movements, including bets, winnings, refunds, rewards, and administrative operations.

- /help [mode]
    Open the interactive help. Optional mode `joueurs` shows public commands, while `staff` also includes management commands.

- /ping
    Check Discord latency, database latency, memory usage, and bot health.

- /partenaires
    Display PronoBot's official partner servers.

- /vote
    Vote for PronoBot on Top.gg and support the project. The embed explains why voting is important to help us grow.

- /support
    Contact the PronoBot team, suggest an improvement, or join the official Discord server. Requests are private and automatically include the relevant server context.

- /pbpremium
    Display information about premium subscription.

- /bet
    Place a bet on an available match. Navigate between matches with ◀ ▶, view a full list of active matches with 📋, then pick your choice and place your bet.

- /removebet
    Cancel a bet as long as the match isn't closed. Dynamic Sportsbook bets can never be removed by the player.

- /listmatches [status]
    List matches with an optional `open`, `closed`, `completed`, or `all` status filter.

- /listallmatches
    Display every open, closed, and completed match without a filter.

- Context menu (right-click > Apps)
    Quickly view stats or information about a user.


### Management Commands (Configurable "Manager" Role)

These commands are reserved for users with the Manager role (configurable).

- /match create
    Create a sports, free, or dynamic Sportsbook match. Sportsbook creation takes base 1/X/2 odds and automatically publishes the live, image-free announcement.

- /match edit
    Edit an existing match.

- /match delete
    Delete a match and refund bets.

- /match cancel
    Cancel a match, refund every bet, and DM bettors with the cancellation reason.

- /match close
    Close a match and set the result — automatic winnings/losses distribution.

- /match deadline
    Modify the betting deadline for a match.

- /restrict <user>
    Restrict a user by applying the configured restricted role, preventing them from betting.

- /unrestrict <user>
    Remove a user's restriction so they can bet normally again.

- /serverinfo, /botinfo
    Server configuration and bot technical status information.

- /contact <message>
    Send a message to PronoBot administration with the server context. This legacy manager command coexists with the public `/support` command.

### Administrator Commands (Configurable "Admin" Role)

These commands are reserved for users with administrator permission or the Admin role (configurable).

- /pb config [option] [value]
    Configure the server (roles, channels, amounts, notification settings, etc.). Example: /pb config initialcoins 500

    Roles: `adminrole`, `managerrole`, `restrictedrole`.

    Economy: `initialcoins`, `dailyamount`, `minbet`, `maxbet`, `dynamicreserve`.

    Channels: `announcementschannel`, `betschannel`, `matcheschannel`, `logschannel`, `levelupchannel`, `activitemembreschannel`.

    Interface and behavior: `language` (`fr`/`en`), `usepremiumimages`, `logslevel` (`none`/`normal`/`detailed`), `pingenabled`, `pingrole`, `closerecap`, `levelupenabled`, `activitemembres`, `cacherparis`, `commandesdejeux`.

    Sportsbook option: `dynamicreserve` sets the maximum net risk for each **new** dynamic match. The reserve and maximum bet are snapshotted when the market is created. Example: `/pb config dynamicreserve 10000`.

    The reserve is a virtual safety pool: it is neither taken from a player nor automatically distributed. A higher reserve makes odds more stable, while a lower reserve makes them react faster. A sensible value is around **20 × the maximum bet** (`10,000` for a maximum bet of `500`).

    Tip: First configure the admin role with /pb config adminrole <your server admin role> and the manager role with /pb config managerrole <role that will manage matches>

- /pb viewconfig
    Display the server's current configuration.

- /pb config (option commandesdejeux)
    Enable or disable games (coinflip, etc.) on the server.

- /togglecommand <disable|enable|list> [command]
    Disable, re-enable, or list disabled commands on the server.

- /tutorial
    Publish PronoBot's interactive onboarding tutorial in the current channel.

- /pb userinfo <user>
    Complete information about a user (Discord info + PronoBot info).
    (also available in context menu)

- /wipeuserdata
    **⚠️ DANGEROUS COMMAND** - Resets all user data on the server (coins, statistics, bets).
    Requires typing "CONFIRM" in a modal to validate. Server settings are preserved.
    _e.g., for a season system?_
    **This action is irreversible!**

- /coins add|remove|set <user> <amount>
    Add, remove, or set a player's coins. _Example: `/coins add @user 100`._

- /coins giveall <amount>
    Add coins to every account on the server. This subcommand is also available to the Manager role.

### Bot Owner Commands

These commands are only deployed in the administration server and verify the bot owner's identity.

- /giveorbs <all or user ID> <amount>
    Grant global Orbs to one user or every existing account.

- /broadcast <message> [title]
    Broadcast an announcement to every server using PronoBot.

- /certify add|remove|check <userid> and /certify list
    Manage and inspect global certifications.

- /setrank <userid> <rank> and /listrank
    Assign a global rank (`player`, `vip`, `champion`, `partner`, `staff`, `owner`) and list ranked users.

- /setpremium activate|deactivate|extend|check
    Activate, deactivate, extend, or inspect a server's Premium subscription by ID.

- /globalstats [period], /performance [action], /server getinfo <serverid>
    Inspect global statistics, performance metrics, and a server's information.

- /reload
    Reload bot commands after an update.

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

Six main categories:

1. **Level** — progression based on earned XP (unique to each server).
2. Wins — total number of won bets.
3. Win Rate — percentage of won bets (minimum 5 bets required).
4. Losses — total number of lost bets.
5. Profit Ratio — coins won / coins lost (minimum: at least 1 loss).
6. Balance — current number of coins owned.

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
2. Set roles via /pb config (adminrole, managerrole, restrictedrole).
3. Set channels via /pb config: announcements, bet-only channel, match announcement channel.
4. Set economic parameters: `initialcoins`, `dailyamount`, `minbet`, `maxbet`, and `dynamicreserve` for Sportsbook matches (default: 10,000).
5. (Optional) Enable match pings with `/pb config pingenabled true` and set the role with `/pb config pingrole <role>`.
6. Create a first match with /match create and test betting as a user.

Tip: start with small values (starting coins and daily reward) to test the system before increasing.

---

## Premium and Partnerships

The premium version takes your server to the next level — the bot will have unique features like **custom image generation** that replace Discord's classic embeds! Sportsbook matches always keep their image-free live embed so odds can refresh immediately.

To become an **official PronoBot partner** and get direct support from staff plus a **free Premium subscription**, join the [official Discord](https://discord.gg/VU3q8MKkDJ).

## Support & Help

- Use `/support` to send a help request or suggestion directly to the team.
- Join the official Discord server: https://discord.gg/VU3q8MKkDJ
- Quick FAQ:
    - "Bot doesn't respond" → check that the bot is online and has necessary permissions.
    - "I can't create matches" → verify you've configured admin and manager roles plus channels in /pb config
    - "You don't have an account" → use /pb open.
    - "Command disabled" → an administrator may have disabled games (/pb config commandesdejeux).

---

## Credits

Developed by Zyksa and Hokanosekai ❤️

Uses Node.js and a database (Supabase) to store accounts and statistics.

---

## Roadmap (Future Ideas)

- Leagues and divisions
- Combo bets
- Seasonal events
- Reward shop
- Daily quests and achievements
- Web dashboard and API for statistics

---

Thank you for using PronoBot! Transform your server into a friendly and competitive betting arena. 🎲🏆
