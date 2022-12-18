---
tags: Presentations
---

# Préparation Talk - Retex construction de l'API pour la cartographie nationale des lieux de médiation numérique

## Titre

Comment on a (toujours) pas codé de back-end après 9 mois en production

## Format

Quicky (environ 15-20 minutes)


## À qui ça s'adresse

Les développeurs et des développeuses qui ont du mal à imaginer comment apporter de la valeur autrement que par la production de code

## Call to action

Produire et maintenir du code n'est pas l'unique moyen de créer de la valeur pour un développeur ou une développeuse, mais probablement l'un des moyens les plus lents et les plus coûteux parmi la panoplie à sa disposition.

Je voudrais qu'en sortant de la salle les développeurs et les développeuses envisagent des solutions alternatives à la production de code pour mettre en place des systèmes.

## PROEP

- Purpose : On a essayé de ne pas coder de back-end depuis plusieurs mois et ça marche bien, avec des effets positifs que nous n'avions pas anticipés
- Rationale : Explication de
    - notre progression et les choix sue nous avons eu à faire
    - comment on a réussi à repousser l'implémentation d'un backend le plus loin possible
    - les effets positifs ciblés initialement étaient au rendez-vous
        - Gain de temps
        - Génération plus rapide de valeur
        - Feedback utilisateur
        - Intégration facile de l'outil hors de son contexte initiale
    - les effets positifs inattendus
        - On profite de la force des produits sur lesquels on s'appuie
            - Équipe de chargés de déploiement
            - Fonctionnalités de rappel par email pour la mise à jour des données
            - Nombreux tests utilisateurs
        - Apport d'un flux d'utilisateurs sur un produit partenaire
        - Contribution open source sur un produit partenaire (sur un sujet prévu dans leur roadmap)
        - Open data by design
- Objections :
    - cela pose des problèmes lorsqu'il y a beaucoup de données
    - nous ne savons pas si nous avons eu la chance de rencontrer des partenaires ouverts ou si c'est repliable
    - nous déléguons une partie de la maîtrise du produit à d'autres acteurs
    - il faut veiller à faire une architecture découplée pour pouvoir changer plus tard
    - ce n'est pas magique, il y a quand même un peu de code à produire, mais il est très réduit et ne prend pas la forme classique que l'on entend lorsque l'on parle de back-end
- Exemples :
    - Saisir de la donnée unitairement
        - Nous avons identifié l'outil DORA qui permet aux acteurs de l'inclusion de référencer leur offre de service
        - Le fonctionnement open source nous a permis d'apporter des contributions pour satisfaire des contraintes liées à notre produit qui n'était pas dans les priorités immédiates de l'équipe de DORA
    - Saisir de la donnée en masse
        - Nous avons activement participé à la co-constuction du schéma de données des lieux de médiation numérique en intégrant le comité de pilotage
        - Une fois ce schéma en ligne, une intégration avec l'outil publier.etatlab.studio nous offre un outil complet de saisie, de validation et de publication de données
    - Dédoublonner des lieux venant de plusieurs sources de données
        - Nous collectons et transformons les jeux de données existants
        - Nous les partageons à l'API data inclusion qui se charge d'agréger de multiples sources de données dont DORA fait également partie, de produire un identifiant unique et de mettre à disposition le résultat
    - Récupérer la donnée pour l'affichage dans la cartographie
        - La mise en ligne en open data d'un fichier sur data.gouv créé une URL stable, s'il s'agit d'un fichier JSON l'URL peut être utilisé dans le front de la cartographie de la même manière qu'un endpoint d'API
- Purpose : Aujourd'hui nous réfléchissons à produire notre propre API, mais c'est pour résoudre des cas à la marge, car notre produit fonctionne parfaitement dans la plupart des cas en l'état. La totalité des acteurs avec qui nous avons interagi ont accueilli très positivement nos contributions et ont salué la valeur que nous leur avons apportée alors même que ces cela nous a fait gagner du temps sur notre propre roadmap.

## Plan détaillé

- Présentation du contexte
    - L'équipe
    - Quelques mots au sujet de la médiation numérique
    - Ce que nous cherchons à résoudre
        - Multiplication de cartographies locales sans cohésion
        - Problème d'uniformisation de la donnée collectée
- Notre solution
    - Une cartographie des lieux de médiation numérique facile à intégrer en marque blanche
- Nos contraintes
  - Petite équipe
  - Impact rapide
- Les étapes de la construction
    - Mise en ligne initiale => Fork du produit Res'in + fichier JSON comme source de données
    - Parcours d'orientation => développement filtres côté front
    - Référencer un lieu sur la cartographie => Collaboration DORA
      - Problème : formulaire trop complexe
      - Solution : contribution open source
      - Effets positifs supplémentaires :
        - On avance la roadmap de DORA
        - Expérience produit de DORA
        - Business development de DORA nous profite également
        - Fonctionnalités de DORA
    - Référencer des lieux en masse => Collaboration Mednum / Datactivist
      - Problème : définir un schéma de données co-construit avec les acteurs existants
      - Solution : intégration comité de pilotage de la définition du schéma
      - Effets positifs supplémentaires
        - Mise en avant comme produit pilote du schéma
        - Participation active à l'élaboration du schéma
        - Une fois en place, le schéma donne accès à tous les outils publier.etalab.studio pour la validation et la publication des données sur data.gouv
    - Fusionner de multiples sources de données => Collaboration avec data.inclusion
      - Problème : API non compatible avec la cartographie
      - Solution : développement de scripts de conversion entre nos schémas respectifs
      - Effets positifs supplémentaires
        - Nous sommes l'une des sources de données importantes de data.inclusion
        - Nous profitons des améliorations sur la qualité des données de data.inclusion
        - Les données sont dédoublonnées par data.inclusion
    - Récupérer les données pour l’affichage dans la cartographie => data.gouv
      - Effets positifs supplémentaires
        - Toutes les données que nous gérons sont disponibles en open data par construction
- Les limites du système
  - Problèmes de perfs lorsqu'il y a beaucoup de données
  - Nous avons peut-être eu de la chance avec nos partenaires qui sont vraiment tous super
  - Nous déléguons une partie de la maîtrise du produit
  - Il faut veiller à avoir une bonne architecture pour pouvoir changer d'avis plus tard
  - Ce n’est pas magique, il y a quand même un peu de code à produire
- Démo de la facilité d'intégration de la cartographie dans une page HTML avec une source de données custom

## Sources

### Sujet

### Outils

- conference hall
- papercall
- cfp.io
- BBL

### Préparation

- [S2E08 : Comment sont choisis les sujets des conférences tech? Avec Estelle Landry](https://www.youtube.com/watch?v=BIrYQE13CGs)
    - [Developers Conferences Agenda/List](https://github.com/scraly/developers-conferences-agenda/)
- [S2E13 : Petit guide des confs tech](https://www.youtube.com/watch?v=QbjccJNB9oc)
    - [Agenda conferences](https://github.com/scraly/developers-conferences-agenda/)
    - [Comment bien préparer sa participation à Devoxx France ?](https://www.devoxx.fr/2022/03/14/comment-bien-preparer-sa-participation-a-devoxx-france/)
- [Osez Devenir Speaker ! (Estelle Landry et Julien Topçu)](https://www.youtube.com/watch?v=278MbzdJ_Gg)
    - 29:34 exemple d'abstract et de références
- [Les secrets de la sélection des talks chez Devoxx France par Nicolas Martignole](https://www.youtube.com/watch?v=zQUVCmAf9DI)
- [Slides: Do's and Don'ts](https://www.youtube.com/watch?v=onfaLYecMlQ)
- [L'art du Story Telling par Cyrille Dupuydauby](https://www.youtube.com/watch?v=aNfYcXTpV1c)
- [Réussir sa candidature aux conférences](https://www.youtube.com/watch?v=sirHZcpSkqs)
    - 40:47 exemple d'abstract et de références "d'un talk qui a bien marché"
- [Donner sa première conférence, de l'idée à la réalisation par Estelle Landry](https://www.youtube.com/watch?v=15LSass6j9A)
    - 34:25 exemple de biographie
    - 36:15 exemple d'abstract et de références
