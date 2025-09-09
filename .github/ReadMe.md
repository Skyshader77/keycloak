https://hub.docker.com/_/sonarqube/

TODO: find a way to automate all of this so we don't have to do this everytime we want to do an analysis

1) Start the Docker Daemon
```sh
sudo systemctl start docker
```
1) run a docker sonarqube instance
```sh
sudo docker run -d -p 9000:9000 sonarqube:community
```
2) Clone the repo

```sh
git clone git@github.com:Skyshader77/keycloak.git
```

4) Go to the repo's root directory

5) Go to your sonarqube instance and create an account
```sh
http://localhost:9000
```
6) Create a local project. IMPORTANT: Project name should be keycloak.

7) Click on Other CI in the Analysis ooptions

8) Generate the token

TODO:in the yaml file, find a way to only run the analysis for the admin console.

10) Copy the token's value and write it to the Dsonar.token value in the docker-compose.yml in the Git repository's root.

11) run the analysis
```sh
sudo docker-compose up maven-sonar
```

11) return to http://localhost:9000 once the analysis is over. This will take around 10-15 minutes.
