# pki_apache2_certificates

## Objectif
Mettre en œuvre une solution PKI complète comprenant :

Une autorité de certification racine (root CA)
Une autorité de certification intermédiaire (intermediate CA)
Un certificat serveur signé par l’intermédiaire
L’activation du protocole HTTPS sur un serveur web (Apache ou Nginx)
La documentation et la présentation des certificats

## Étapes réalisées

1. Création de la CA racine (Root CA)
   Génération d’une paire de clés (privée/publique)
   Création d’un certificat autosigné pour la root CA
   
2. Création de la CA intermédiaire
   Génération d’une paire de clés pour l’intermédiaire
   Création d’une demande de signature de certificat (CSR) pour l’intermédiaire
   Signature de la CSR de l’intermédiaire par la root CA pour obtenir un certificat intermédiaire
   
3. Création du certificat serveur
   Génération d’une paire de clés pour le serveur web
   Création d’une CSR pour le serveur
   Signature de la CSR du serveur par la CA intermédiaire
   
5. Chaîne de certification
   Génération du fichier de chaîne de certificats (server-chain.pem) contenant :
   certificat serveur + certificat intermédiaire + certificat root
   
6. Installation sur le serveur web
   Copie de la clé privée et des certificats dans /etc/ssl/private et /etc/ssl/certs
   Configuration d’un VirtualHost HTTPS sur le port 443 dans Apache (ou Nginx)
   Activation du module SSL et du site sécurisé
   
7. Vérification
Accès au site via HTTPS
Présentation de la chaîne de certification dans le navigateur
Vérification que le certificat serveur est bien signé par l’intermédiaire
