# Smart-device-project
Smart Agri-Sensor : Solution IoT pour l'Agriculture de Précision

Description
Le Smart Agri-Sensor est un dispositif intelligent conçu pour répondre aux défis du changement climatique et optimiser la gestion des ressources en eau dans le secteur agricole. Basé sur le microcontrôleur ESP32, ce capteur surveille en temps réel les conditions environnementales (humidité du sol, température et pression atmosphérique) pour aider les agriculteurs à prendre des décisions d'irrigation basées sur des données factuelles plutôt que sur des calendriers fixes.

Caractéristiques Principales

Surveillance Environnementale : Mesure de l'humidité du sol, de la température et de la pression barométrique.
Edge AI (Intelligence Embarquée) : Utilisation d'une logique de décision locale (Rule-Based Logic) pour classer le besoin d'irrigation en trois états : "Optimal", "Surveillance" ou "Critique".
Optimisation Énergétique : Gestion avancée de l'énergie via le mode Deep Sleep, permettant une autonomie théorique allant jusqu'à 40 jours sur batterie.
Connectivité IoT : Transmission des données et des alertes en temps réel via le protocole MQTT.
Dashboard de Monitoring : Interface utilisateur interactive développée sous Node-RED pour la visualisation des données et le contrôle à distance.
Historisation des Données : Possibilité d'exporter les mesures au format CSV pour des analyses agronomiques à long terme.

Architecture du Système
Matériel (Hardware) 

Microcontrôleur : ESP32 (WeMos board).
Capteur Température/Pression : Bosch BMP180.
Capteur d'Humidité : Water Sensor (analogique).

Logiciel (Software)

Langage : C++ (Arduino IDE/ESP32 framework).
Communication : Protocole MQTT (Broker EMQX).
Backend & Visualisation : Node-RED.


Installation et Utilisation
Configuration de l'ESP32 : Téléversez le code source sur votre carte en configurant vos identifiants Wi-Fi et l'adresse du broker MQTT.
Déploiement du Backend : Importez le flux (flow) Node-RED pour activer le serveur de collecte et le dashboard.
Surveillance : Accédez à l'interface web (Dashboard) pour suivre l'état de votre parcelle en temps réel.

Optimisation Énergétique
Pour maximiser la durée de vie de la batterie, le capteur suit un cycle de 15 minutes:
Réveil (Wake-up).
Acquisition des données et traitement IA local.
Envoi des données via MQTT (environ 12 secondes d'activité).
Retour immédiat en Deep Sleep.
