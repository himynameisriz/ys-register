# What is this?
A pretty simple cash register application

# Requirements to run this project
[Node14](https://nodejs.org/en/download/current/) or [Docker](https://www.docker.com/)

# How to build and run (Node)
- Clone the repository
- Go to a terminal to the repository
- Run in terminal `npm install`

For development purposes:
- Run in terminal `npm run start`

For production purposes: 
- Run in terminal `npm run build`
- Run in terminal `npm run serve`

The API is now accessible from port 3000.

# How to build and run (Docker)
- Clone the repository
- Go to a terminal to the repository
- Run in terminal `docker build -t register .`
- Run in terminal `docker run -p 49160:3000 -d register`
-- You can change 49160 to any port you want

The API is now accessible from port 49160 (unless you chose something else)

# Available API calls

# make-change
This is a call to take in (with JSON) a total (the price of goods) and the paid amount (from the customer) and return the smallest amount of bills to return (i.e. one $5 bill instead of five $1 bills).

- URL
 localhost:3000/make-change
 
 - Method
 GET
 
 - Data Params
 We expect a JSON body in the form of:
 ```json
{
  "currency": "usd",
	"total": 123,
	"paid": 150
}
```
Note: Currency can be left blank, and will default to USD. Casing on the currency should not matter, and the program will fail if given a value for total or paid with more than 2 decimals.

- Success repsonse

- Failure response
There are generally three failure responses

An invalid total amount
```json
{
  "success": "false",
  "message": "Invalid total amount. Received undefined. Expected example: 12.34"
}
```

An invalid paid amount
```json
{
  "success": "false",
  "message": "Invalid paid amount. Received 123.123. Expected example: 12.34"
}
```

An unsupported currency
```json
{
  "success": "false",
  "message": "Currency is not supported, please use a supported currency: USD,GBP. Received: ABC."
}
```

- Sample call
```
localhost:49160/make-change
body: {
	"currency": "lala",
	"total": 123,
	"paid": 150
}
```
