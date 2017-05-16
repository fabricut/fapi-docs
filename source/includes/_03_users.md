# Users

## Get Requesting User

This endpoint retrieves the user making the request.

### HTTP Request

`GET https://fabricut-fapi.herokuapp.com/users/whoami`

```shell
curl "https://fabricut-fapi.herokuapp.com/users/whoami" \
     -H "Authorization: Bearer eyJ0eI1NiJ9.eyJle6MX0.ukcjpjAtHtM" \
     -H "Accept: application/vnd.fabricut.v2"
```

> The above command returns JSON structured like this:

```json
{
  "data": {
    "id": 1,
    "type": "user",
    "attributes": {
      "first-name": "Charles",
      "last-name": "Smith",
      "email": "charles@fabricut.com"
    }
  }
}
```

## Get All Users

This endpoint retrieves all the users the requesting user account has permissions to.

### HTTP Request

`GET https://fabricut-fapi.herokuapp.com/users`

```shell
curl "https://fabricut-fapi.herokuapp.com/users" \
     -H "Authorization: Bearer eyJ0eI1NiJ9.eyJle6MX0.ukcjpjAtHtM" \
     -H "Accept: application/vnd.fabricut.v2"
```

> The above command returns JSON structured like this:

```json
{
  "data": [
    {
      "id": 1154,
      "type": "user",
      "attributes": {
        "first-name": "Whitney",
        "last-name": "Custo",
        "email": "whitney.custo@fabricut.com"
      }
    },
    {
      "id": 2184,
      "type": "user",
      "attributes": {
        "first-name": "Charles",
        "last-name": "Smith",
        "email": "chares@fabricut.com"
      }
    },
    {
      "id": 4873,
      "type": "user",
      "attributes": {
        "first-name": "Chuck",
        "last-name": "Jones",
        "email": "chuck@fabricut.com"
      }
    }
  ],
  "links": {}
}
```
