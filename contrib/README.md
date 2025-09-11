# Contribution tooling
To build and distribute our ontology, we took the follwing stack: 

- Widoco to generate website documentation for a `rdf` file
- VocBench to collaborate over the ontology. (picked from [W3C Ontology Editor List](https://www.w3.org/wiki/Ontology_editors)).

## Workflows

**General workflow**  
1. Contributors, Reviewers and Maintainers update or suggest update on VocaBench.
2. When decided, Maintainers pin a new version and export it on `/release` folder
3. Once pushed, a github pipeline generates the documentation and serve it as a github page.

**Onboarding workflow**  
1. A person sign up
2. System administrators and admin receive mails notification
3. System administrators define roles and permission for this new member.

**Issue/tickets workflow**  
This is not yet define, we use github issues for now.

## Local Development

- run `docker compose up`
- access [http://localhost:1979/vocbench3](http://localhost:1979/vocbench3)
- create your system administrator
- enjoy

To run the documentation script over a new release: 
- Place your file under the name: `v0.0.<my-version>.rdf`
- run `bin/widoco`
- open the index-en.html file on your browser.
