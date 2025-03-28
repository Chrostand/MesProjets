FROM ubuntu:20.04

# Crée les répertoires nécessaires
RUN mkdir -p /opt/gochassis && \
    mkdir -p /opt/gochassis/conf

# Copie les fichiers de configuration
COPY ./conf/microservice.yaml /opt/gochassis/conf
COPY ./conf/chassis.yaml /opt/gochassis/conf

# Copie le fichier exécutable
COPY ./Catalog /opt/gochassis

# Assure que le fichier est exécutable
RUN chmod +x /opt/gochassis/Catalog

# Définir les variables d'environnement
ENV CHASSIS_HOME=/opt/gochassis/

# Définir le répertoire de travail
WORKDIR $CHASSIS_HOME

# Exposer le port
EXPOSE 8089

# Commande par défaut
CMD ["/opt/gochassis/Catalog"]

