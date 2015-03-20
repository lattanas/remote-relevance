NOTE: This does not actually work yet. Still in initial development.

# remote-relevance
Evaluate relevance on remote systems using BigFix actions.

#### Concept:

- user enters relevance query into webapp
- webapp creates a BigFix action using REST API targeting a "testing" computer group
- action uses relevance substitution to return the result to the webapp using CURL(or similar) on the endpoint

Relevance Substitution on Client:
    concatenations "~" of (base64 encode it) of unique values of (it as string) of ( THE_RELEVANCE_QUERY_GOES_HERE )
Example:
    concatenations "~" of (base64 encode it) of unique values of (it as string) of ( names of regapps )

#### Models?

- computers
  - /api/computer/{computer id}
- computergroups
  - /api/computergroup/{site type}/{site name}/{id}/computers

- computergroups
  - queries
    - computers
      - results

#### frameworks

Not sure yet: 
- Node.js
- WebSockets?
- Express or Loopback?

#### References:

[ IBM DevWorks BigFix REST API Doc ](https://www.ibm.com/developerworks/community/wikis/home?lang=en#!/wiki/Tivoli+Endpoint+Manager/page/REST+API)

http://stackoverflow.com/questions/695438/safe-characters-for-friendly-url

https://en.wikipedia.org/wiki/Base64

http://bigfix.me/relevance/details/2163
