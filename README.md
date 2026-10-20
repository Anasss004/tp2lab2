# Lab — Spring Core : IoC et Injection de Dépendances

## Overview

Ce projet illustre la mise en œuvre du conteneur **IoC (Inversion of Control)** et de l'**Injection de Dépendances (DI)** avec le framework **Spring Core** en Java.

L'objectif est d'injecter dynamiquement les dépendances entre les couches DAO et Métier à l'aide des annotations Spring (`@Repository`, `@Component`, `@Autowired`, `@Qualifier` et `@Primary`).

Cette approche réduit le couplage entre les composants et permet de basculer facilement entre plusieurs implémentations de la couche DAO, notamment `DaoImpl` et `DaoImpl2`.

---

## Project Structure

```text
├── pom.xml
├── screen1.png
├── screen2.png
└── src/
    └── main/
        └── java/
            └── com/
                └── example/
                    ├── dao/
                    │   ├── IDao.java
                    │   ├── DaoImpl.java
                    │   └── DaoImpl2.java
                    ├── metier/
                    │   ├── IMetier.java
                    │   └── MetierImpl.java
                    └── presentation/
                        └── Presentation2.java
```

---

## Technical Stack

- **Language:** Java
- **JDK:** 17 / 21
- **Framework:** Spring Context 6.1.2
- **Build Tool:** Maven

---

## Execution Instructions

### 1. Compile the project

Open a terminal in the project directory and execute:

```bash
mvn clean compile
```

### 2. Run the application

Execute the `main` method of the following class:

```text
com.example.presentation.Presentation2
```

You can also run the application directly from your IDE, such as IntelliJ IDEA.

---

## Demonstrations & Screenshots

### 1. Execution with `DaoImpl`

The first execution demonstrates dependency injection using the `DaoImpl` implementation.

The DAO bean can be selected explicitly using `@Qualifier("dao")` or automatically using `@Primary`, depending on the configuration.

<img width="1917" height="1070" alt="10" src="https://github.com/user-attachments/assets/84342989-12a9-48db-8933-f56a2f201654" />

---

### 2. Execution with `DaoImpl2`

The second execution demonstrates how to switch to the `DaoImpl2` implementation using the `@Qualifier("dao2")` annotation.

This illustrates the flexibility of Spring's dependency injection mechanism without requiring significant changes to the business logic.

<img width="1907" height="962" alt="11" src="https://github.com/user-attachments/assets/86855233-e0fc-4fe6-8f55-ba86d8c95b99" />

---
<img width="1897" height="1020" alt="12" src="https://github.com/user-attachments/assets/f178df9a-5186-4cba-b5bf-92d0b57bc405" />

## Key Concepts

- **IoC (Inversion of Control):** Spring manages the creation and lifecycle of application objects.
- **Dependency Injection (DI):** Dependencies are provided by the Spring container rather than instantiated directly by dependent classes.
- **`@Component` / `@Repository`:** Declare classes as Spring-managed beans.
- **`@Autowired`:** Injects the required dependency.
- **`@Qualifier`:** Selects a specific bean when multiple implementations are available.
- **`@Primary`:** Defines the default bean when multiple candidates match a dependency.

---

## Conclusion

This lab demonstrates how Spring Core simplifies dependency management through IoC and DI. By separating interfaces from their implementations, the application becomes![Uploading 10.png…]()
 more modular, maintainable, and easier to extend.
