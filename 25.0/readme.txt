#validate the db connection after deployment.


kubectl exec -it deployment/postgres -- bash

Connect to the Database:
psql -U keycloak -d keycloak

List Tables:
\dt

Query the User: (new user get created in keycloak)
query example:
SELECT * FROM user_entity WHERE username = 'new_username'; 

SELECT * FROM user_entity WHERE username = 'praba';


the main turn around happaned when adding the below flag to move the keycloak from in file database to external db.

        args:
        - start-dev
        - '--spi-db-schema-manager-updates=update'

-------------------------------------
------------------------------------- 

16 - Sep - 2024
The deployment configuration are update to helm chart.
clone the repo and get in to helm_keycloak folder and try the installation.

helm install my-keycloak . --dry-run -n keycloak-helm
