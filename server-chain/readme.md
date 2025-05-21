# Description

Le fichier `server-chain.pem` contient les trois certificat (serveur, intermédiaire et root).

Ce fichier est fourni dans la configuration apache, il est nécessaire pour apache pour s'assurer de l'intégrité 
de la provenance de chaque certificat.
<br>

Soit la chaine : **`rootCA -> intermediateCA -> serverCA`**
