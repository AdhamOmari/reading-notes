> 2.1. @RequestMapping — by Path
`@RequestMapping(value = "/ex/foos", method = RequestMethod.GET)
@ResponseBody
public String getFoosBySimplePath() {
    return "Get some Foos";
}`

> RequestMapping — the HTTP Method
The HTTP method parameter has no default. So, if we don't specify a value, it's going to map to any HTTP request.

> `@RequestMapping(value = "/ex/foos", method = POST)
@ResponseBody
public String postFoos() {
    return "Post some Foos";
}`

> RequestMapping and HTTP Headers
> `@RequestMapping(value = "/ex/foos", headers = "key=val", method = GET)
@ResponseBody
public String getFoosWithHeader() {
    return "Get some Foos with Header";
}`


> Accessing Data with JPA

> What You Will build ? You will build an application that stores Customer POJOs (Plain Old Java Objects) in a memory-based database.


> Spring Data JPA focuses on using JPA to store data in a relational database. Its most compelling feature is the ability to create repository implementations automatically, at runtime, from a repository interface.


`package com.example.accessingdatajpa;

import java.util.List;

import org.springframework.data.repository.CrudRepository;

public interface CustomerRepository extends CrudRepository<Customer, Long> {

  List<Customer> findByLastName(String lastName);

  Customer findById(long id);
}`

> Create an Application Class
Spring Initializr creates a simple class for the application. The following listing shows the class that Initializr created for this example (in src/main/java/com/example/accessingdatajpa/AccessingDataJpaApplication.java):

`package com.example.accessingdatajpa;

import org.springframework.boot.SpringApplication;
import org.springframework.boot.autoconfigure.SpringBootApplication;

@SpringBootApplication
public class AccessingDataJpaApplication {

  public static void main(String[] args) {
    SpringApplication.run(AccessingDataJpaApplication.class, args);
  }

}`

> Notice the typical CRUD functionality:

* save(…) – save an Iterable of entities. Here, we can pass multiple objects to save them in a batch
* findOne(…) – get a single entity based on passed primary key value
* findAll() – get an Iterable of all available entities in database
* count() – return the count of total entities in a table
* delete(…) – delete an entity based on the passed object
* exists(…) – verify if an entity exists based on the passed primary key value
