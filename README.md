# 🖥️ Tableau de bord de supervision d’infrastructure

Ce projet met en place un **tableau de bord complet** pour surveiller, automatiser et gérer une infrastructure multi-cloud (VMs, hyperviseurs, serveurs physiques).

---

## ⚙️ Fonctionnalités principales

- Supervision de **5 éléments d’infrastructure** (CPU, mémoire, disque, réseau)  
- Visualisation des **métriques en temps réel** et **historiques**  
- **Alertes automatiques** sur incidents ou dépassement de seuils  
- **Actualisation automatique toutes les 30 secondes**  
- **Conditionnement direct des fonctionnalités du PC / serveur** 🖥️  

---

## Automatisation intégrée

Le tableau de bord permet désormais d’**agir directement** sur les systèmes surveillés :

- Démarrage / arrêt / redémarrage de services  
- Exécution de **scripts automatisés** selon les alertes  
- Ajustement dynamique des ressources (CPU, RAM, réseau)  
- Mise en veille, redémarrage ou arrêt distant  
- Nettoyage automatique (caches, logs, disques)  

---

## Architecture technique

- **Frontend :** React / Vue.js (interface de supervision)  
- **Backend API :** Node.js / FastAPI  
- **Base de données :** PostgreSQL / InfluxDB  
- **Agents locaux :** services installés sur chaque machine pour exécuter les actions  
- **Sécurité :** chiffrement TLS, authentification JWT, journalisation complète des actions  

### Composants utile au fonctionnement de cette application

| Composant | Rôle |
|------------|------|
| **Frontend (Dashboard Web)** | Interface utilisateur affichant les métriques et actions |
| **Backend API** | Gère la logique, les alertes et la communication avec les agents |
| **Base de données** | Stocke les métriques, alertes et journaux d’actions |
| **Agent local** | Collecte les métriques et exécute les commandes sur le poste surveillé |
| **Message Broker (optionnel)** | Synchronisation des ordres d’action (RabbitMQ, Kafka, MQTT) |

---

## Suivre l'Installation & Lancement rapide

### 1.  Prérequis
Assure-toi d’avoir installé :
- **Docker & Docker Compose**  
- **Git**  
- (Optionnel) **Python 3.10+** ou **Node.js 18+**

---

### 2. cloner le dépôt
```bash
git clone https://github.com/<ton-utilisateur>/<ton-repo>.git
cd <ton-repo>



3. ⚙️ Configurer les variables d’environnement

Crée un fichier .env à la racine du projet :

DB_HOST=db
DB_USER=admin
DB_PASSWORD=admin123
DB_NAME=infrastructure_monitoring

API_PORT=8080
REFRESH_INTERVAL=30

AGENT_AUTH_TOKEN=changeme_secure_token

Lancer l’infrastructure avec Docker
docker-compose up -d


Cela démarre :

Le backend API

La base de données

Le frontend (tableau de bord web)

Les agents simulés avec des métriques d’exemple


Accéder au tableau de bord

👉 http://localhost:8080

Vous y trouverez :

Les 5 machines surveillées

Les métriques en temps réel

Les alertes actives

Les actions automatiques configurées



/-*  Installe un agent local sur une machine distante :

curl -s https://raw.githubusercontent.com/<ton-utilisateur>/<ton-repo>/main/agent/install.sh | bash


Puis configure-le avec ton token d’authentification défini dans .env.

Lancer les commandes suivantes: 
docker-compose logs -f	Suivre les logs en direct
docker-compose down	Arrêter tous les services
docker-compose restart	Redémarrer le système
docker exec -it api /bin/bash	Accéder au conteneur backend
