## What is GraphQL
<ul>
  <li class="fragment">A query language that allow to fetch what you what</li>
  <li class="fragment">Flexible</li>
  <li class="fragment">A specification</li>
</ul>
<div class="fragment">
![spec](images/spec.png)
</div>

!SUB
## Who is using GraphQL

<img data-src="images/users.png" height="60%" width="60%">

http://graphql.org/users/


!SUB
## What is GraphQL
<table class="reveal">
  <tr>
    <td class="fragment"><img data-src="images/graphql-describe.png"></td>
    <td class="fragment"><img data-src="images/graphql-ask.png"></td>
    <td class="fragment"><img data-src="images/graphql-get.png"></td>
  </tr>
</table>


!SUB
## Hello World

![hello-1](images/hello1.png)

!SUB
## Hello World
![hello-2](images/hello2.png)


!SUB
<img data-src="images/model_0.png" height="80%" width="80%">

!SUB
<img data-src="images/model_1.png" height="80%" width="80%">

!SUB
<img data-src="images/model_2.png" height="80%" width="80%">

!SUB
# DEMO
<img data-src="images/giphy-hackerman.gif" height="80%" width="80%">


!SUB
### Demo internals
![demo-1-1](images/demo-1-1.png)


!SUB
### Demo internals
![demo-1-3](images/demo-1-2.png)

!SUB
### Demo internals
![demo-1-3](images/demo-1-3.png)

!SUB
### HTTP request
<div class="fragment" align="left">

```json
// HTTP POST request body
{  
   "query":"query { persons { name } }"
}
```

<div class="fragment" align="left">

```json
// HTTP response body
{  
   "data":{  
      "persons":[  
         {  
            "name":"..."
         },
      ]
   }
}
```

!SLIDE
### GraphQL Queries : Arguments

In REST you pass a single set of arguments as query parameters in GraphQL **every field and nested object** can get its own set.

<pre class="fragment"><code>
{                       {
  person(id: 1)           "data": {
    name                     "person" {
  }                             "name": "Niek Palm"
}                            }
                          }
                        }
</code></pre>

!SUB
### GraphQL Queries : Aliases
**Aliases** let you rename the result of a field to anything you want.
<pre class="fragment"><code>
{                                 {
  person(id: 1)                     "data": {
    name                              "person" {
  }                                       "name": "Niek Palm"
}                                      }
                                    }
                                  }

</code></pre>


!SUB
### GraphQL Queries : Aliases
**Aliases** let you rename the result of a field to anything you want.
<pre><code>
{                                 {
  speaker: person(id: 1)            "data": {
    fullName: name                    "speaker" {
  }                                       "fullName": "Niek Palm"
}                                      }
                                    }
                                  }

</code></pre>

!SUB
### GraphQL Queries : Fragments
GraphQL includes reusable units called **fragments**. Fragments let you construct sets of fields, and then include them in queries.

<pre class="fragment"><code>
fragment details on Person {
  name
  github
}
</code></pre>


!SUB
### GraphQL Queries : Variables
A GraphQL query can be parameterized with variables, maximizing query reuse, and avoiding costly string building in clients at runtime.


!SUB
# DEMO
<img data-src="images/giphy-programming.gif" height="60%" width="60%">


!SUB
### GraphQL Mutations

Any operations that cause writes should be sent explicitly via a mutation. To call a mutation, you must use the keyword **mutation** before your GraphQL query


!SUB
### GraphQL Mutations

```
mutation {
  addPerson(person: {name: "Edsgar"}) {
    id
    name
  }
}

```

!SUB
# DEMO
<img data-src="images/giphy-bart.gif" height="60%" width="60%">


!SUB
### GraphQL Subscriptions

<div class="fragment" align="left">

```
subscription {
  comments {
    comment
    author
  }
}
```

<div class="fragment" align="left">

```json
"data" : {
  "comments" : {
    "comment" : "Testing shows the presence,
                 not the absence of bugs"
    "author" : "Edsgar"
  }
}
```

!SUB
## Schema
A GraphQL schema is in essence the definition of a type system

<pre><code class="fragment">
schema {
    query: Query,
    mutation: Mutation
    subscription : Subscription
}

type Query {
  person(id: Long!): Person
}

type Person {
    id: ID!
    name: String!
}

</code></pre>


!SLIDE
### How to start implementing
![lang](images/graphql-languages-lib.png)

[GraphQL.org](https://graphql.org) and [Awesome GraphQL](https://github.com/chentsulin/awesome-graphql)

!SUB
![](images/sample-java.png)
<div class="fragment">
<img data-src="images/sample-java-graphiql.png" height="70%" width="70%">
[https://github.com/npalm/graphql-java-demo](https://github.com/npalm/graphql-java-demo)
</div>

!SUB
### Java example
- Spring Boot and GraphQL Spring Boot Starter <!-- .element: class="fragment" -->
- GraphQL (schema first) via GraphQL tools <!-- .element: class="fragment" -->
- GraphQL interface provided <!-- .element: class="fragment" -->
- Build via Gradle (and Docker) <!-- .element: class="fragment" -->


!SUB

<!-- .slide: data-background-size="contain" data-background="images/graphql-java.jpg" data-transition="slide" data-background-transition="fade" -->



!SUB
![](images/sample-javascript.png)
<div class="fragment">
<img data-src="images/sample-javascript-graphiql.png" height="70%" width="70%">
[https://github.com/npalm/graphql-js-demo](https://github.com/npalm/graphql-js-demo)
</div>

!SUB
## GraphQL Architecture
![graphql-architecture](images/rest-architecture-2.png)


!SUB
### Also Cool
- GraphQL for datastores: [Postgres](https://github.com/graphile/postgraphile) / [Neo4j](https://github.com/neo4j-graphql)
- Write a static blog using React and GraphQL, [Gatsby](https://www.gatsbyjs.org/)
- gRPC with GraphQL [Google rejoiner](https://github.com/google/rejoiner)
