# Utiliser l'image de base Debian
FROM debian:latest

# Mettre à jour l'index des paquets et installer les paquets nécessaires (openssh-server)
RUN apt-get update && apt-get install -y \
    openssh-server \
    && mkdir /var/run/sshd

# Créer un utilisateur root avec un mot de passe
RUN echo 'root:root123' | chpasswd

# Modifier la configuration de SSH pour accepter les connexions sans clé
RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config \
    && sed -i 's/#PasswordAuthentication yes/PasswordAuthentication yes/' /etc/ssh/sshd_config

# Exposer le port SSH (ici, nous utilisons le port 2222 au lieu du port 22)
EXPOSE 2222

# Lancer le serveur SSH en mode premier plan
CMD ["/usr/sbin/sshd", "-D"]
