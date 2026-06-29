# 📊 Stack de Monitoring Complète avec Docker

Ce projet met en place une infrastructure de monitoring robuste et conteneurisée pour surveiller l'état de santé du système hôte et des conteneurs Docker en temps réel.

## 🚀 Architecture de la Stack

La stack s'appuie sur les technologies suivantes :
*   **Prometheus** : Base de données orientée séries temporelles pour collecter et stocker les métriques.
*   **Grafana** : Plateforme de visualisation pour créer des tableaux de bord dynamiques.
*   **Node Exporter** : Collecteur de métriques pour le système hôte Linux (CPU, mémoire, disque, réseau).
*   **cAdvisor** : Collecteur de métriques spécifiques aux conteneurs Docker (utilisation des ressources par conteneur).
*   **Alertmanager** : Gestionnaire d'alertes pour centraliser et router les notifications (Slack, Email, Discord...).

---

## 🛠️ Configuration Prometheus & Alertes

Le système est configuré avec un intervalle de collecte agressif de **5 secondes** (`scrape_interval: 5s`) et intègre des règles d'alertes automatiques.

### Alerte configurée (`alerts.yml`) :
*   **HighCPUUsage** : Déclenchée si l'utilisation moyenne du CPU dépasse **80%** pendant plus de **1 minute** (Sévérité : `critical`).

---

## 🏃 Demarrage Rapide

### Prérequis
*   Docker installé
*   Docker Compose installé

### Lancement de la Stack
Pour démarrer l'ensemble des services en arrière-plan, exécutez :

```bash
docker compose up -d



📁 Structure du Projet

├── alerts.yml          # Définition des règles d'alertes Prometheus
├── prometheus.yml      # Configuration globale et cibles de scraping
├── docker-compose.yml  # Définition des conteneurs de la stack
└── README.md           # Documentation du projet