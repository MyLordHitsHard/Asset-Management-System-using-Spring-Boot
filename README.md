# Asset-Management-System-using-Spring-Boot
Assignment project

### To run this project after cloning:
-> Run the following docker command to create a database in MySQL <br>
-> ``` docker run -d -e MYSQL_ROOT_PASSWORD=1234 -e MYSQL_DATABASE=asset_management --name mysqldb -p 3306:3306 mysql:8.0 ``` <br>
-> After succesfully running the docker container, build/run the project <br>

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
