
Explanation 
========================

The filter of logstash.config

		filter {
			grok {
				match => {     "email" => "%{DATA:account}@"   }
				
				add_field => { "username" => "%{account}"      }
				}
			}		 


1. email is a name of old field & exists in test1 index.
2. account is a variable.
3. username is a name of new field. 



### Before Parsering
```JSON
  { 
     "email" : "lucasko.tw@gmail.com" 
  }

```

### After Parsering
```JSON
  { 
     "email" : "lucasko.tw@gmail.com"  ,

     "username" : "lucasko.tw"
  }

```


