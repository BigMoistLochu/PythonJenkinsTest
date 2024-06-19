FROM jenkins/jenkins:lts

USER root

# Zaktualizuj listę pakietów i zainstaluj narzędzia do kompilacji C++
RUN apt-get update && \
    apt-get install -y sudo python3 python3-venv python3-pip
USER jenkins

EXPOSE 8080
EXPOSE 50000

# CMD to run Jenkins
CMD ["jenkins.sh"]
