# Room

## save data in a local database using Room


* The Room persistence library provides an abstraction layer over SQLite to allow fluent database access while harnessing the full power of SQLite.
* Room provides the following benefits:
  1. Compile-time verification of SQL queries.
  2. Convenience annotations that minimize repetitive and error-prone boilerplate code.
  3. Streamlined database migration paths.


> Because of these considerations, we highly recommend that you use Room instead of using the SQLite APIs directly.


> add the following dependencies to your app's build.gradle file:
>  `dependencies {
    def room_version = "2.3.0"

    implementation "androidx.room:room-runtime:$room_version"
    annotationProcessor "androidx.room:room-compiler:$room_version"

    // optional - RxJava2 support for Room
    implementation "androidx.room:room-rxjava2:$room_version"

    // optional - RxJava3 support for Room
    implementation "androidx.room:room-rxjava3:$room_version"

    // optional - Guava support for Room, including Optional and ListenableFuture
    implementation "androidx.room:room-guava:$room_version"

    // optional - Test helpers
    testImplementation "androidx.room:room-testing:$room_version"

    // optional - Paging 3 Integration
    implementation "androidx.room:room-paging:2.4.0-alpha04"
}`

> Primary components
* There are three major components in Room:
* The database class that holds the database and serves as the main access point for the underlying connection to your app's persisted data.
* Data entities that represent tables in your app's database.
* Data access objects (DAOs) that provide methods that your app can use to query, update, insert, and delete data in the database.
* The database class provides your app with instances of the DAOs associated with that database.
* The app can also use the defined data entities to update rows from the corresponding tables, or to create new rows for insertion.

> Data access object (DAO)
* UserDao provides the methods that the rest of the app uses to interact with data in the user table.

`@Dao
public interface UserDao {
    @Query("SELECT * FROM user")
    List<User> getAll();

    @Query("SELECT * FROM user WHERE uid IN (:userIds)")
    List<User> loadAllByIds(int[] userIds);

    @Query("SELECT * FROM user WHERE first_name LIKE :first AND " +
           "last_name LIKE :last LIMIT 1")
    User findByName(String first, String last);

    @Insert
    void insertAll(User... users);

    @Delete
    void delete(User user);
}`

> Defining data using Room entities

`@Entity
public class User {
    @PrimaryKey
    public int id;

    public String firstName;
    public String lastName;
}
If you want the table to have a different name, set the tableName property of the @Entity annotation.
Room uses the field names as column names in the database by default.
@Entity(tableName = "users")
public class User {
    @PrimaryKey
    public int id;

    @ColumnInfo(name = "first_name")
    public String firstName;

    @ColumnInfo(name = "last_name")
    public String lastName;
}`