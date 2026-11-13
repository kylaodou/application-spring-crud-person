# Spring Boot — CRUD de personnes

API REST Spring Boot qui gère une liste de personnes (création, lecture, mise à jour, suppression)
avec une base H2 en mémoire. Le projet montre une architecture en couches (contrôleur, service
générique, dépôt JPA), une gestion centralisée des erreurs et des tests.

## Routes

| Méthode | Route | Rôle |
|---|---|---|
| GET | `/persons` | Liste des personnes |
| GET | `/persons/{id}` | Détail d'une personne |
| POST | `/persons` | Création |
| PUT | `/persons` | Mise à jour |
| DELETE | `/persons/{id}` | Suppression |

Les erreurs sont renvoyées au format JSON par `RestControllerExceptionHandler`
(`400 Bad Request`, `404 Not Found`).

Une collection Postman prête à l'emploi se trouve dans `postman/`.

## Stack technique

- Java 11, Spring Boot 2.7 (Web, Data JPA)
- Base H2 en mémoire
- Lombok
- JUnit, WebFlux (WebTestClient) pour les tests
- Maven

## Lancement

Prérequis : JDK 11 ou plus.

```bash
git clone https://github.com/kylaodou/application-spring-crud-person.git
cd application-spring-crud-person

./mvnw spring-boot:run        # Linux / macOS
mvnw.cmd spring-boot:run      # Windows
```

L'API écoute sur http://localhost:8080. La console H2 est disponible sur
http://localhost:8080/h2-console (URL JDBC : `jdbc:h2:mem:persondb`, utilisateur `sa`).

## Tests

```bash
./mvnw test
```

## Auteur

[@kylaodou](https://github.com/kylaodou)
