# 1.3.9 Non-tabular data: Linked Data

Example SPARQL query for [Wikipedia SPARQL endpoint](http://dbpedia.org/snorql)  

Here's an example for Tom Hanks

```
PREFIX rdfs: <http://www.w3.org/2000/01/rdf-schema#>
PREFIX rdf: <http://www.w3.org/1999/02/22-rdf-syntax-ns#>  
PREFIX dbo: <http://dbpedia.org/ontology/>  
PREFIX : <http://dbpedia.org/resource/>  
SELECT ?movie ?title   
WHERE {  
	?movie rdf:type dbo:Film .  
	?movie dbo:starring :Tom_Hanks .  
	?movie rdfs:label ?title  
}
```

Note: this will return all the titles in different languages! If you want to filter for en (English) only then add a FILTER statement:

```
FILTER (lang(?title) = 'en')
```
