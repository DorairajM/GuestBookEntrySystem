# GuestBookEntrySystem
Basic CRUD operations 



GuestBookEntrySystem Project is developed using spring, angular 1.x and h2 database. This Project has two variants i.e secured and non-secured

1. Non Secured : Both UI and Rest resources are NOT secured
	
	a. Use http://localhost:8080/home url to launch the application. rest end point url is http://localhost:8080/guestBookEntries/
	b. All basic CRUD operations are supported.
	c. In order to test CORS, run the same application with 8090 port(http://localhost:8090)
	d. After running same app with 8090 port, message will be displayed like 'Hello, Guest Book User!, Datetime:2018-06-30T19:00:50.477' right to the 'Greetings from CORS domain:'
	
2. Secured: Both UI and Rest resources are secured

	a. Implemented spring security along with Oauth and JWT.
	b. Before using the application, need to configure access_token as access_token is hardcoded in angular request interceptor to access the protected resource.
	c. Issue the following curl command to get the access_token after running the application.
		curl testjwtclientid:XY7kmzoNzl100@localhost:8080/oauth/token -d grant_type=password -d username=dorairaj -d password=jwtpass
		output:
		{"access_token":"eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJhdWQiOlsidGVzdGp3dHJlc291cmNlaWQiXSwidXNlcl9uYW1lIjoiZG9yYWlyYWoiLCJzY29wZSI6WyJyZWFkIiwid3JpdGUiXSwiZXhwIjoxNTMwNDEyMjA5LCJhdXRob3JpdGllcyI6WyJTVEFOREFSRF9VU0VSIl0sImp0aSI6ImI5NjNlZDIzLTlkNWItNDZlNC1hYThlLWFmYjRhZTRiYTBjNiIsImNsaWVudF9pZCI6InRlc3Rqd3RjbGllbnRpZCJ9.2LYBMaS6dGNMSEAFA9Mt_cIuyM-wohTAQpRP1ohGfOI","token_type":"bearer","expires_in":43199,"scope":"read write","jti":"b963ed23-9d5b-46e4-aa8e-afb4ae4ba0c6"}
	d. Get the access_token from the above output and put value for config.headers.Authorization header in src/main/resources/static/js/app/app.js file. search with phrase 'config.headers.Authorization'. phrase will be found at line no 66 .

		ex:- config.headers.Authorization = 'Bearer eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJhdWQiOlsidGVzdGp3dHJlc291cmNlaWQiXSwidXNlcl9uYW1lIjoiZG9yYWlyYWoiLCJzY29wZSI6WyJyZWFkIiwid3JpdGUiXSwiZXhwIjoxNTMwNDEyMjA5LCJhdXRob3JpdGllcyI6WyJTVEFOREFSRF9VU0VSIl0sImp0aSI6ImI5NjNlZDIzLTlkNWItNDZlNC1hYThlLWFmYjRhZTRiYTBjNiIsImNsaWVudF9pZCI6InRlc3Rqd3RjbGllbnRpZCJ9.2LYBMaS6dGNMSEAFA9Mt_cIuyM-wohTAQpRP1ohGfOI';
	e. After replacing the access_token, Use http://localhost:8080/home url to launch the application. rest end point url is http://localhost:8080/guestBookEntries/
	f. All basic CRUD operations are supported.
	g. In order to test CORS, run the same application with 8090 port(http://localhost:8090)
	h. After running same app with 8090 port, message will be displayed like 'Hello, Guest Book User!, Datetime:2018-06-30T19:00:50.477' right to the 'Greetings from CORS domain:'
	
	
Please reach out to me incase of any queries, email: dorai.mca@gmail.com, mobile: +91 9885412626.
