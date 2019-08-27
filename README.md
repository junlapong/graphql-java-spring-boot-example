# graphql-java-spring-boot-example
Sample app for my tutorial [Building a GraphQL Server with Spring Boot](https://app.pluralsight.com/guides/building-a-graphql-server-with-spring-boot). 

You'll need Java 8.

Clone this repo and execute

```
./gradlew bootRun
```

Or inside an IDE, execute the class `com.example.DemoGraphQL.DemoGraphQlApplication`.

You can go to [http://localhost:8080/h2-console/login.jsp](http://localhost:8080/h2-console/login.jsp) and enter the following information:
- JDBC URL: jdbc:h2:mem:testdb
- User Name: sa
- Password: \<blank\>

To check the database or to [http://localhost:8080/graphiql](http://localhost:8080/graphiql) to start executing queries. For example:

## Example

### findAllBooks

```graphql
{
  findAllBooks {
    id
    isbn
    title
    pageCount
    author {
      firstName
      lastName
    }
  }
}
```

### newBook

```graphql
mutation {
  newBook(
    title: "Java: The Complete Reference, Tenth Edition"
    isbn: "1259589331"
    pageCount: 555
    author: 1
  ) {
    id
    title
  }
}
```

### newAuthor

```graphql
mutation {
  newAuthor (
    firstName: "Alex"
    lastName: "Banks"
  ) {
    id
  }
}
```

### findAllAuthors

```graphql
{
  findAllAuthors {
    id
    firstName
    lastName
  }
}
```

### newBook

```graphql
mutation {
  newBook(
    title: "Learning GraphQL"
    isbn: "9781492030706"
    pageCount: 345
    author: 2
  ) {
    id
    title
  }
}
```

### deleteBook

```graphql
mutation {
  deleteBook(id: 3)
}
```

### updateBookPageCount

```graphql
mutation {
  updateBookPageCount(id: 2, pageCount: 250) {
    id
    pageCount
  }
}
```

## License
MIT
