# Project 12: “Federated” query by agents

[OVERVIEW Google Slide Deck](https://docs.google.com/presentation/d/1SKxtUceSBcfwzozCJn0HN4jqHLtO1c8_TaF5ZqrtzCY/edit?usp=sharing)

### SPARQL Endpoints (the two endpoints join on "participant"):

http://fairdata.systems:8990/sparql  (yes, 8990!  Not the default for virtuoso!)

<code><pre>
     PREFIX efo: \<http://www.ebi.ac.uk/efo/efo.owl#>
     PREFIX sio: \<http://semanticscience.org/resource/>
     PREFIX rdfs: \<http://www.w3.org/2000/01/rdf-schema#>
     select *
     where {
      ?inf a efo:EFO_0001067 .
      ?inf sio:has-participant ?participant .
     }
</pre></code>



http://ldp.cbgp.upm.es:8890/sparql

<code><pre>

PREFIX efo: \<http://www.ebi.ac.uk/efo/efo.owl#>
PREFIX sio: \<http://semanticscience.org/resource/>
PREFIX rdfs: \<http://www.w3.org/2000/01/rdf-schema#>
select *
where {
       ?participant a sio:pathogen .
       ?participant sio:has-identifier ?id .
}
</pre></code>

## Abstract

We wish to design a federated query framework that does not require the participating data sources to expose their data or their interface in the public (even password protected!).  The overall idea is that there is a metadata descriptor of the data in the resource, which allows a client to determine the data in that resource meets their requirements.  They then "knock on the door" of the data resource, and through some (undefined) certification process, ask that they be "invited inside".  The process of "inviting inside" is the data resource docker pull'ing the client's image (again, there will eventually be some kind of certification process here, for security!) and allowing that client to execute its query over their data resource.

The interface that will expose the data in the resource will be [Triple Pattern Fragments](https://linkeddatafragments.org/specification/triple-pattern-fragments/) because these are extremely easy to build, and can expose any kind of underlying data source (e.g. databases, triplestores, APIs etc.)

We anticipate using ShEX to describe the 'shape' of the data from each resource.  This will allow machmaking between user needs and one or more potential providers.


## Topics

Containers
 Data Platform
 Federated Human Data
 GA4GH partnership
 Interoperability Platform
 Rare Disease

**Project Number:** 12



**EasyChair Number:** 19

## Team

### Lead(s)

Mark D Wilkinson (mark.wilkinson@upm.es)

### Nominated participant(s)

Mark D Wilkinson
 Pablo Alarcon

## Expected outcomes

Expected outcomes: Some of the strategy for achieving the goals has been planned within other similar projects, such as the Personal Health Train and Farm Data Train (where several of the Hackathon participants are involved in those projects). As such, we can anticipate having a working strawman prototype by the end of four days. This will then be evaluated (post-hackathon) by the other members of the technical architecture team of EJP, as well as by these peer communities, with the aim of reaching a final architecture proposal with at least one reference implementation, to put forward to the public by early 2021.

## Expected audience

Coders in Ruby or Python; experience with Linked Data, SPARQL, Docker, and ontologies; good grasp of HTTP Protocols.

**Number of expected hacking days**: 4

