# Nested query with foreign keys

```graphql
{
    repos {
        nodes {
            name
            license {
                _key
                name
            }
        }
    }
}
```
[Try this query](https://datasette-graphql-demo.datasette.io/graphql/fixtures?query=%0A%7B%0A%20%20%20%20repos%20%7B%0A%20%20%20%20%20%20%20%20nodes%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20name%0A%20%20%20%20%20%20%20%20%20%20%20%20license%20%7B%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20_key%0A%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20%20name%0A%20%20%20%20%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%20%20%20%20%7D%0A%20%20%20%20%7D%0A%7D%0A)

Expected output:

```json
{
    "repos": {
        "nodes": [
            {
                "name": "datasette",
                "license": {
                    "_key": "apache2",
                    "name": "Apache 2"
                }
            },
            {
                "name": "dogspotter",
                "license": {
                    "_key": "mit",
                    "name": "MIT"
                }
            },
            {
                "name": "private",
                "license": null
            }
        ]
    }
}
```
