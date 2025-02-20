# Installation de WordPress avec Docker Desktop (Mac)

**Guide simple pour déployer WordPress en utilisant Docker Desktop sur Mac.**

## Prérequis

- Docker Desktop pour Mac (téléchargeable sur [Docker Hub](https://www.docker.com/products/docker-desktop))

## Installation en 4 étapes

### 1. Installer Docker Desktop

1. Téléchargez et installez Docker Desktop depuis le [site officiel](https://www.docker.com/products/docker-desktop).
2. Lancez Docker Desktop.
3. Attendez que l'icône Docker dans la barre de menu indique "Docker Desktop is running".

### 2. Préparer le projet

1. Créez un nouveau dossier pour votre projet.
2. Ouvrez Terminal et naviguez vers votre dossier :

   ```sh
   cd le/repertoire/du/projet
   ```

3. Copiez le fichier d'exemple `.env.example` :

   ```sh
   cp .env.example .env
   ```

4. Ouvrez `.env` et modifiez les mots de passe.

### 3. Lancement

1. Démarrez les conteneurs :

   ```sh
   docker-compose up -d
   ```

### 4. Accès aux services

- WordPress : [http://localhost:8000](http://localhost:8000)
- PHPMyAdmin : [http://localhost:8080](http://localhost:8080)

**Login :** `wordpress`  
**Password :** celui que vous avez défini dans `.env`

## Commandes utiles

- **Arrêter les conteneurs :**

    ```sh
    docker-compose down
    ```

- **Voir les conteneurs en cours :** Interface Docker Desktop ou

    ```sh
    docker ps
    ```

- **Redémarrer :** Utilisez l'interface Docker Desktop ou

    ```sh
    docker-compose restart
    ```

## Résolution de problèmes courants

- Si les ports sont déjà utilisés, modifiez `WORDPRESS_PORT` et `PHPMYADMIN_PORT` dans `.env`.
- En cas d'erreur, vérifiez que Docker Desktop est bien démarré.

## Note

Les données de votre site sont automatiquement sauvegardées dans le dossier `wordpress` et la base de données persiste même après l'arrêt des conteneurs.
