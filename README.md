# 🔐 Sécurisation IoT d’un Datacenter

> Projet académique réalisé dans le cadre de la **SAÉ 4.IOM.01 – Implémenter les réseaux et protocoles sans fil dédiés à l’IoT**  
> BUT Réseaux & Télécommunications – Parcours IoM  

---

## 🚀 Objectif
Concevoir un **système de sécurisation IoT pour datacenter** intégrant :  
- 📡 Supervision en temps réel (température, fumée, mouvement, choc)  
- 🛂 Contrôle d’accès par **RFID avec protection anti-clonage**  
- 🔄 Haute disponibilité via **VRRP**  
- 📊 Supervision centralisée avec **Node-RED, InfluxDB et Grafana**  

---

## 🏗️ Architecture
- **ESP8266** → connecte les capteurs et envoie les données via MQTT  
- **Raspberry Pi** → héberge les services :  
  - 📨 **Broker MQTT**  
  - ⚙️ **Node-RED** (traitement des événements & automatisation)  
  - 🗄️ **InfluxDB** (base de données temporelle)  
  - 📊 **Grafana** (tableaux de bord)  
  - 🗃️ **MySQL** (gestion RFID et logs)  
- **Redondance** → deux Raspberry Pi avec **VRRP**  

---

## 🔧 Technologies utilisées
![MQTT](https://img.shields.io/badge/MQTT-Protocol-blueviolet?logo=eclipsemosquitto&logoColor=white)
![Node-RED](https://img.shields.io/badge/Node--RED-Flow--based-red?logo=nodered&logoColor=white)
![InfluxDB](https://img.shields.io/badge/InfluxDB-TimeSeries-blue?logo=influxdb&logoColor=white)
![Grafana](https://img.shields.io/badge/Grafana-Monitoring-orange?logo=grafana&logoColor=white)
![MySQL](https://img.shields.io/badge/MySQL-Database-4479A1?logo=mysql&logoColor=white)
![ESP8266](https://img.shields.io/badge/ESP8266-IoT-lightgrey?logo=espressif&logoColor=white)
![Raspberry Pi](https://img.shields.io/badge/RaspberryPi-Server-C51A4A?logo=raspberrypi&logoColor=white)

---

## 📡 Capteurs intégrés
- 🛂 **RFID PN532** – authentification + protection anti-clonage  
- 💥 **Capteur de choc** – détection d’ouverture/impact  
- 🌫️ **MQ135** – détection de fumée (PPM)  
- 👀 **HC-SR501** – détection de mouvement PIR  
- 🌡️ **DHT22** – température & humidité  

---

## 📊 Supervision & Visualisation
- **Node-RED** : traitement des événements, alertes (e-mail, WhatsApp, LEDs)  
- **InfluxDB** : stockage historique des mesures  
- **Grafana** : tableaux de bord interactifs  

---

## 🔒 Sécurité mise en place
✔️ Authentification + ACL sur le broker MQTT  
✔️ Tokens d’accès restreints pour Grafana, Node-RED & InfluxDB  
✔️ Requêtes SQL sécurisées contre l’injection  
✔️ Redondance VRRP (basculement ~50ms)  

---

## 📂 Structure du dépôt
