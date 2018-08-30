# GraphQL - The next API language
Slide deck for the talk [GraphQL - The Next API Language](https://2018.javazone.no/program/5c1efd67-e8f0-432d-bf25-696a51db2068) at the JavaZone 2018 in Oslo.

- You can view the slides via GitHub static pages [here](http://npalm.github.io/graphql-slides-20180913).
- The sources of the example in this talk are in this [repo](https://github.com/npalm/graphql-java-demo)

## slides
For the slides we use the [RevealJS](https://github.com/hakimel/reveal.js/) framework.
- See index.html for the slide show composition
- See markdown/* for the slide sources.

### Run the slides from sources
- You can also run the slides locally in a container from sources.
```
docker run -d -p 8080:80 --name slides \
  -v ${PWD}:/usr/share/nginx/html nginx
```
- Or use yarn
```
yarn && yarn start
```
- Open a browser [slides](http://localhost:9000/)
