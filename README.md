# Asset-Management-System-using-Spring-Boot
Assignment project

### To run this project after cloning:
-> Run the following docker command to create a database in MySQL <br>
-> ``` docker run -d -e MYSQL_ROOT_PASSWORD=1234 -e MYSQL_DATABASE=asset_management --name mysqldb -p 3306:3306 mysql:8.0 ``` <br>
-> After succesfully running the docker container, build/run the project <br>
Postman collection link:<br>
``` https://api.postman.com/collections/32222541-d1f18cfd-04cb-4154-8a2a-2d1e33bb398c?access_key=PMAT-01HKS9HWQ1PPHV2KB9TEAABD7H ```

For Categories:<br>
Get all categories:<br>
``` /api/categories ```<br>
Get a category by id:<br>
``` /api/categories/{categoryId} ```<br>
Post a new category:<br>
``` /api/categories ```<br>
Delete a category:<br>
``` /api/categories/{categoryId} ```<br>
Update a category:<br>
``` /api/categories/{categoryId} ```<br>
Note: Cannot delete a category if it is assigned to some asset<br>
<br><br>


For Assets:<br>
Get all assets:<br>
``` /api/assets ```<br>
Get an asset by id:<br>
``` /api/assets/id/{assetId} ```<br>
Get an asset by name:<br>
``` /api/assets/name{assetName} ```<br>
Post a new asset:<br>
``` /api/assets/ ```<br>
Delete an asset:<br>
``` /api/assets/{assetId} ```<br>
Update an asset:<br>
``` /api/assets/{assetId} ```<br>
Assign an asset:<br>
``` /api/assets/{assetId}/assign?assignmentStatus=ASSIGNED ```<br>
Recover an asset:<br>
``` /api/assets/{assetId}/recover?assignmentStatus=RECOVERED ```<br>
Certainly! Here's the provided information converted into Markdown code:
```markdown
# Asset Management System API Documentation
## GET
### Get all categories
- **Request:**
- Method: GET
- URL: http://localhost:8080/api/categories
- **Response:**
- Status: OK (200)
- Headers:
- Content-Type: application/json
- Transfer-Encoding: chunked
- Date: Wed, 10 Jan 2024 11:54:48 GMT
- Keep-Alive: timeout=60
- Connection: keep-alive
- Body:
```json
[
{
"id": 1,
"name": "Laptops",
"description": "Portable devices used for computing"
},
{
"id": 2,
"name": "Mobile Phones",
"description": "Handheld portable devices used for communication"
}
]
```
### Get all assets
- **Request:**
- Method: GET
- URL: http://localhost:8080/api/assets
- **Response:**
- Status: OK (200)
- Headers:
- Content-Type: application/json
- Transfer-Encoding: chunked
- Date: Wed, 10 Jan 2024 11:54:57 GMT
- Keep-Alive: timeout=60
- Connection: keep-alive
- Body:
```json
[
{
"id": 1,
"name": "Acer1",
"purchaseDate": "2024-01-09",
"conditionNotes": "New and Unused",
"category": {

"id": 1,
"name": "Laptops",
"description": "Portable devices used for computing"
},
"assignmentStatus": "RECOVERED"
},
{
"id": 2,
"name": "Samsung Galaxy S23",
"purchaseDate": "2024-01-09",
"conditionNotes": "New and Unused",
"category": {
"id": 2,
"name": "Mobile Phones",
"description": "Handheld portable devices used for communication"
},
"assignmentStatus": "AVAILABLE"
}
]
```
### Get category by id
- **Request:**
- Method: GET
- URL: http://localhost:8080/api/categories/1
- **Response:**
- Status: OK (200)
- Headers:
- Content-Type: application/json
- Transfer-Encoding: chunked
- Date: Wed, 10 Jan 2024 11:55:04 GMT
- Keep-Alive: timeout=60
- Connection: keep-alive
- Body:
```json
{
"id": 1,
"name": "Laptops",
"description": "Portable devices used for computing"
}
```
### Get asset by id
- **Request:**
- Method: GET
- URL: http://localhost:8080/api/assets/id/1
- **Response:**
- Status: OK (200)
- Headers:
- Content-Type: application/json
- Transfer-Encoding: chunked
- Date: Wed, 10 Jan 2024 11:55:10 GMT
- Keep-Alive: timeout=60
- Connection: keep-alive
- Body:
```json
{

"id": 1,
"name": "Acer1",
"purchaseDate": "2024-01-09",
"conditionNotes": "New and Unused",
"category": {
"id": 1,
"name": "Laptops",
"description": "Portable devices used for computing"
},
"assignmentStatus": "RECOVERED"
}
```
## POST
### Post a category
- **Request:**
- Method: POST
- URL: http://localhost:8080/api/categories
- Body (raw JSON):
```json
{
"name": "Audio Devices",
"description": "Consists of speakers and other devices used for audio"
}
```
- **Response:**
- Status: Created (201)
- Headers:
- Content-Type: application/json
- Transfer-Encoding: chunked
- Date: Wed, 10 Jan 2024 11:57:18 GMT
- Keep-Alive: timeout=60
- Connection: keep-alive
- Body:
```json
{
"id": 3,
"name": "Audio Devices",
"description": "Consists of speakers and other devices used for audio"
}
```
### Post an asset
- **Request:**
- Method: POST
- URL: http://localhost:8080/api/assets
- Body (raw JSON):
```json
{
"name": "Apple IPhone 15",
"purchaseDate": "2024-01-10",
"conditionNotes": "New and Unused",
"category": {
"id": 2
},
"assignmentStatus": "AVAILABLE"

}
```
- **Response:**
- Status: Created (201)
- Headers:
- Content-Type: application/json
- Transfer-Encoding: chunked
- Date: Wed, 10 Jan 2024 11:57:36 GMT
- Keep-Alive: timeout=60
- Connection: keep-alive
- Body:
```json
{
"id": 4,
"name": "Apple IPhone 15",
"purchaseDate": "2024-01-10",
"conditionNotes": "New and Unused",
"category": {
"id": 2,
"name": null,
"description": null
},
"assignmentStatus": "AVAILABLE"
}
```
## PUT
### Put to modify a category
- **Request:**
- Method: PUT
- URL: http://localhost:8080/api/categories/2
- Body (raw JSON):
```json
{
"name": "Mobile Phones",
"description": "Handheld portable devices used for communication"
}
```
- **Response:**
- Status: OK (200)
- Headers:
- Content-Type: application/json
- Transfer-Encoding: chunked
- Date: Wed, 10 Jan 2024 11:57:54 GMT
- Keep-Alive: timeout=60
- Connection: keep-alive
- Body:
```json
{
"id": 2,
"name": "Mobile Phones",
"description": "Handheld portable devices used for communication"
}
```
### Put to modify an asset

- **Request:**
- Method: PUT
- URL: http://localhost:8080/api/assets/1
- Body (raw JSON):
```json
{
"name": "Acer1",
"purchaseDate":
