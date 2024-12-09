# Spring Microservices Project

## Objectif

Créer une application basée sur une architecture microservices permettant de gérer des factures contenant des produits et appartenant à un client.

---

![usecase](https://github.com/user-attachments/assets/a36c9ada-8f33-4190-ba34-64cf4077f190)

Ce diagramme illustre une architecture simple de microservices composée de deux services principaux : Customer Service et Inventory Service. Les services sont enregistrés dans le serveur Eureka et accédés via Spring Cloud Gateway. Les clients interagissent avec l'application via la Gateway.


![usecase2](https://github.com/user-attachments/assets/2922e898-ebb5-4e9d-9067-b27fcf1c94d1)

Ce diagramme ajoute un troisième service, Billing Service, à l'architecture initiale. Billing Service utilise OpenFeign pour communiquer avec Customer Service et Inventory Service. La Gateway Spring Cloud et Eureka Server gèrent le routage et l'enregistrement dynamique des services.


![usecase3](https://github.com/user-attachments/assets/f64841b2-89f1-4bf8-b0e7-f1c30371b1b8)

Ce diagramme final ajoute un Config Service pour la gestion centralisée des configurations de l'application. Tous les microservices (Customer, Inventory, Billing) ainsi que la Gateway récupèrent leurs configurations depuis ce service. L'architecture est maintenant complète, permettant une meilleure évolutivité et centralisation.


### Activité Pratique N°3 : Clients REST (RestTemplate et OpenFeign)

Le schéma ci-dessous, pris en classe, illustre deux modèles pour la communication entre services dans une architecture microservices :
1. **RestTemplate (Modèle Programmatique)** : Utilisé pour effectuer des requêtes HTTP de manière impérative.
2. **OpenFeign (Modèle Déclaratif)** : Permet de déclarer des clients REST en utilisant des interfaces Java annotées.

Ce schéma détaille les différences et les interactions entre ces deux modèles :

![tableau](https://github.com/user-attachments/assets/217741aa-7e42-4ab1-a6f0-a9069afc3f9e)

**Remarque** : Bien que ce schéma soit fait à la main, il reflète les concepts importants abordés pendant la session.



![EUreka](https://github.com/user-attachments/assets/775905e1-ba51-4004-a754-015788a8fe59)

Voici une capture d'écran de l'interface Eureka montrant les trois services enregistrés et fonctionnant avec succès (`Customer Service`, `Inventory Service`, `Billing Service`).


## Ressources

- **Partie Backend**: [Vidéo 1](https://www.youtube.com/watch?v=hVlEoKQG_2E)
- **Partie 2**: [Vidéo 2](https://www.youtube.com/watch?v=XEzBA3yIII8)
- **Service de Configuration**: [Vidéo 3](https://www.youtube.com/watch?v=-G2rcLMO1gQ)

---

## Étapes du Travail

1. **Customer Service**:
   - Créer un microservice pour gérer les clients.
   - Entité : `Customer`.
   - Repository : `CustomerRepository` (Spring Data).
   - Déployer et tester l'API REST avec Spring Data Rest.

2. **Inventory Service**:
   - Créer un microservice pour gérer les produits.
   - Entité : `Product`.
   - Repository : `ProductRepository` (Spring Data).
   - Déployer et tester l'API REST avec Spring Data Rest.

3. **Gateway**:
   - Implémenter Spring Cloud Gateway pour gérer le routage.
   - Configuration statique via `application.yml`.

4. **Service Eureka Discovery**:
   - Créer un service d'annuaire basé sur Netflix Eureka.
   - Permettre la découverte dynamique des services.

5. **Configuration Dynamique**:
   - Configurer la Gateway pour gérer dynamiquement les routes via Eureka.

6. **Billing Service**:
   - Créer un microservice pour gérer la facturation.
   - Utiliser **OpenFeign** pour la communication entre les services `Customer-Service` et `Inventory-Service`.

7. **Service de Configuration**:
   - Créer un service centralisé pour gérer la configuration de l'ensemble des microservices.

8. **Client Angular**:
   - Développer une interface Angular pour afficher les factures et interagir avec le backend.



---

## Diagramme

Le diagramme ci-dessous représente l'architecture cible du projet :

