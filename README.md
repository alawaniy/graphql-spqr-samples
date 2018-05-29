# GraphQL SPQR Spring Boot Samples

Package with maven, run the jar, play around.

Out of the box it runs on port 7777

Graphiql tool is mapped to root (e.g. http://localhost:7777/)

API is exposed on /graphql

* Spring Boot SPQRR Sample

http://localhost:7777

```graphql
{
  getNormalGreeting(person: {firstName: "si", lastName: "li"})
}
```


```graphql
{
  getPoliteGreeting(customer: {firstName: "san", lastName: "li", title: MR})
}
```


```graphql
{
  getProductsInStock(vendorId: 2) {
    product {
      name
      description
    }
    stockSize
  }
}
```


```graphql
{
  firstNPersons(count: 5) {
    firstName
    lastName
    socialNetworkAccounts {
      networkName
      username
      numberOfConnections
    }
  }
}
```

* Spring Boot SPQR Starter Sample

http://localhost:8989/graphiql

```graphql
mutation {
  createProject(name: "spring boot", tags: ["java"]) {
    code
    name
    done
    tags
    issues {
      code
      description
      status
    }
  }
}
```


```graphql
mutation {
  createIssue(projectCode: "BPR", description: "spring boot description", status: DONE) {
    code
    description
    project {
      name
      tags
      done
      code
    }
    status
  }
}
```


```graphql
{
  project(code: "BPR") {
    code
    done
    name
    tags
    issues {
      code
      description
      status
      project {
        code
        name
        tags
      }
    }
  }
}
```

