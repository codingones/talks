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
        - Multiplication de cartographies loclales sans cohésion
        - Problème d'uniformisation de la donnée collectée
- Notre solution
    - La

    - Démo intégration d'une cartographie avec un jeu de données from scratch

    - Retex, expliquer pourquoi ça a marché, les effets de bord heureux

## Slides

---

- Les 3 slides les plus importants
    - 1er (Titre + sous-titre)
    - 2e (se présenter, annoncer l'angle (débutant, expert, etc.))
    - Dernier (Merci écrit en gros)
        - comme il va rester longtemps, il faut y mettre les informations importantes
- 1 slide = 1 minute (+- 20%)
- Slides autoportant
    - une idée par slide
    - on ne doit pas perdre le contexte
- Varier les templates pour briser la monotonie
- Répéter le message que l'on veut faire passer jusqu'à 3 fois en le reformulant

## Biographie

---

- Éviter le côté CV

## Speaker references

---

- Essayer de retrouver la captation Efrei Linux

## Abstract

Notre très petite équipe a réussi à repousser toujours plus loin la mise en place d'un backend pour notre produit.  
Cela nous a permi de gagner un temps très précieux en période de lancement, avec beaucoup d'éffets positifs dont certains auxquels nous ne nous attendions vraiment pas en faisant ce choix !

---

- Similaire à un synopis de film
- Doit suciter l'intérêt
- Ne dois pas tout dévoiler
- Expliquer le pourquoi (why)
- Clair et précis


## Talk References

Sujet présenté pour la première fois à l'édition décembre 2022 de l'unconf organsisée par HackYourJob (pas de captation).

#retour-expérience #open-source #open-data

---

- les détails pour l'orga
- plan détaillé
- repository
- slides
- Raconter de quoi on va parler (what)
- Mots clés
- Exprimer la valeur apportée
- Refs
    - meetup
    - bbl
    - captation
    - podcast

## Message aux organisateurs

Lors de la présentation du sujet en unconf, j'ai eu des retours très positif de la part d'un public composé de participants réguliers, de speakers et d'un organisateur de conférences tech.

Ces retours m'ont motivés à partager mon expérience à un plus large public. Ce qui m'a convaincu d'entreprendre cette démarche est que cela peut changer le regard des développeurs et des développeuses sur la façons d'apporter de la valeur au produit.

En effet bien souvent on se réduit à notre capacité à écrire du code avec certains langages / frameworks ou maîtrise de certaines technologie, alors qu'on a tout intérêt à se servir de notre approche systémique et notre esprit d'analyse pour proposer des solutions plus pertinentes qui ne nécessessitent pas forcément de passer par du code.

---

- Purquoi c'est important
- Ce que l'on va apporter aux participants
- La démarche
- Mettre à plat les arguments

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
