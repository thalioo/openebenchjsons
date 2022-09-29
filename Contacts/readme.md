PerMedCoE_contact0.json is empty.
Other contacts are OK. One comment about the use of OpenEBench REST API.
The Contact collection endpoint is:
https://openebench.bsc.es/api/scientific/staged/Contact
But this endpoint is for the **collection** (!).
~~~shell
curl -k -H "Content-Type: application/json" \
-u user:password https://openebench.bsc.es/api/scientific/staged/Contact?community_id=OEBC009 -d @PerMedCoE_contact1.json
~~~
It expects the ARRAY of contacts:

~~~shell
[
{
    "_id": "Arnau.Montagud",
    "_schema" : "https://www.elixir-europe.org/excelerate/WP2/json-schemas/1.0/Contact",
    "community_id" : "OEBC009",
    "contact_type": "person",
    "givenName": "Arnau",
    "surname": "Montagud",
    "email": [
      "arnau.montagud@bsc.es"
    ]
}
]
~~~
alternatively, it can be:
~~~shell
curl -k -H "Content-Type: application/json" -u user:password \
https://openebench.bsc.es/api/scientific/staged/Contact/Arnau.Montagud?community_id=OEBC009 -d @PerMedCoE_contact1.json
~~~
that includes the contact_id in the URL.
