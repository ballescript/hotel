# Setup du serveur

3 containers:

*   container web (serveur) : Nginx -> uWSGI -> Django, managés par Supervisord
*   container db : postgres
*   container adminer : adminer pour la gestion graphique de postgres

### Build / run

Build la stack, site accessible sur le port 8000 (cf docker-compose.yml)

*   chdir dans ce dossier et
*   `docker-compose up`
*   Puis se connected à l'admin de la base de données adminer sur localhost:8080 avec les identifiants suivants :
    *   System: PostgreSQL
    *   Server: db
    *   Username: postgres
    *   Password: example
    *   Database: (vide)
*   Créer une base de données "django"
*   `docker-compose run bash` et dans le terminal
*   `python3 manage.py collectstatic && python3 manage.py makemigrations && python3 manage.py migrate`
