> The Data Model
Let's define two entity classes Library and Address having a one-to-one relationship, using the @OneToOne annotation. The association is owned by the Library end of the association:

`@Entity
public class Library {

    @Id
    @GeneratedValue
    private long id;

    @Column
    private String name;

    @OneToOne
    @JoinColumn(name = "address_id")
    @RestResource(path = "libraryAddress", rel="address")
    private Address address;
    
    // standard constructor, getters, setters
}
@Entity
public class Address {

    @Id
    @GeneratedValue
    private long id;

    @Column(nullable = false)
    private String location;

    @OneToOne(mappedBy = "address")
    private Library library;

    // standard constructor, getters, setters
}`


> We must be careful to have different names for each association resource. Otherwise, we will encounter a JsonMappingException with the message: “Detected multiple association links with same relation type! Disambiguate association”.



> Creating the Resources
First, let's add a Library instance to work with:

`curl -i -X POST -H "Content-Type:application/json" 
  -d '{"name":"My Library"}' http://localhost:8080/libraries
The API returns the JSON object:

{
  "name" : "My Library",
  "_links" : {
    "self" : {
      "href" : "http://localhost:8080/libraries/1"
    },
    "library" : {
      "href" : "http://localhost:8080/libraries/1"
    },
    "address" : {
      "href" : "http://localhost:8080/libraries/1/libraryAddress"
    }
  }
}
Note that if you're using curl on Windows, you have to escape the double-quote character inside the String that represents the JSON body:`


testing 
`<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-engine</artifactId>
    <version>5.7.0</version>
    <scope>test</scope>
</dependency>
<dependency>
    <groupId>org.junit.jupiter</groupId>
    <artifactId>junit-jupiter-api</artifactId>
    <version>5.7.0</version>
    <scope>test</scope>
</dependency>
<dependency>
    <groupId>org.springframework</groupId>
    <artifactId>spring-test</artifactId>
    <version>5.3.3</version>
    <scope>test</scope>
</dependency>`




>  Enable Spring in Tests with JUnit 5
JUnit 5 defines an extension interface through which classes can integrate with the JUnit test.

> We can enable this extension by adding the @ExtendWith annotation to our test classes and specifying the extension class to load. To run the Spring test, we use SpringExtension.class.

> We also need the @ContextConfiguration annotation to load the context configuration and bootstrap the context that our test will use.

Let's have a look:

`@ExtendWith(SpringExtension.class)
@ContextConfiguration(classes = { ApplicationConfig.class })
@WebAppConfiguration
public class GreetControllerIntegrationTest {
    ....
}`

> Verify View Name
We can invoke the /homePage endpoint from our test as:

`http://localhost:8080/spring-mvc-test/`


`http://localhost:8080/spring-mvc-test/homePage`
First, let's see the test code:

`@Test
public void givenHomePageURI_whenMockMVC_thenReturnsIndexJSPViewName() {
    this.mockMvc.perform(get("/homePage")).andDo(print())
      .andExpect(view().name("index"));`
}