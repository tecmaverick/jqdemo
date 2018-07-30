# jq Demo

## General
1. View the file contains valid json. If valid outputs the JSON file else will pinpoint the line which doesn't conforms to JSON grammer.
```
cat <filename>.json | jq .
```

2. To retun the raw string, use the raw switch, which return string without quotes

```
cat youtube.json | jq -r ".kind"
#outputs: youtube#searchListResponse
```


## Arrays
1. Get first element in an array. Sample JSON: [{"ID":"1"},{"ID":"2"}] 

```
cat json_array.json|jq ".[0]"
```

2. Get last element in an array, synatax similar to Python Sample JSON: [{"ID":"1"},{"ID":"2"}] 

```
cat json_array.json|jq ".[-1]"
```

3. Get value of first name key in an array index. Sample JSON: {"markers":[{"name":"Alpha"},{"name":"Beta"}]}

```
cat markers.json| jq ".markers[0] | .name"
#outputs "Alpha"

#To return raw string, i.e. taking off the double quotes, use the -r switch
cat markers.json| jq -r ".markers[0] | .name"
```

4. Get all values of a specific key in an array. Sample JSON: {"markers":[{"name":"Alpha"},{"name":"Beta"}]}
```
cat markers.json | jq ".markers[] | .name"
#outputs
"Alpha"
"Beta"
```





  
