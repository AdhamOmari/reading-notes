> Spring Security Architecture
This guide is a primer for Spring Security, offering insight into the design and basic building blocks of the framework. We cover only the very basics of application security. However, in doing so, we can clear up some of the confusion experienced by developers who use Spring Security. To do this, we take a look at the way security is applied in web applications by using filters and, more generally, by using method annotations. Use this guide when you need a high-level understanding of how a secure application works, how it can be customized, or if you need to learn how to think about application security.

> This guide is not intended as a manual or recipe for solving more than the most basic problems (there are other sources for those), but it could be useful for beginners and experts alike. Spring Boot is also often referenced, because it provides some default behavior for a secure application, and it can be useful to understand how that fits in with the overall architecture.


> Authentication and Access Control
Application security boils down to two more or less independent problems: authentication (who are you?) and authorization (what are you allowed to do?). Sometimes people say “access control” instead of "authorization", which can get confusing, but it can be helpful to think of it that way because “authorization” is overloaded in other places. Spring Security has an architecture that is designed to separate authentication from authorization and has strategies and extension points for both.

> he main strategy interface for authentication is AuthenticationManager, which has only one method:

`public interface AuthenticationManager {

  Authentication authenticate(Authentication authentication)
    throws AuthenticationException;
}`

> The most commonly used implementation of AuthenticationManager is ProviderManager, which delegates to a chain of AuthenticationProvider instances. An AuthenticationProvider is a bit like an AuthenticationManager, but it has an extra method to allow the caller to query whether it supports a given Authentication type:

`public interface AuthenticationProvider {

	Authentication authenticate(Authentication authentication)
			throws AuthenticationException;

	boolean supports(Class<?> authentication);
}`


![alt](https://github.com/spring-guides/top-spring-security-architecture/raw/main/images/authentication.png)



> Customizing Authentication Managers
Spring Security provides some configuration helpers to quickly get common authentication manager features set up in your application. The most commonly used helper is the AuthenticationManagerBuilder, which is great for setting up in-memory, JDBC, or LDAP user details or for adding a custom UserDetailsService. The following example shows an application that configures the global (parent) AuthenticationManager:

`@Configuration
public class ApplicationSecurity extends WebSecurityConfigurerAdapter {

   ... // web stuff here

  @Autowired
  public void initialize(AuthenticationManagerBuilder builder, DataSource dataSource) {
    builder.jdbcAuthentication().dataSource(dataSource).withUser("dave")
      .password("secret").roles("USER");
  }

}`


> has a UserDetailsService
* passwordEncoder bean
* configure AuthManagerBuilder
* auth.userDetailsService(userDetailsService).passwordEncoder(passwordEncoder());
* configure HttpSecurity
* cors? csrf?
* matchers for URLs that are allowed
* ensure that login and signup URLs allowed; also consider homepage etc.
* formLogin with login page set up
* logout
 `   @Override
    @Bean
    public AuthenticationManager authenticationManagerBean() throws Exception {
        return super.authenticationManagerBean();
    }
> Step 6: registration page`

* create it w/ form
* ensure it posts to the route you specified in web config
* try it out!
* add to a template w/ things about the Principal