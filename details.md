
## Token format

 Tokens are flat json arrays. This way they can be appended as url parameterst to `http` `GET` requests.
 
 ```
 {
   "pennytoken-service-provider" : "<Identifying URL of the service provider that issued the token.>"
   "pennytoken-token-secret" : <The secret that uniquely identifies the token.>
 }
 ```
 
 The value of the pennytoken is not part of the token itself. 
 Instead the service provider responds with the value of the token 
 when the token is verified and cached-in by the content provider.
 
 ## Interaction between content provider and user
 
 The content provider can announce that it supports pennytoken micropayment 
 services by including an element of the following format in the `html` of any page it serves.
 It is important that this information is also sent in pages that are freely accessible without pennytokens.
 For example, it can be included in the landing page, or in ad-supported pages 
 that can alternatively be served without ads when pennytokens are passed.
 
 ```
 <meta content='
		{
		    "pennytoken": {
		      {
		        "urls"    : <regex pattern matching all urls that support/require pennytokens. E.g. "http://www.nyt.com/*">,
		        "price"   : <token price per page load in fractions of dollar cents>
		        "feature" : <a description of what is offered in exchange for the tokens. E.g. "no ads">
		      }
		    }
		}'
	>
	```
	
	The users browser plugin parses the information in html and manages when tokens are sent. 
	How this is done is left to the implementation. However, the intention is NOT that the user confirms the issue
	of a token on every page request. 
	
	
 
 