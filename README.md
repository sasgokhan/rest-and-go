This is a API to lear Go Programming laguage
What you can do with this : 

You can perform basic CRUD(CREATE, READ, UPDATE and DELETE) operations

You can search on the Database 

We have also authentication configuration to improve security. You need to be authenticated to perform CRUD operations

Authentication is based on JWT (JSON Web Tokens)

I have used MongoDB as Backend data store. 

Setup Steps: 
1-) We need to setup Golang Development environment. I used wget https://raw.githubusercontent.com/canha/golang-tools-install-script/master/goinstall.sh for go installation

2-) Our directory should be in $GOPATH/src/ 

3-) We need to have MongoDB setup in our local environment
After installing Mongo DB, start it's server by typing mongod in Terminal.

4-) I have a sample file to inject some data to the database. Perform mongo < dummyData.js to insert the dummmy product data. You can update this as you wish. 

The database is on my local : 

const SERVER = "http://localhost:27017" 

if you are using different port or any other location, you need to update this at store/repository.go

5-) We need to install all the go dependencies

// Library to handle jwt authentication 
$ go get "github.com/dgrijalva/jwt-go"

// Libraries to handle network routing
$ go get "github.com/gorilla/mux"
$ go get "github.com/gorilla/context"
$ go get "github.com/gorilla/handlers"

// mgo library for handling Mongo DB
$ go get "gopkg.in/mgo.v2"

What we need to expect : The response will be in JSON format. Check snapshots for the views. 

6-) Authentication: We need to use CURL or POSTMAN :
curl -X POST \
-H "Content-Type: application/json" \
-d '{ username: "<YOUR_USERNAME>", password: "<RANDOM_PASSWORD>"}' \
BASE_URL/get-token
Check snapshots.

7-) Logging Check logs in Terminal which is running server. 

8-) What we can add : 
Session Management
User and Roles Management
Exception Handling
Unit Tests....
Better Log visualisation


