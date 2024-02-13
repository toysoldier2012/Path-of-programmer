#http

无状态
无法记录之前的用户状态


| Operation | API Endpoint      | HTTP Method | Response Status |
| --------- | ----------------- | ----------- | --------------- |
| Create    | `/cashcards`      | `POST`      | 201 (CREATED)   |
| Read      | `/cashcards/{id}` | `GET`       | 200 (OK)        |
| Update    | `/cashcards/{id}` | `PUT`       | 204 (NO DATA)   |
| Delete    | `/cashcards/{id}` | `DELETE`    | 204 (NO DATA)   |

# Restful API
#restful

Representation state transfer API

## GET requests
#get

Pour récupérer les inforamations

## POST requests
#post

Création

## DELETE requests
#delete

Suppression

## PUT/PATCH requests
#put #patch

PUT est pour modifier le resource, ou créer un nouveau resource s'il n'est pas exist
PATCH est pour modifier partiellement

# Status codes

200+ les codes réussi

300+ redirect

400+ Client error
- 400 bad request
- 401 unauthorized
- 403 forbidden
- 404 not found
- 405 method not allowed

500+ Server error

![[Pasted image 20230926205129.png]]