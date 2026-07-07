# Automatisation d'une tête d'usinage — Simulation CODESYS

Projet réalisé dans le cadre du cours de Logique Programmée à l'EPHEC.
Simulation complète en CODESYS (V3.5 SP21) d'un système multimode : automatique, manuel, arrêt, arrêt d'urgence.

## Le système

Une tête d'usinage perce une pièce serrée par un vérin pneumatique. Trois capteurs (S1, S2, S3) repèrent la position verticale de la tête.

Cycle automatique :
1. Serrage de la pièce (vérin V)
2. Démarrage du foret (moteur B)
3. Descente grande vitesse jusqu'à S2
4. Descente petite vitesse jusqu'à S3
5. Perçage : 5 secondes d'arrêt en position basse
6. Remontée grande vitesse jusqu'à S1
7. Arrêt moteur B, relâchement du vérin

Le sélecteur A-0-M donne accès aux 4 modes (auto / arrêt / manuel / urgence), gérés via un GEMMA et une hiérarchie de GRAFCETs (niveau 1 système → niveau 2 matériel → niveau 3 programme PLC).

## Matériel visé

- PLC : Siemens S7-1200 (CPU 1214C DC/DC/DC)
- HMI : Siemens KTP700
- 2 moteurs DC (foret + déplacement vertical), vérin pneumatique double effet
- Capteurs de position S1/S2/S3, bouton AU, switch A-0-M

## Logiciel

- CODESYS V3.5 SP21 (simulation, sans matériel physique)
- Programme principal en SFC hiérarchique, actions en ST et FBD
- Interface de visualisation développée pour simuler le pupitre opérateur et le process

## Contenu du dossier

- `projet-codesys/` : projet CODESYS à ouvrir
- `schemas-electriques/` : schémas de puissance et de commande
- `grafcet/` : GRAFCETs niveaux 1, 2 et 3
- `rapport/` : rapport complet (conception, câblage, programme, tests de validation)
