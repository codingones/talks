# Préparation Talk - Retex construction de l'API pour la cartographie nationale des lieux de médiation numérique

## Table des matières

- 🪧 [Titre](#titre)
- ⏱️ [Format](#format)
- 👥 [À qui ça s'adresse](#à-qui-ça-sadresse)
- 🚀 [Call to action](#call-to-action)
- 📝 [PROEP](#proep)
- 🗺️ [Plan détaillé](#plan-détaillé)
- 🎬 [Slides](#slides)
- 🎀 [Abstract](#abstract)
- 🎙️ [Talk References](#talk-references)
- ✉️ [Message aux organisateurs](#message-aux-organisateurs)
- 🫖 [Biography](#biography)
- 💬 [Speaker references](#speaker-references)
- 🌐 [Sources](#sources)

## Titre

Comment on n'a (toujours) pas codé de back-end après 9 mois en production

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
    - notre progression et les choix que nous avons eu à faire
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
  - Notre solution
  - Nos contraintes
- Les étapes de la construction
    - Mise en ligne initiale => Fork du produit Res'in + fichier JSON comme source de données
    - Parcours d'orientation => développement filtres côté front
    - Référencer un lieu sur la cartographie => Collaboration DORA
      - Problème : formulaire trop complexe
      - Solution : contribution open source
      - Effets positifs supplémentaires
    - Référencer des lieux en masse => Collaboration Mednum / Datactivist
      - Problème : définir un schéma de données co-construit avec les acteurs existants
      - Solution : intégration comité de pilotage de la définition du schéma
      - Effets positifs supplémentaires
    - Fusionner de multiples sources de données => Collaboration avec data.inclusion
      - Problème : API non compatible avec la cartographie
      - Solution : développement de scripts de conversion entre nos schémas respectifs
      - Effets positifs supplémentaires
    - Récupérer les données pour l’affichage dans la cartographie => data.gouv
      - Effet positif supplémentaire
- Les limites
- Démo de l'intégration avec une source de données personnalisée

## Slides

[Comment on n'a (toujours) pas codé de backend après 9 mois en production](https://hackmd.io/@marc-gavanier/SyRTWj2uo#/)

---

- Les 3 slides les plus importants
    - 1er (Titre + sous-titre)
    - 2e (se présenter, annoncer l'angle (débutant, expert, etc.))
    - Dernier (Merci écrit en gros)
        - comme il va rester longtemps, il faut y mettre les informations importantes
- 1 slide = 1 minute (+- 20%)
- Slides autoportantes
    - une idée par slide
    - on ne doit pas perdre le contexte
- Varier les templates pour briser la monotonie
- Répéter le message que l'on veut faire passer jusqu'à 3 fois en le reformulant

## Abstract

Lors de ce retour d'expérience, vous verrez comment notre petite équipe de développement a réussi à maximiser la valeur produite en ne codant pas.

Vous découvrirez au travers d'exemples concrets pourquoi cela nous a permis de gagner un temps très précieux en période de lancement, ainsi que les nombreux effets positifs auxquels nous ne nous attendions vraiment pas en faisant ce choix !

---

- Similaire à un synopsis de film
- Doit susciter l'intérêt
- Ne dois pas tout dévoiler
- Expliquer le pourquoi (why)
- Clair et précis

## Talk References

#retour-expérience #open-source #open-data

Sujet présenté pour la première fois à l'édition décembre 2022 de l'unconf organisée par HackYourJob (pas de captation).

\## 🗺️ Plan détaillé

- Présentation du contexte
    - L'équipe
    - Quelques mots au sujet de la médiation numérique
    - Notre solution
    - Nos contraintes
- Les étapes de la construction
    - Mise en ligne initiale => Fork du produit Res'in + fichier JSON comme source de données
    - Parcours d'orientation => développement filtres côté front
    - Référencer un lieu sur la cartographie => Collaboration DORA
        - Problème : formulaire trop complexe
        - Solution : contribution open source
        - Effets positifs supplémentaires
    - Référencer des lieux en masse => Collaboration Mednum / Datactivist
        - Problème : définir un schéma de données co-construit avec les acteurs existants
        - Solution : intégration comité de pilotage de la définition du schéma
        - Effets positifs supplémentaires
    - Fusionner de multiples sources de données => Collaboration avec data.inclusion
        - Problème : API non compatible avec la cartographie
        - Solution : développement de scripts de conversion entre nos schémas respectifs
        - Effets positifs supplémentaires
    - Récupérer les données pour l’affichage dans la cartographie => data.gouv
        - Effet positif supplémentaire
- Les limites
- Démo de l'intégration avec une source de données personnalisée

\## 🎬 Slides

Travail en cours, mais l'essentiel est posé

[Comment on n'a (toujours) pas codé de back-end après 9 mois en production](https://hackmd.io/@marc-gavanier/SyRTWj2uo#/)

---

- Les détails pour l'orga
- Plan détaillé
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

\## 🌱 Origine

À l'issue de la présentation du sujet à l'unconf HackYourJOb, j'ai eu des retours très positifs de la part d'un public composé de participants réguliers, de speakers, et d'un organisateur de conférences tech.
Ces retours m'ont motivé à partager mon expérience à un plus large public.  
Ce qui m'a convaincu d'entreprendre cette démarche est que cela peut changer le regard des développeurs et des développeuses sur l'impact qu'ils ou elles peuvent avoir sur le produit.

\## 🤔 Pourquoi moi ?

Lead développeur sur la start-up d'état "cartographie nationale des lieux de médiation numérique", je suis à l'origine de la stratégie qui consiste à privilégier des collaborations entre produits, des solutions open source ou des publications en open data, plutôt que de passer systématiquement par la case développement.

\## 🎯 Objectif

On se réduit bien souvent à notre capacité à écrire du code avec certains langages / frameworks ou maîtrise de certaines technologies, alors qu'on a tout intérêt à se servir de notre approche systémique et notre esprit d'analyse pour proposer des solutions plus originales et plus efficaces que ce dont nous avons l'habitude.

Avec ce retour d'expérience, je voudrais toucher les développeurs et des développeuses qui ont du mal à imaginer comment apporter de la valeur autrement que par le code. En effet, produire et maintenir du code n'est pas l'unique moyen à disposition, mais certainement le plus lent et le plus coûteux.

Je voudrais qu'en sortant de la salle les développeurs et les développeuses envisagent des solutions alternatives à l'écriture de code pour mettre en place des systèmes dans les produits sur lesquels ils ou elles contribuent.

---

- Purquoi c'est important
- Ce que l'on va apporter aux participants
- La démarche
- Mettre à plat les arguments

## Biography

Ingénieur logiciel indépendant, je suis passionné par le développement, mais ce que j'aime encore plus c'est apporter un maximum de valeur aux utilisateurs des produits sur lesquels j'interviens.
Je m'intéresse donc à tous les sujets qui favorisent la fluidité du développement et la collaboration tels que l'agilité, TDD, BDD, DDD, DevOps

En ce moment, je suis en mission chez beta.gouv où j'aide 13 millions de Français éloignés du numérique à devenir indépendant sur le sujet.  
Pour y parvenir, je contribue sur la [Cartographie nationale des lieux de médiation numérique](https://cartographie.societenumerique.gouv.fr) qui rend visible l'offre d'accompagnement disponible en France auprès des travailleurs sociaux qui sont les principaux prescripteurs des services de médiation numérique.

---

- Éviter le côté CV

## Speaker references

Quelques présentations que j'ai faites pour l'association étudiante Efrei Linux et mes collègues à beta.gouv:
- [Du test logiciel au TDD](https://hackmd.io/@codingones/ByCYIe9ms#/)
- [Fonctions & inversion de dépendance](https://hackmd.io/@codingones/BJbtIKGdY#/)

## Sources

### Sujet

- [Cartographie Nationale des lieux de médiation numérique](https://cartographie.societenumerique.gouv.fr)
- [DORA](https://dora.fabrique.social.gouv.fr/)
- [Schéma de données des lieux de médiation numérique](https://lamednum.coop/schema-de-donnees-des-lieux-de-mediation-numerique-2/)
- [Data.inclusion](https://www.data.inclusion.beta.gouv.fr)
- [schema.data.gouv.fr](https://schema.data.gouv.fr/LaMednum/standard-mediation-num/latest.html)
- [data.gouv.fr](https://www.data.gouv.fr/fr/organizations/cartographie-nationale-des-lieux-de-mediation-numerique/)

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
- [Les secrets de la sélection des talks chez Devoxx France par Nicolas Martignole](https://www.youtube.com/watch?v=zQUVCmAf9DI)
- [Slides: Do's and Don'ts](https://www.youtube.com/watch?v=onfaLYecMlQ)
- [L'art du Story Telling par Cyrille Dupuydauby](https://www.youtube.com/watch?v=aNfYcXTpV1c)
- [Réussir sa candidature aux conférences](https://www.youtube.com/watch?v=sirHZcpSkqs)
- [Donner sa première conférence, de l'idée à la réalisation par Estelle Landry](https://www.youtube.com/watch?v=15LSass6j9A)
