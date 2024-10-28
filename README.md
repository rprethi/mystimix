# Mystimix

### Projet de VR par Audrey Dandurand, Camilia Bouatmani, Ihab Mouhajer et Prethiah Rajaratnam
---

Mystimix offre une expérience interactive et immersive plongeant les joueurs dans la peau d'un magicien qui doit élaborer des recettes de sorts en combinant divers ingrédients et en explorant les mystères de la magie.

## La proposition
---
Le magicien se rend dans son sanctuaire et commence à explorer la pièce. Un livre flottant et un chaudron sont posés sur un bureau situé au centre de la pièce. Une zone délimitée autour de la table permet de désactiver le flottement du livre. Simultanément, un menu apparaît dans le livre, contenant les différents ingrédients qu'il peut utiliser, lesquels produisent des résultats différents à chaque fois qu’une recette est terminée. Le magicien doit se déplacer dans la pièce pour cueillir les ingrédients nécessaires à la réalisation de la recette demandée. Un chronomètre évalue la performance du magicien, l'encourageant ainsi à compléter les trois recettes dans le temps le plus court possible.

## Moodboard visuel
---

![mystimix_planche_inspiration](https://github.com/user-attachments/assets/f96a9e97-0f13-4969-8248-adf8c21a666c)

## Moodboard sonore
---

<iframe width="560" height="415" src="https://www.youtube.com/embed/h1Dd3F5EBJY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<iframe width="560" height="415" src="https://www.youtube.com/embed/K3Q4F8sWBBY" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<iframe width="560" height="415" src="https://www.youtube.com/embed/f_5BxlzgkDo" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

<iframe width="560" height="415" src="https://www.youtube.com/embed/hKjD8whqeK0" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>


<iframe width="560" height="415" src="https://www.youtube.com/embed/Ppi5T6TxUSU" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

## L'environnement virtuel

## Schéma d'interactivité
```mermaid
graph TD;
    Début[Début du jeu]-->| Apparition dans le couloir |Menu[Menu avec les consignes apparait];
    Menu[Menu avec les consignes apparait]-->Chronomètre[Le chronomètre est démarré];
    Menu[Menu avec les consignes apparait]-->Lanternes[Les lanternes du couloir s’allument];
    Lanternes[Les lanternes du couloir s’allument]-->Déplacement[Déplacement du personnage];
    Chronomètre[Le chronomètre est démarré]-->Déplacement[Déplacement du personnage];
    Déplacement[Déplacement du personnage]-->|Audio|Bruit[Bruit de pas];
    Déplacement[Déplacement du personnage]-->Zone1[Rentre dans la zone 1];
    Déplacement[Déplacement du personnage]-->ExtérieurZone1[Reste en dehors de la zone 1];
    ExtérieurZone1[Reste en dehors de la zone 1]-->Déplacement[Déplacement du personnage];
    Bruit[Bruit de pas]-->Zone1[Rentre dans la zone 1 qui se trouve aux limites du tapis];
    Zone1[Rentre dans la zone 1 qui se trouve aux limites du tapis]-->DéplacementLivre[Déplacement vertical du livre];
    Zone1[Rentre dans la zone 1 qui se trouve aux limites du tapis]-->LumièreLivre[Un faisceau lumineux s'allume au dessus du livre];
    LumièreLivre[Un faisceau lumineux s'allume au dessus du livre]-->Zone2[Rentre dans la zone 2 qui se trouve autours de la table];
    DéplacementLivre[Déplacement vertical du livre]-->Zone2[Rentre dans la zone 2 qui se trouve autours de la table];
    Zone2[Rentre dans la zone 2 qui se trouve autours de la table]-->ArrêtDéplacementLivre[Arrêt du déplacement vertical du livre];
    Zone2[Rentre dans la zone 2 qui se trouve autours de la table]-->CouleurLumièreLivre[Le faisceau lumineux au dessus du livre change de couleur];
    Zone2[Rentre dans la zone 2 qui se trouve autours de la table]-->Recette[La recette apparait dans le livre];
    ArrêtDéplacementLivre[Arrêt du déplacement vertical du livre]-->DéplacementIngrédients[Déplacement du personnage pour prendre ingrédients];
    CouleurLumièreLivre[Le faisceau lumineux au dessus du livre change de couleur]-->DéplacementIngrédients[Déplacement du personnage pour prendre ingrédients];
    Recette[La recette apparait dans le livre]-->DéplacementIngrédients[Déplacement du personnage pour prendre ingrédients];
    DéplacementIngrédients[Déplacement du personnage pour prendre ingrédients]-->| Les ingrédients sont dans le panier. |IngrédientsChaudron[Les 3 ingrédients sont mis dans le chaudron];
    IngrédientsChaudron[Les 3 ingrédients sont mis dans le chaudron]-->| La cuillère tourne toute seule dans le chaudron. |MélangeIngrédients[Mélange des ingrédents et apparition du résultat];
    MélangeIngrédients[Mélange des ingrédents et apparition du résultat]-->| La 3e recette est terminée |ArrêtChronomètre[Le chronomètre s'arrête];
    MélangeIngrédients[Mélange des ingrédents et apparition du résultat]-->| La 3e recette n'est pas encore réalisée |Page[La page tourne];
    Page[La page tourne]-->Recette[La recette apparait dans le livre];
    ArrêtChronomètre[Le chronomètre s'arrête]-->Début[Début du jeu];
```
