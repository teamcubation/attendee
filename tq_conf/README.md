# Pasos para configurar Attendee en Ubuntu 24.04

- git clone https://github.com/teamcubation/attendee.git
- copiar .env file (backup local)
- build.sh y start.sh
- configurar nginx (ver nginx_conf)
- configurar certbot
- configurar service daemon (ver attendee.service)

# Pasos para actualizar

- Actualizar repo https://github.com/teamcubation/attendee desde el main branch
- En el server:
  - `cd attendee`
  - `sudo systemctl stop attendee.service`
  - `git pull`
  - `./tq_conf/build.sh`
  - `sudo systemctl start attendee.service`
  - `sudo docker compose -f dev.docker-compose.yaml exec attendee-app-local python manage.py migrate`