4. Objectif : Un Hello World d’une image nginx en utilisant un container détaché à durée de vie longue

* Ecrire un fichier hello.html avec comme contenu « <h1>Hello, World!</h1> »
* Créer un fichier Dockerfile 
        - héritant de l’image de base « nginx:latest »,
        - y copier le fichier « hello.html » dans le répertoire /usr/share/nginx/html/
* Construire cette image
* Démarrer un nouveau container depuis cette image, en utilisant l’option « détaché » et en utilisant l’option de publication de port.

/Desktop/workspace/Docker/exo4$ docker build -t hello-html .

/Desktop/workspace/Docker/exo4$ docker run -p "8080:80" -d hello-html

docker ps
CONTAINER ID        IMAGE               COMMAND                  CREATED             STATUS              PORTS                  NAMES
9fbe436a0c91        hello-html          "nginx -g 'daemon of…"   5 minutes ago       Up 5 minutes        0.0.0.0:8080->80/tcp   lucid_varahamihir

firefox:
# http://0.0.0.0:8080/hello.html
# http://localhost:8080/hello.html