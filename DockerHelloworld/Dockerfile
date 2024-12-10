# Utiliser Debian comme image de base
FROM debian:latest

# Mettre à jour l'index des paquets et installer curl
RUN apt-get update && apt-get install -y curl

# Exécuter le script hello-world
RUN curl -fsSL https://get.docker.com/ | sh

# Afficher un message de bienvenue pour tester l'installation
CMD echo "Hello from Docker, from a custom Debian-based image!"
