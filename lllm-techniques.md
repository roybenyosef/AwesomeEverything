# Enforcing structured output
* use a 3rd party like: https://github.com/jxnl/instructor
  * example with pydnatic: https://python.useinstructor.com/blog/2023/09/11/generating-structured-output--json-from-llms/
* in openai there is json mode: https://platform.openai.com/docs/guides/text-generation/json-mode - put it can be prompt injected to break schema
  * https://www.youtube.com/watch?v=zt1zCwLrSPg
* few shot for example
* 

# Prompt Injection
  * use different language
  * role playing, gandma technique!
  * https://www.anthropic.com/research/many-shot-jailbreaking
  * https://www.microsoft.com/en-us/security/blog/2024/06/26/mitigating-skeleton-key-a-new-type-of-generative-ai-jailbreak-technique/
  * https://github.com/leondz/garak

# Coding assistent security
* using copilot for example, you might get an sql injection when prompting naively
```
public class SearchRepository {
   public List<Product> searchProduct (String input) {
       // lowercase the input
       var Lower Input = input.toLowerCase(Locale.R00T);

       // NAIVE prompt:
       // create a query matching the input to the product name or the product description
       var query = em. createNativeQuery("Select * from Product where lower(description) like '%"
       lower Input + "%' OR lower(product_name) Like '%" + Lower Input + "%' ", resultClass:Product.class);  
       // execute the query
       var resultList = (List<Product>) query getResultList();
       // return the list of results
       return resultList;
   }
}
```

Instead, we should know what we want to ask - ask for named parameters!
```
// create a query using named parameters matching the input to the product name and the product description
var query = em.createNativeQuery(sqlString:"Select * from Product where lower(description) like
: input OR lower (product_name) like : input", resultClass: Product.class);
// set the named parameter
query setParameter ("input", "%" + lowerInput +"/"）；
// execute the query
var resultList = (List<Product>) query getResultList();
// return the list of results
return resultList;
```




