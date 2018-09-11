<!-- .slide: data-background="images/past.jpg" data-transition="slide" data-background-transition="fade" -->

!SUB
## REST API

Resource: `/talks`
```
[
  {
    "title" : "GraphQL - The Next API Language",
    "speaker" : {
      "id" : "niek",
      "href" : "http://someconference/speakers/niek"
    }
  }
  {
    "title" : "Built To Last ...and the end of migrations",
    "speaker" : {
      "id" : "adam",
      "href" : "http://someconference/speakers/adam"
    }
  }
]
```

!SUB
## REST API
Resource `/speakers/niek`

```
{
  "id" : "niek",
  "name" : "Niek Palm",
  "twitter" : "niekos77",
  "blog" : "https://040code.github.io",
  "github": "npalm",
  "city" : "Eindhoven",
  "shoppinglist" : {
    "href" : "http://someconference/speakers/niek/shoppinglist"
  }
}
```

!SUB
## REST Architecture
![rest](images/rest-architecture.png)

!SUB
## REST Architecture
![rest-2](images/rest-architecture-2.png)
