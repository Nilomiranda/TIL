You can tell eslint to ignore a certain block of code, instead of just next line or the whole file by doing the following:

```javascript
/* eslint-disable @typescript-eslint/indent */  
	
	// block of code for lint to ignore

/* eslint-enable @typescript-eslint/indent */  
```

The syntax is as follows:

`/* eslint-disable ESLINT_RULE_NAME */`

code in between

``/* eslint-enable ESLINT_RULE_NAME */``