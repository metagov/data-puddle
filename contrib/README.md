# Contribution tooling
To build and distribute our ontology, we took the follwing stack: 

- Widoco to generate website documentation for a `rdf` file
- VocBench to collaborate over the ontology. (picked from [W3C Ontology Editor List](https://www.w3.org/wiki/Ontology_editors)).

## Workflows

1. Contributors, Reviewers and Maintainers update or suggest update on VocaBench.
2. When decided, Maintainers pin a new version and export it on `/release` folder
3. Once pushed, a github pipeline generates the documentation and serve it as a github page.

## Local Development

- run `docker compose up`
- access [http://localhost:1979/vocbench3](http://localhost:1979/vocbench3)
- create your system administrator
- enjoy