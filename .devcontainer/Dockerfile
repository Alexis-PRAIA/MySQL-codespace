# Utilisez l'image de base Codespaces pour PHP
FROM mcr.microsoft.com/vscode/devcontainers/php:0-7

# Installez le client MySQL
RUN apt-get update && apt-get install -y mysql-client

# [Optional] Définissez d'autres configurations personnalisées si nécessaire
# ...

# [Optional] Définissez un utilisateur non-root pour l'exécution des commandes
USER vscode

# [Optional] Définissez le répertoire de travail dans lequel l'environnement de développement démarrera
WORKDIR /workspace

# [Optional] Commande par défaut pour démarrer l'environnement de développement
CMD ["sleep", "infinity"]
