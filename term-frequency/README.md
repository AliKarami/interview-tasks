#Term Frequency

We want to build a multi-layer caching system on top of our search service, but the problem is if we cache every single query in the highest cache layer, it uses too much memory which is not acceptable. 
    
In order to solve this, we decided to keep track of user query frequencies through time, and in each period, fill each cache layer based on the term frequencies of the previous period.  
  
We need an application to generate frequency reports for us.  
    
These are the project specifications:    
1. Your Application should provide a REST API to get called on each search request and get the search query string as input.
2. Each query string contains one or multiple words, and it should be tokenized following the [Apache Lucene Standard Tokenizer](https://lucene.apache.org/solr/guide/6_6/tokenizers.html#Tokenizers-StandardTokenizer) and [Apache Lucene Keyword Tokenizer](https://lucene.apache.org/solr/guide/6_6/tokenizers.html#Tokenizers-KeywordTokenizer) rules, so you will have two different tokenization for each query.
3. You should keep track of each token frequency separately (both the Standard and the Keyword tokens).
4. The trend of the search queries is not constant and varies through time, and we should fill our caching system only based on "recent" frequencies, not the entire time. (time matters)
5. You should provide a way to export the frequency report; you will get two parameters:

| Parameter | Definition | Constraints | Default Value |  
|--|--|--|--|
| t | how "recent" frequencies should be included in the report (in hours) | <168 | 1 |
| n | how many tokens (in descending order) should be returned | <total # of tokens | 10 |

6. Your results should be in the `CSV` format.   
7. You're free to use any database, open-source tool, and library, but they should be dockerized. (`docker-compose.yml` should be there)    
    
You should:    
1. Design the term-frequency service and document your architecture briefly.    
2. Implement the service using Golang.    
3. Create a new public Github repository and push your solution to it.  
  
**P.S:** for anything which is not specified in project specifications, you're free to decide/design.
