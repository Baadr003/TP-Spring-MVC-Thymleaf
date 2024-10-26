# Application CRUD Spring Boot & Thymeleaf 

Une application CRUD simple construite avec Spring Boot et Thymeleaf, démontrant les fonctionnalités de gestion des utilisateurs.

##  Fonctionnalités

-  Créer, Lire, Mettre à jour et Supprimer des utilisateurs
-  Validation des formulaires
-  Interface utilisateur simple et claire
-  Code source facile à comprendre

## Technologies Utilisées

- Spring Boot 
- Thymeleaf
- MySQL
- Maven
- Hibernate
- Spring MVC

## Prérequis

Assurez-vous d'avoir installé :

- Java 8 ou supérieur
- Maven
- MySQL
- Un IDE : IntelliJ

##  Pour Commencer

### 1. Configurer MySQL
Créer une nouvelle base de données :
```sql
CREATE DATABASE thymeleaf;
```

### 2. Configurer application.properties
```properties
server.port=8080

# Configuration de la base de données
spring.datasource.url=jdbc:mysql://localhost:3306/thymeleaf?useUnicode=true&useJDBCCompliantTimezoneShift=true&useLegacyDatetimeCode=false&serverTimezone=UTC
spring.datasource.username=root
spring.datasource.password=

# Configuration JPA
spring.jpa.show-sql=true
spring.jpa.hibernate.ddl-auto=update
```

Visitez `http://localhost:8080` dans votre navigateur.

##  Structure du Projet

```
src/
├── main/
│   ├── java/
│   │   └── com/example/
│   │       ├── domain/
│   │       │   └── User.java
│   │       ├── repository/
│   │       │   └── UserRepository.java
│   │       ├── controller/
│   │       │   └── UserController.java
│   │       └── DemothymeleafApplication.java
│   └── resources/
│       ├── templates/
│       │   ├── add-user.html
│       │   ├── update-user.html
│       │   └── index.html
│       └── application.properties
```

##  Utilisation

1. **Ajouter un Utilisateur :**
   - Cliquez sur "Ajouter un nouvel utilisateur"
   - Remplissez le formulaire
   - Cliquez sur Soumettre

2. **Voir les Utilisateurs :**
   - Visitez la page d'accueil pour voir tous les utilisateurs

3. **Mettre à jour un Utilisateur :**
   - Cliquez sur "Modifier" à côté de l'utilisateur
   - Modifiez les informations
   - Cliquez sur Mettre à jour

4. **Supprimer un Utilisateur :**
   - Cliquez sur "Supprimer" à côté de l'utilisateur
   - Confirmez la suppression

##  Composants Clés

### Entité User
```java
@Entity
public class User {
    @Id
    @GeneratedValue(strategy = GenerationType.AUTO)
    private long id;
    
    @NotBlank(message = "Le nom est obligatoire")
    private String name;
    
    @NotBlank(message = "L'email est obligatoire")
    private String email;
    
    // Getters et Setters
}
```

### Repository User
```java
@Repository
public interface UserRepository extends CrudRepository<User, Long> {
}
```

##  Résolution des Problèmes

Problèmes courants et solutions :

1. **Échec de Connexion à la Base de Données**
   - Vérifiez que MySQL est en cours d'exécution
   - Vérifiez les identifiants de la base de données
   - Assurez-vous que la base de données existe

2. **L'Application ne Démarre Pas**
   - Vérifiez si le port 8080 est disponible
   - Vérifiez la version de Java
   - Vérifiez la configuration dans application.properties

##  Vidéo Démonstratif



https://github.com/user-attachments/assets/860db14f-217f-4062-bde3-229771425a38


