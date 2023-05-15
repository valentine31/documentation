# Quality 

## SonarQube

### Présentation
SonarQube est l'un des outils d'analyse de code source fournis par l'offre Cloud π Native, il permet de vérifier la qualité du code lors des différentes étapes du processus de développement, de la construction à la livraison.

Des *Quality gates* seront positionné afin de garantir que le code construit respecte les normes de sécurité et de qualité.


### Utilisation depuis la CI

Les variables d'environnement suivantes sont disponibles permettant de contacter sonar :

- SONAR_HOST_URL
- SONAR_TOKEN

Celui-ci sera préconfiguré pour quelques outils (npm, mvn, ...) et disponible dans les templates Gitlab CI et utilisable via l'exemple suivant :

```yaml
test_front:
  variables:
    WORKING_DIR: "src"
  stage: test
  extends:
    - .node:sonar
```

## Trivy

### Présentation
Trivy est l'un des outils d'analyse de code source fournis par l'offre Cloud π Native, il permet de vérifier la qualité du code lors des différentes étapes du processus de développement, de la construction à la livraison.

Des *Quality gates* seront positionné afin de garantir que le code construit respecte les normes de sécurité et de qualité.


### Utilisation depuis la CI

Les variables d'environnement suivantes sont disponibles permettant de contacter sonar :

- SONAR_HOST_URL
- SONAR_TOKEN

Celui-ci sera préconfiguré pour quelques outils (npm, mvn, ...) et disponible dans les templates Gitlab CI et utilisable via l'exemple suivant :

```yaml
trivy_scan_back:
  variables:
    WORKING_DIR: 'src'
    IMAGE_NAME: 'candilibv2'
    DOCKERFILE: 'Dockerfile-devops'
  stage: test-docker
  extends:
    - .docker:test
```