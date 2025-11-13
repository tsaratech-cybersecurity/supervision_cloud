

Le but ici c'est de : Créer une application cloud média moderne pour la gestion de contenus liés aux trajets. Commençons par la base de données, puis l'interface utilisateur.
Maintenant,l'interface utilisateur avec la palette de couleurs demandée et une architecture modulaire.

les palettes de couleurs utilisées : #1E0F1C, #A7001E, #E2E9C0, #7AA95C, #955149

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

--
